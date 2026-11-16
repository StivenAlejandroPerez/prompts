# PRD overview (`prd`) - template

Written by Lumiere with `write_doc`, `doc_id = prd`. One per CR. A person approves it. Written in English.

```markdown
# PRD - Overview

- CR: {cr_id} · {change_request.title}
- Provider: {provider} ({provider_type}) · Kind: {new_provider | change | rebase}
- Base version: {base_version or "none (new provider)"}
- Requested by: {requested_by}

## Problem and goal
Why the change is requested and what success looks like, in the person's terms. 3 to 6 lines.

## Scope
### In scope
- ...
### Out of scope
- ...

## Operations
| Operation | PRD | Why it is in scope |
|---|---|---|
| {operation} | `prd_{operation}` | ... |
Operations defined by: {person | Lumiere after reviewing the material}.

## Sources used
| Notes | Source | What it contributed |
|---|---|---|
| `notes_{source_id}` | {source_name} | ... |

## Requirements shared by all operations
Environments and URLs, authentication and signature, common headers, sensitive fields that DEUNA must obfuscate in logs, common HTTP behavior. Each item cites `notes_{source_id} p. N`.

## Provider limitations
What the provider cannot do or requires another path for (for example: no same-day refunds, everything through settlement). Each item cites its source.

## Common acceptance criteria
- AC-1 ...
- AC-2 ...

## Assumptions
| Assumption | Why it was needed | Who must confirm |
|---|---|---|

## Open questions
Questions still unanswered when this revision was written. Empty if none.
```

Rules:
- Criteria are numbered `AC-1`, `AC-2`... inside this document, one verifiable behavior each.
- Nothing about files, mappings or implementation steps.
- "Not specified in the source" facts stay as open questions or assumptions, never as requirements.
