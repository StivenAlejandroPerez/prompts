# TRD of one operation (`trd_{operation}`) - template

Written by Nexus with `write_doc`, `doc_id = trd_{operation}` (for example `trd_authorize`). One per operation. It is the `trd_section` that the tasks of that operation point to. Written in English.

```markdown
# TRD - {operation}

Parent: `trd` · Comes from: `prd_{operation}` rev {n}

## Goal
What the operation must do after the change, in technical terms. 2 to 4 lines.

## Files and changes
| File | Change (field level) | Criteria |
|---|---|---|
| `{operation}/{provider}_{operation}_payload_1.mapping` | Add `{field}` under `{path}`, value from `{source}` | `prd_{operation}:AC-1` |

## Request
Fields to send: exact name, type, length or range, required or dependent on another field, value source. A field the PRD marks "Not specified" is listed here as an assumption.

## Response
Fields to read and where they go in the DEUNA result.

## Statuses
Provider status -> DEUNA status, for this operation only.

## Errors
Provider code -> DEUNA code, the same way the existing files do it.

## Signature, headers and sensitive fields
What changes, if anything. Sensitive fields to obfuscate in logs.

## Tests
- New scenarios to add.
- Existing scenarios that must keep passing.

## Criteria of the PRD this covers
- `prd_{operation}:AC-1`, `prd_{operation}:AC-2`

## Assumptions
| Assumption | Why | Impact if wrong |
|---|---|---|
```

Rules:
- Every path in the table exists in the base version or follows the naming convention. When the file is new, say "new file".
- Every acceptance criterion of `prd_{operation}` appears in at least one row.
- No code or mapping content is written here beyond what is needed to be exact about a field: Nomia writes the files.
