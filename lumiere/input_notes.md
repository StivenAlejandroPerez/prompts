# Lumiere - the notes it reads (extractor output)

The extractor writes one document per source: `notes_{source_id}`. The template is `extractor/doc_notes.md` (at the root of this repo). Lumiere reads every notes document before it asks anything.

## Sections and how Lumiere uses them

| Section of the notes | What it holds | What Lumiere does with it |
|---|---|---|
| Header | Source id, pages read, provider, operations of the CR, hint | Checks that the pages read cover the whole source (`pages read 1-N`). If not, asks for the rest. |
| Source summary | What the document is | Context for the overview |
| Capabilities according to the source | Features (purchase, refund, void, capture, polling, webhooks, 3DS, OTP, optional integrations), regions and payment methods only if mentioned | Candidate operations and scope |
| Limitations | What the source says cannot be done or needs another path | Goes into the PRD as requirements and limits |
| General configuration | URLs and environments, authentication (names only), headers, signature and encryption, HTTP codes, sensitive fields to obfuscate, test data | Cross-operation requirements in the overview |
| Operation: {name} | Flow step by step, endpoint, request and response field tables (type, length, required, format, default, depends on, reference), statuses with the operation they belong to, errors, examples | The base of `prd_{operation}` |
| Events and webhooks | Event order, frequency, retries, signature, configuration limits | Requirements of the operations that use them |
| Not found in the source | Table: credentials, URLs, test data, errors, statuses, HTTP codes, signature, examples, event order | Gaps to ask about |
| Open questions for product | Concrete questions with page or section | The first questions to ask the person |
| Pages without useful content | Empty or unreadable pages | Ask for a better source if it matters |

## Reading rules
- "Not specified in the source" means unknown. It is never filled in from general knowledge.
- Every fact has a citation `(p. N)`. When Lumiere carries a fact into a PRD it keeps the reference as `notes_{source_id} p. N`.
- A status or error is valid only for the operation or event it is listed under. If the notes say "Not specified which operation it applies to", the PRD keeps that doubt and asks.
- Test data (test cards, sandbox users) is copied as the notes have it. Real credentials never appear: `[REDACTED]`.
- Several notes documents can contradict each other. Lumiere reports both versions to the person and does not pick one.

## When the notes are not good enough
Lumiere may reopen a notes document (it can write `notes_{source_id}`) when a person asks. It rewrites it complete with the same template and never adds facts that are not in the source.
