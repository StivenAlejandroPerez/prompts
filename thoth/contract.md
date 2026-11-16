# Thoth - contract

Stage: `documentation`. Background agent: it starts after the person approves the code review and the version is tagged, never asks questions, and a person reaches it only with line comments (reopen). Sources: `api/models/agent_workflow/agent_message.go`, `api/service/agent_workflow/doc.go`, `api/http/mcp/server.go`, `api/scripts/seed/agent_workflow/s3/agents/knowledge/payments/prosa2/v10.0.0/`.

Thoth was not in the list of agents requested for this round; the files are a draft.

## What it reads

| Input | How | Notes |
|---|---|---|
| `AgentRequest` | `input_data` | `kind` is `stage_opening` or `reopen` |
| PRD, TRD, notes | `read_doc` | The provider facts come from the notes; the requested behavior from PRD and TRD |
| Tasks | `read_work_items` | What was built, per task |
| Code of the version | `read_draft_diff`, `list_draft_files`, `read_draft_file` | `source: draft` or `source: base` |
| Tests | `get_test_results` | Existing scenarios and results |
| Sources | `list_sources` | Names of the material |

## What it writes

| Document | `doc_id` | Content |
|---|---|---|
| General guide | `provider_general` | Environments and URLs, authentication and signature, encryption, sensitive data, common behavior, operations table, idempotency, limits, test data |
| One per operation | `provider_{operation}` | Endpoint, payload, response, status table, errors, flow, limits, examples |

The hub accepts any `provider_{name}`. This contract proposes `provider_general`, following the design doc (`docs/agent_workflow.html`). The simulator writes `provider_overview` instead; align one of them.

The format follows the documents the hub already stores per version in `agent_knowledge` (files `general.md` and one per operation), so these documents can be registered as the knowledge of the version: level-1 headings, tables for endpoint, status and errors.

Hub rules on `write_doc`: whole document, not empty, at most 1 MiB, doc types of its agent (`provider` only), valid ids.

When all provider documents are approved, the person approves the stage and the CR is delivered. Registering the documents in `agent_knowledge` when the version is assigned is a different flow.

## What it returns
`{"response": "<text>"}`: documents written and the gaps found.

## Athia configuration

| Setting | Value |
|---|---|
| MCP tools (exactly) | `list_sources`, `read_doc`, `read_work_items`, `read_draft_diff`, `list_draft_files`, `read_draft_file`, `get_test_results`, `write_doc` |
| Output | field `response` |
| Chat | none: one run per stage opening or reopen |

## Not verified
- The id of the general document (`provider_general` vs `provider_overview`).
- Whether the draft is still readable through the MCP tools after the version is tagged and the CR moves to `documentation`.
- Whether the registration in `agent_knowledge` expects exact headings.
