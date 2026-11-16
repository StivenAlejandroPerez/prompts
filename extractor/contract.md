# Extractor - contract

Stage: `discovery`. Background agent, no chat: the hub starts one run for each uploaded source, and the agent writes the notes of that source. Sources: `api/models/agent_workflow/agent_message.go`, `api/service/agent_workflow/source.go`, `api/service/agent_workflow/run_guard.go`, `api/http/mcp/server.go`, `api/http/mcp/tools.go`.

## What it reads

| Input | How | Notes |
|---|---|---|
| `AgentRequest` | `input_data` of the run | `kind: "extraction"` |
| The source | `list_sources`, `read_source_pages` | Text by pages, at most 20 per call. See `input_sources.md` |

`AgentRequest` fields of an extraction:

| Field | Meaning |
|---|---|
| `kind` | `extraction` |
| `cr_id` | The change request |
| `source_id`, `source_name` | The source to read |
| `pages` | Number of pages of the source |
| `hint` | Optional hint from the person (where to look first) |
| `notes_doc_id` | The document to write: `notes_{source_id}` |
| `provider_type`, `provider`, `operations` | Repeat the change request; `operations` can be empty |
| `contract_version`, `agent`, `change_request`, `docs` | Common fields; `stage` is empty for the extractor |

The agent has no `read_doc`: it cannot read back what it wrote.

## What it writes

| Document | `doc_id` | Rules |
|---|---|---|
| Notes of the source | `notes_{source_id}` | Only the notes of the source it is extracting |

Hub rules on `write_doc` (error codes the agent can read and fix):

| Error code | Cause |
|---|---|
| `doc_without_content` | Empty content |
| `doc_too_large` | More than 1 MiB |
| `invalid_doc_id`, `doc_id_not_allowed` | The id is not valid |
| `doc_not_writable_by_agent` | The doc type is not notes |
| `source_not_being_extracted` | Notes of another source |

Errors of `read_source_pages`: `invalid_page_range`, `max_pages_per_read_exceeded` (20), `page_out_of_range` (the message carries the total).

Each `write_doc` is the whole document and creates the next revision. The prompt asks for one write per run.

## What the hub does when the run ends
- Notes exist -> the source becomes `ready` with its `notes_doc_id`. When it was the last source in extraction, discovery moves to reviewing the notes.
- The run ended without notes -> the source is `failed` ("the extractor wrote no notes"). A failed source can be retried.
- The run failed -> the source is `failed` with the message of the run.

A person reviews the notes. Lumiere (`notes_{source_id}`, `Open questions for product`) and Nexus read them next.

## What it returns
`{"response": "<2 or 3 lines>"}`: source read, pages covered, operations found. The notes never travel in the reply.

## Athia configuration

| Setting | Value |
|---|---|
| MCP tools (exactly) | `list_sources`, `read_source_pages`, `write_doc` |
| Output | field `response` |
| Chat | none: one run per source |
| Knowledge base | none needed: the rules live in the prompt and in `doc_notes.md` |

## Not verified
- The behavior with a scanned PDF (no text layer).
- The behavior with a JSON file that is not a Postman collection.
- The memory mode in Athia for a run without chat.
