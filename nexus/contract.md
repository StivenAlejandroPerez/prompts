# Nexus - contract

Stage: `technical_review`. Background agent: it starts by itself when discovery is approved, never asks questions and plain chat messages are rejected by the hub (`agent_works_in_background`). Sources: `api/models/agent_workflow/agent_message.go`, `api/service/agent_workflow/work_item.go`, `api/http/mcp/server.go`, `api/http/mcp/tools.go`.

## What it reads

| Input | How | Notes |
|---|---|---|
| `AgentRequest` | `input_data` | `kind` is `stage_opening` or `reopen` |
| Approved discovery documents | `read_doc` for each entry of `stage.input_docs` | `prd`, `prd_{operation}`, `notes_{source_id}`, at the exact revisions listed |
| Files of the base version | `read_draft_file` with `source: base` | To make paths and changes real |
| Review round | `read_review` | Only when `stage.return_reason` is `review:NNN` |
| Current tasks | `read_work_items` | When replanning |
| Production comparison | `compare_versions` | Only when `stage.return_reason` is `update:vX` |

| Situation | Where it shows | Behavior |
|---|---|---|
| Normal stage opening | `kind: stage_opening`, no `return_reason` | Write `trd_{operation}` per operation and the overview `trd` |
| Code review asked for changes | `return_reason: review:NNN` | Read the round, replan the fix as new tasks |
| Request must update to a newer production version | `return_reason: update:vX` | Write the TRD for the update from `compare_versions` |
| A person commented a TRD | `kind: reopen` | Rewrite only `doc_id`, applying `comments[]` and `message` |

## What it writes

| Document | `doc_id` | Notes |
|---|---|---|
| TRD overview | `trd` | Must contain exactly one `work-items` block |
| TRD of one operation | `trd_{operation}` | Parent of the overview |

Rules the hub enforces on `trd` (error codes it returns, so the agent can fix and retry):

| Error code | Cause |
|---|---|
| `trd_without_work_items` | No `work-items` block |
| `trd_work_items_block_repeated` | More than one block |
| `trd_work_items_not_yaml` | The block is not a valid YAML list |
| `trd_work_items_empty` | The list is empty |
| `trd_work_items_too_many` | More than 30 tasks |
| `trd_work_item_id_invalid` | Id does not match `^[a-z0-9][a-z0-9_-]{0,49}$` |
| `trd_work_item_id_repeated` | Two tasks with the same id |
| `trd_work_item_without_title` | Empty title |
| `trd_work_item_without_files` | A task without files |
| `trd_work_item_file_invalid` | Path is empty, absolute, not clean or contains `..` |
| `trd_work_item_file_in_two_items` | A file owned by two tasks |

When the person approves technical review, the hub creates one work item and one Nomia chat per task of the block.

Common limits: whole document each time, not empty, at most 1 MiB, doc types of its agent only.

## What it returns
`{"response": "<text>"}`: documents written, number of tasks, version impact, assumptions. No documents in the reply.

## Athia configuration

| Setting | Value |
|---|---|
| MCP tools (exactly) | `list_sources`, `read_source_pages`, `read_doc`, `read_work_items`, `read_review`, `compare_versions`, `read_draft_file`, `write_doc` |
| Output | field `response` |
| Chat | none: one run per stage opening or reopen |

## Not verified or not built yet
- The path `update:vX` ("update to vX") is not implemented in the hub yet; the prompt section is forward-looking.
- In the review path, this contract follows the simulator: the `work-items` block lists only the new fix tasks and the tasks that do not appear stay as they are (done). Confirm how the hub applies a block on a replanned stage.
- The hub reads no "version impact" from the TRD in `service/agent_workflow` (no parser found): the section is a convention for people until the version flow reads it.
