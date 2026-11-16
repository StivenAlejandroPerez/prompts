# Nomia - output files

What Nomia returns in `files`, and the rules for each file.

## Shape
```json
{ "path": "{operation}/{provider}_{operation}_{kind}_{n}.mapping", "content": "<the whole file>" }
```

## Rules
- The `path` is one of `work_item.files`, exactly as written. Any other path is a mistake.
- `content` is the whole file after the change, never a patch or a fragment.
- Only files that changed are returned. If the received file already does what the person asks, return no file and say so.
- Keep what the task does not touch: keys, order, comments, spacing.
- Keep the file valid in the format it had when received. If the received file is empty or new, follow the examples of the same kind in the TRD and the mapping reference.
- Every value added comes from the TRD, the PRD or the notes. If one is missing, ask; do not guess.
- No secrets, keys, tokens or customer data in a file.

## File naming (as the repo uses it)
| Kind | Path |
|---|---|
| Operation files | `{operation}/{provider}_{operation}_{kind}_{n}.mapping` |
| Shared files | `common/{provider}_{kind}_{n}.mapping` |
| Kinds seen | `communication`, `payload`, `response`, `errors`, `headers`, `statuses` |

Examples from the repo: `authorize/prosa2_authorize_payload_1.mapping`, `common/prosa2_headers_1.mapping`, `authorize/adyen_authorize_payload_1.mapping`.

## What the reply text says
For each changed file: the path, what changed (fields) and the criterion it covers (`prd_{operation}:AC-n`). If a criterion cannot be met in these files, it says so.
