# Provider operation document (`provider_{operation}`) - template

Written by Thoth with `write_doc`, `doc_id = provider_{operation}` (for example `provider_authorize`). One per operation of the CR. It follows the format of the per-operation documents the hub stores per version (see the seeded `authorize.md` of prosa2). Written in English.

```markdown
# {operation}

{One or two lines: what the operation does.}

# Flow

1. Step by step (authentication, signature, call, response handling).

# Endpoint

| Field | Value |
|---|---|
| Endpoint | `METHOD {base}/path` |
| Headers | `Header-Name: value or description` |

# Payload

```json
{ "example": "request body as the mapping builds it" }
```

Fields:
| Field | Type | Length or range | Required | Format or values | Default | Depends on |
|---|---|---|---|---|---|---|

# Response

```json
{ "example": "provider response" }
```

Fields DEUNA reads: {list}.

# Status

| Provider | DEUNA | Meaning |
|---|---|---|
Statuses of this operation only.

# Errors

| HTTP | Provider code | What DEUNA does |
|---|---|---|

# Limits

Restrictions of the provider for this operation.

# Examples

Request and response pairs, including a failure case, with test data published by the provider.

# Gaps

What is not specified.
```

Rules:
- Payload and response come from the mapping files of the version (`..._payload_1.mapping`, `..._response_1.mapping`), not from the PRD wishes.
- Status and errors come from the `statuses` and `errors` mapping files and the notes.
- Anything the source marks as "Not specified in the source" is written as "Not specified", never completed.
- Statuses and errors that the sources do not tie to this operation are not listed here.
