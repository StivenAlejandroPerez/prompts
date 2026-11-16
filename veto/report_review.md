# Veto - report format and severity guide

The report is the arguments of `write_review`. Written in English. The person reads it in the review page and sees the comments by file and line.

## Summary
Two or three sentences:
1. What was checked (documents, tasks, files, tests).
2. The verdict and the main reason.

Example: "I checked the 3 tasks against prd_authorize and prd_purchase, read the 5 changed files and the unit test results. The authorize payload does not send the new field for AC-2, so I ask for changes. Purchase is correct."

## One comment
| Field | What to write |
|---|---|
| `file` | Path inside the draft, for example `authorize/prosa2_authorize_payload_1.mapping` |
| `line_start`, `line_end` | The lines of the draft file that show the problem |
| `severity` | `blocker`, `major` or `minor` |
| `body` | What is wrong, the evidence (criterion or TRD section), what to change |

Body pattern: `[AC-2 of prd_authorize] The field "cryptogram" is not sent when network_token is present. TRD trd_authorize says it is required in that case. Add it under "paymentInformation".`

## Severity guide

| Severity | Use when | Examples |
|---|---|---|
| blocker | An acceptance criterion is not met, a test fails or did not run, a task file has no change, a secret or card data is in a file, a file is invalid | Criterion without evidence in the code; `ran=false`; `task_files_untouched` not empty; token in a mapping |
| major | A real problem that does not break a criterion | Risky default, inconsistency between two operations, missing edge case from the PRD |
| minor | Clarity or small inconsistencies | A misleading name, an unused key |

Rules:
- `changes_requested` if there is at least one blocker, `approved` otherwise.
- Majors and minors go as comments in an approved report.
- One issue per comment. If the same issue appears in several files, comment once and name the other files.
- Do not ask for work that no PRD, TRD or task requested.

## Checklist before `write_review`
1. Every acceptance criterion of every task has evidence or a blocker.
2. Every task file was checked (`task_files_untouched` read).
3. Tests were read (`get_test_results`).
4. No file outside the tasks changed without a reason.
5. No secrets or card data in any file.
6. `write_review` is called once.
