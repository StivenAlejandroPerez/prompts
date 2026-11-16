# PRD of one operation (`prd_{operation}`) - template

Written by Lumiere with `write_doc`, `doc_id = prd_{operation}` (for example `prd_authorize`). One per operation of the CR. The operation id is lowercase. A person approves it. Written in English.

```markdown
# PRD - {operation}

Parent: `prd` · Sources: `notes_{source_id}`, ...

## Objective
What this operation must do after the change. 2 to 4 lines.

## Flow
1. Step by step, as the source describes it (authentication, signature, call, response handling).
   Each step cites `notes_{source_id} p. N`.

## Request requirements
| Field | Rule | Required | Depends on | Reference | Source |
|---|---|---|---|---|---|
| {exact field name} | type, length or range, format, default | yes / no / "Not specified" | field it depends on | "same value as {field} of {operation}" | notes p. N |

## Response requirements
Same table for the fields DEUNA must read or keep.

## Statuses and mapping to DEUNA
Statuses of this operation only. A status that the source does not tie to this operation is not listed here: it goes under Open questions.
| Provider status | DEUNA status | Meaning | Source |
|---|---|---|---|

## Errors
| HTTP | Provider code | Message | Expected DEUNA outcome | Source |
|---|---|---|---|---|

## Business rules and limits
Rules and restrictions of the provider that apply to this operation.

## Edge cases
- ...

## Test data
Provider-published test cards or sandbox values and the result each one triggers (as the notes have them).

## Acceptance criteria
- AC-1 ...
- AC-2 ...

## Out of scope
- ...

## Assumptions and open questions
| Item | Type (assumption / question) | Who must answer |
|---|---|---|
```

Rules:
- Acceptance criteria are numbered `AC-1`, `AC-2`... inside this document, one verifiable behavior each, using field names exactly as the notes spell them. Nexus and Veto refer to them as `prd_{operation}:AC-n`.
- Do not write file names, mapping syntax or implementation steps: that is the TRD.
- If the source says a value is not specified, write "Not specified in the source" and add the question below. Never guess a size, a format or a default.
