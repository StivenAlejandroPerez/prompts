# TRD overview (`trd`) - template

Written by Nexus with `write_doc`, `doc_id = trd`. One per CR. A person approves it, and approving it creates the work items. Written in English.

````markdown
# TRD - Overview

- CR: {cr_id} · {change_request.title}
- Provider: {provider} ({provider_type}) · Kind: {new_provider | change | rebase}
- Based on: `prd` rev {n}, `prd_{operation}` rev {n}, ..., notes `notes_{source_id}` rev {n}
- Base version: {base_version or "none (new provider)"}

## Technical summary
What changes, in which operations, and the approach. 4 to 8 lines.

## Operations
| Operation | TRD | Files touched |
|---|---|---|
| {operation} | `trd_{operation}` | n |

## Shared files
Files that more than one operation uses (headers, communication, statuses) and the change to each.

## Version impact
{major | minor | patch}: reason.

## Risks and provider limitations
- ...

## Coverage of acceptance criteria
| Criterion | Task | Where it is met |
|---|---|---|
| `prd_{operation}:AC-n` | {task id} | file and section |

## Tasks
How the work is split into tasks for Nomia and why (granularity rule below).

```work-items
- id: authorize
  operation: authorize
  title: Send the new fields in authorize
  files:
    - authorize/{provider}_authorize_payload_1.mapping
    - authorize/{provider}_authorize_response_1.mapping
  trd_section: trd_authorize
  criteria: [prd_authorize:AC-1, prd_authorize:AC-2]
```

## Assumptions
| Assumption | Why | Impact if wrong |
|---|---|---|
````

## The `work-items` block (the hub validates it)

- Exactly one block per TRD overview: three backticks plus `work-items`, and a YAML list inside.
- Fields of each task:

| Field | Rule |
|---|---|
| `id` | `^[a-z0-9][a-z0-9_-]{0,49}$`, unique. The chat of the task is `nomia.{id}` |
| `operation` | The operation the task belongs to, or `common` |
| `title` | Not empty |
| `files` | At least one. Relative path, no leading `/`, no `..`, clean. One file belongs to one task |
| `trd_section` | `overview` or `trd_{operation}`: where Nomia reads the detail |
| `criteria` | Acceptance criteria ids it must satisfy |

- At most 30 tasks.
- Granularity (as the simulator plays it): `new_provider` -> one task per operation plus one `common` task for shared files. Change on one operation -> one task. Change on several operations -> one task per operation.
- File naming: `{operation}/{provider}_{operation}_{kind}_{n}.mapping`, shared `common/{provider}_{kind}_{n}.mapping`. Kinds seen in the repo: `communication`, `payload`, `response`, `errors`, `headers`, `statuses`.

## Replan after a code review (`review:NNN`)
Add a section `Fixes from review NNN` with what the review asked and the new tasks (ids that do not clash with the existing ones, files the review marked). Tasks not listed in the block stay as they are.

## Update to a newer production version (`update:vX`)
Add a section `Update to vX` with the decision for each overlap file (what production content is kept, what part of the request change is redone), the files that are brought together without a decision, and the re-check of each acceptance criterion against the new base. Not built in the hub yet.
