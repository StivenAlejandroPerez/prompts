# Veto - contract

Stage: `code_review`. Background agent: it runs when a person asks for a code review ("Create version" / "Request code review"), one run per round, and delivers one report. A person reads it and approves or asks for changes. Sources: `api/models/agent_workflow/review.go`, `api/models/agent_workflow/agent_message.go`, `api/http/mcp/tools.go`, `api/scripts/athia-sim/scenarios/veto.yaml`.

## What it reads

| Input | How | Notes |
|---|---|---|
| `AgentRequest` | `input_data` | `review` = `{review_id, branch, snapshot}` |
| Documents | `read_doc` | `prd`, `prd_{operation}`, `trd` |
| Tasks | `read_work_items` | Operation, status, files each task may change, acceptance criteria |
| What changed | `read_draft_diff` | Draft (`release/{cr_id}`) vs the version it started from (the one in production). Per file: status added/modified/removed, changed lines with numbers, owner task. `task_files_untouched` lists task files with no change |
| Files | `list_draft_files`, `read_draft_file` | `source: draft` or `source: base` (the production version) |
| Tests | `get_test_results` | Per kind: status, passed, failed, failure titles. `ran=false` = no test run on the draft |

## What it writes

One report per round with `write_review`:

```json
{
  "cr_id": "CR-0140",
  "result": "changes_requested",
  "summary": "Two or three sentences for the person.",
  "comments": [
    { "file": "authorize/prosa2_authorize_payload_1.mapping", "line_start": 12, "line_end": 14, "severity": "blocker", "body": "What is wrong, the evidence, and what to change." }
  ]
}
```

| Field | Rule |
|---|---|
| `result` | `approved` or `changes_requested` |
| `summary` | Two or three sentences |
| `comments[].file` | Path inside the draft |
| `comments[].line_start`, `line_end` | Optional; lines of the draft file |
| `comments[].severity` | `blocker`, `major` or `minor`. Blockers are what makes a review ask for changes |
| `comments[].body` | Required |

The hub stores the report at `cr/{cr_id}/reviews/{nnn}.json` and a row `REVIEW#{nnn}`. It is called once per round.

What the hub does next:
- A report with a blocker asks for changes and the hub returns the CR to development by itself.
- An approved report waits for a person: approve (go to documentation) or ask for changes.

Veto writes no documents (`agentDocTypes` is empty for it).

## What it returns
Short text in `response`: the round, the result, the number of blockers.

## Athia configuration

| Setting | Value |
|---|---|
| MCP tools (exactly) | `read_doc`, `read_work_items`, `read_draft_diff`, `list_draft_files`, `read_draft_file`, `get_test_results`, `write_review` |
| Output | field `response` |
| Chat | none: one run per round |

## Not verified
- Which tests run on the draft today and whether `get_test_results` covers e2e for mappings.
- Whether the hub validates that `comments[].file` exists in the draft.
