# Provider general document (`provider_general`) - template

Written by Thoth with `write_doc`, `doc_id = provider_general`. One per CR. It follows the format of the general document the hub stores per version (see the seeded `general.md` of prosa2). Written in English.

```markdown
# {Provider}

{One paragraph: what the provider is, how it is integrated (API family), and how DEUNA uses it.}

# Environments

| Environment | Base URL |
|---|---|
| Develop / Staging / Sandbox | `{url}` |
| Production | `{url}` |

# Authentication

How requests are authenticated and signed: credential names read from the connection (never values), header names, signature algorithm, fields that go into the signature and where the result is sent. Keys are never logged.

# Encryption and sensitive data

- Encryption used by the provider, if any.
- Fields that DEUNA must obfuscate in logs: {field list}.

# Operations

| Operation | Endpoint | Notes |
|---|---|---|
| authorize | `POST /path` | ... |

# Idempotency

How the provider detects duplicates and what DEUNA sends for it.

# Limits and restrictions

What the provider cannot do or requires another path for.

# Test data

| Value | Result it triggers | Source |
|---|---|---|
| {provider-published test card or sandbox user} | {result} | notes p. N |

# Gaps

What the sources do not specify and the documentation could not state.
```

Rules:
- Every statement is verifiable in the files, the TRD, the PRD or the notes.
- Credentials appear by name only. Test data appears only if the provider published it.
- Level-1 headings (`#`) as above, tables for environments, operations and test data.
