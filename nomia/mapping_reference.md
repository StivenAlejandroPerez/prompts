# Mapping reference (knowledge base of Nomia) - DRAFT, incomplete

Purpose: the document Nomia consults for names and syntax of `.mapping` files. This draft holds only what is visible in this repository. The real specification of the mapping engine is NOT here and must be added before Nomia can be trusted to write mappings.

## What is verified (from the simulator samples in `api/scripts/athia-sim/documents/mappings/`)
- A mapping file is a JSON-shaped text with template expressions between double braces.
- Values come from the transaction request, for example `{{.transaction_request.transaction.amount}}`, and from global settings, for example `{{.globals.<provider>_api_url}}`.
- File kinds and what a sample of each holds:

| Kind | Sample content (keys seen) |
|---|---|
| `communication` | `url`, `http_method`, `use_static_client`, `response_type`, `interceptor_redirect_get_headers`, `payload_type`, `case_sensitive_headers` |
| `payload` | The JSON body sent to the provider, with template values |
| `response` | How the provider response is read |
| `errors` | Provider error codes mapped to DEUNA codes |
| `headers` | Request headers |
| `statuses` | Provider statuses mapped to DEUNA statuses |

- Naming: `{operation}/{provider}_{operation}_{kind}_{n}.mapping`, shared files `common/{provider}_{kind}_{n}.mapping`.

## What is missing (to be written from the mapping engine documentation)
1. The complete syntax: conditionals, loops, functions available inside `{{ }}`, escaping, null handling.
2. The full list of variables (`transaction_request.*`, `globals.*`, connection and merchant data).
3. The exact schema of each file kind: required keys, allowed values, defaults.
4. How `statuses` and `errors` are matched and what happens on no match.
5. How `response` extracts values and where they land in the DEUNA result.
6. Validation rules and how to run the existing scenarios or tests of a mapping.
7. Two or three complete real examples per kind (sanitized).

## Rules for the final version
- English, with every statement checked against the engine.
- Examples sanitized: no real credentials, keys or customer data.
