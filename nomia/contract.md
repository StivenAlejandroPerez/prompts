# Nomia - contract

Stage: `development`. One chat per task (`nomia.{work_item_id}`) so the memory stays small. It does not start by itself: the person starts each task from the payments editor ("Agent loop"). Sources: `api/models/agent_workflow/agent_message.go`, `api/models/agent_workflow/work_item.go`, `api/service/agent_workflow/agent_request.go`, `api/scripts/athia-sim/scenarios/nomia.yaml`.

## What it reads

| Input | How | Notes |
|---|---|---|
| `AgentRequest` | `input_data` | `kind` is `stage_opening` or `message` |
| `work_item` | in the request | `work_item_id`, `operation`, `title`, `files[]` (the only writable paths), `trd_section`, `criteria[]` |
| `files[]` | in the request, on `message` | `[{path, content}]`: the task files as the person has them in the editor, unsaved edits included |
| TRD | `read_doc` `trd` and `trd_{operation}` | The section named by `work_item.trd_section` is its instruction |
| PRD | `read_doc` `prd_{operation}` | Acceptance criteria |
| Notes and sources | `read_doc`, `list_sources`, `read_source_pages` | To check provider facts |

| kind | Behavior |
|---|---|
| `stage_opening` | Read the TRD, say what it will change, in which files, for which criteria. No files yet. |
| `message` with `files` | Propose the change as whole files |
| `message` without `files` | Ask the person to open the task files in the editor and repeat |

## What it writes

Nothing through MCP. The hub does not give Nomia a write tool: `agentDocTypes` is empty for it and its workspace tools (`read_file`, `write_file`) are not built. Its MCP profile has `list_sources`, `read_source_pages` and `read_doc` only.

It proposes changes in the reply:
- `files`: whole files, each `{path, content}`, with a path from `work_item.files`.
- The editor shows them as a diff; accepting them commits them to the draft of the CR.

## What it returns

```json
{
  "response": "Short text for the person.",
  "files": [
    { "path": "authorize/prosa2_authorize_payload_1.mapping", "content": "<the whole file>" }
  ]
}
```

- `response` is required. `files` is omitted or empty when nothing changed.
- The response lists each changed file, what changed and the criterion it covers.

## Athia configuration

| Setting | Value |
|---|---|
| MCP tools (exactly) | `list_sources`, `read_source_pages`, `read_doc` |
| Output | `response` and `files` (both must reach the run output) |
| Chat | one per task; the hub sends a `thread_id` per chat |
| Knowledge base | the mapping reference (`mapping_reference.md`), once it exists |

## Not verified or not built yet
- How Athia's Output node resolves a nested path such as `{{nodes.main.response.files}}` so `files` reaches `output_data`. The hub docs list it as unchecked.
- Whether the hub rejects a path outside `work_item.files` or only the prompt prevents it.
- The tool `run_unit_tests` mentioned in the design is not built.
- The real mapping language reference (see `mapping_reference.md`).
