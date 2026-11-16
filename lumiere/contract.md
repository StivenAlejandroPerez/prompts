# Lumiere - contract

Stage: `discovery`. Chat agent: it talks with the person who opened the change request (CR). Sources: `api/models/agent_workflow/agent_message.go`, `api/http/mcp/server.go`, `api/http/mcp/tools.go`, `api/service/agent_workflow/doc.go`, `api/service/agent_workflow/run_guard.go`.

## What it reads

| Input | How | Notes |
|---|---|---|
| `AgentRequest` | `input_data` of the run | The hub sends it on every run. Kinds below. |
| Notes `notes_{source_id}` | `read_doc` | Written by the extractor. See `input_notes.md`. |
| Sources | `list_sources`, `read_source_pages` | Raw pages, max 20 per call. Only to verify a fact. |
| Its own PRDs | `read_doc` | `prd`, `prd_{operation}`, latest or a given `rev`. |

`AgentRequest` kinds Lumiere receives:

| kind | Why it runs | Fields that matter | Expected behavior |
|---|---|---|---|
| `message` | A person wrote in the chat | `message` | Ask blocking questions, or write the PRDs once confirmed |
| `reopen` | A person commented one document | `doc_id`, `on_revision`, `comments[]`, `message` | Rewrite only that document |
| `sources_updated` | New files were read | `new_notes[]` | Read them, update the overview, flag affected PRDs |
| `stage_opening` | Discovery just opened | `stage`, `docs` | Read the notes, say what the material covers, first questions |

Other fields: `change_request` (`kind` new_provider/change/rebase, `provider`, `provider_type`, `title`, `operations`, `operations_known`, `operations_by`, `base_version`), `docs[]` (state of every document), `contract_version` (1).

## What it writes

| Document | `doc_id` | Written with | Approval |
|---|---|---|---|
| PRD overview | `prd` | `write_doc` | A person approves it (stage `discovery`) |
| PRD of one operation | `prd_{operation}` | `write_doc` | A person approves it |
| Notes (only on reopen) | `notes_{source_id}` | `write_doc` | Notes are read and approved or reopened like any document |

Also writes the operation list: `set_operations` (complete list, lowercase ids). The hub refuses to drop an operation that already has its PRD.

Hub rules that apply to every `write_doc`:
- The agent sends the whole document, not a diff. Each call creates the next revision (`r001`, `r002`...).
- Not empty, at most 1 MiB (`doc_without_content`, `doc_too_large`).
- Only the doc types of its agent: notes and prd (`doc_not_writable_by_agent` otherwise).
- Valid ids only (`invalid_doc_id`, `doc_id_not_allowed`).
- A document is rewritten only by the agent of its `owner_stage`.

## What it returns

The output of the run is `{"response": "<text>"}`. The text goes to the chat. Documents never travel in the reply.

The reply should say: what was written (ids and revisions) and what is needed from the person.

## Athia configuration

| Setting | Value |
|---|---|
| MCP tools (exactly) | `list_sources`, `read_source_pages`, `read_doc`, `set_operations`, `write_doc` |
| Output | field `response` (the hub also accepts `answer`, `output`, `message`, `text`, `content`) |
| Input | the `AgentRequest` as `input_data`; the hub sends a `thread_id` per chat |
| Memory | chat agent: confirm the memory mode with the Athia team (not verified) |

## Next in the flow
When the PRDs are approved, Nexus (`technical_review`) reads `prd`, every `prd_{operation}` and the notes.

## Not verified
- How Athia's memory modes behave with the `thread_id` the hub sends.
- Whether the acceptance criteria ids can repeat across PRD documents without confusing the work items. This contract proposes `AC-n` per document and references like `prd_authorize:AC-2` in the TRD.
