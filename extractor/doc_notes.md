# Notes of one source (`notes_{source_id}`) - template

Written by the extractor with `write_doc`, `doc_id = notes_{source_id}` (the hub sends it as `notes_doc_id`). One per source. A person reviews it, and Lumiere and Nexus read it. Written in English.

```markdown
# Notes - {source_name}

- Source: `{source_id}` · pages read: 1-{pages}
- Provider: {provider} ({provider_type})
- Operations of the CR: {operations or "not defined"}
- Hint from the person: {hint or "none"}

## Source summary
3 to 5 lines: what the document is and what it covers.

## Capabilities according to the source
| Capability | According to the source | Conditions or limits | Citation |
|---|---|---|---|
(purchase, refund, void, capture, polling, webhooks, 3DS, OTP, optional integrations such as express or direct.
Regions and payment methods only if the source mentions them, literal, without classifying them.)

## Limitations
What the source says CANNOT be done or requires another path, with citation.

## General configuration
### URLs and environments
Production, development or sandbox. (p. N)
### Authentication and required credentials
Names and how they are obtained. Never values.
### Common headers
### Signature and encryption
### HTTP status codes and general error format
### Sensitive data to obfuscate in logs
Field · why · citation.
### Test data
Card or user · result it triggers · citation.

## Operation: {name}
### Step-by-step flow
1. ...
### Endpoint
`METHOD /path` (p. N)
### Request
| Field | Type | Length or range | Required | Format or values | Default | Depends on | Reference | Citation |
|---|---|---|---|---|---|---|---|---|
### Successful response
Same field table.
### Error responses
| Code | Message | Meaning | Citation |
### Statuses
| Status | Meaning | Applies to (operation or event) | Citation |
### Field dependencies and references
### Limitations of this operation
### Examples
Literal request and response, with citation.

## Events and webhooks
Events, order, frequency, retries, signature, configuration restrictions. (p. N)

## Not found in the source
| Item | Result |
|---|---|
| Required credentials | Found (p. N) / Not found |
| URLs per environment | |
| Test data (cards, users) | |
| Errors | |
| Statuses | |
| HTTP status codes | |
| Signature and encryption | |
| Request and response examples | |
| Event order or state machine | |

## Open questions for product
1. Concrete question, with the page or section that raises it.

## Pages without useful content
```

Rules:
- Every fact has a citation `(p. N)` or `(pp. N-M)`. A fact without a citation is not written.
- If the source does not say it, write literally "Not specified in the source". It applies to each attribute of a field (type, length, required, format, default). Never deduce a format from a field name.
- A status, error code, field or rule belongs only to the operation or event the source ties it to. If the source does not say which, write "Not specified which operation it applies to".
- Literal values (URLs, headers, field names, codes, enums) are copied exactly.
- Test cards and sandbox values that the provider publishes are copied as they are, with the result they trigger. Real keys, tokens and passwords are `[REDACTED]`.
- Everything ambiguous, contradictory or missing goes to "Open questions for product" as a concrete question. Lumiere reads that section and asks the person.
- If the extractor could not cover every page, the header says `pages read: 1-40 of 90` and an open question asks for the rest.
- If a section does not apply, keep the title and one line saying why.
