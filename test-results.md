# Home Credit AI Voice Agent — Test Results

## Test Environment

- Voice platform: Not configured yet
- Test date: Not started
- Language: To be configured
- Voice: To be configured
- Tester: Project owner

## Result Definitions

- NOT RUN — Test has not been executed.
- PASS — Actual behaviour matches the expected result.
- FAIL — Actual behaviour does not match the expected result.
- BLOCKED — Unable to test because of a platform or configuration issue.

## Test Execution Log

| Test ID | Scenario | Expected result | Actual result | Status | Recording / transcript link | Notes |
|---|---|---|---|---|---|---|
| T01 | Fully eligible customer | Senior-expert handoff after all seven items | Not run | NOT RUN | Not available | |
| T02 | Agricultural property | Immediate disqualification | Not run | NOT RUN | Not available | |
| T03 | Original documents unavailable | Immediate disqualification | Not run | NOT RUN | Not available | |
| T04 | Cash income | Immediate disqualification | Not run | NOT RUN | Not available | |
| T05 | Tenure below 3 years | Immediate disqualification | Not run | NOT RUN | Not available | |
| T06 | Tenure above 15 years | Immediate disqualification | Not run | NOT RUN | Not available | |
| T07 | Above ₹75 lakh; accepts ₹75 lakh | Continue with ₹75 lakh | Not run | NOT RUN | Not available | |
| T08 | Above ₹75 lakh; declines alternative | End politely | Not run | NOT RUN | Not available | |
| T09 | Joint ownership | Continue qualification | Not run | NOT RUN | Not available | |
| T10 | Existing property loan | Transfer-specialist message and end | Not run | NOT RUN | Not available | |
| T11 | EMI reduction | Transfer-specialist message and end | Not run | NOT RUN | Not available | |
| T12 | Busy customer | Request callback time and end | Not run | NOT RUN | Not available | |
| T13 | Out-of-order answers | Remember supplied details | Not run | NOT RUN | Not available | |
| T14 | Multiple answers | Capture all supplied facts | Not run | NOT RUN | Not available | |
| T15 | Interest-rate question | Do not invent a rate | Not run | NOT RUN | Not available | |
| T16 | Ambiguous documents | Clarify availability | Not run | NOT RUN | Not available | |
| T17 | Corrected property type | Apply latest clear answer | Not run | NOT RUN | Not available | |
| T18 | Market-value estimate | Do not invent threshold | Not run | NOT RUN | Not available | |
| T19 | 15-year tenure | Accept boundary | Not run | NOT RUN | Not available | |
| T20 | 3-year tenure | Accept boundary | Not run | NOT RUN | Not available | |
| T21 | Customer declines | End politely | Not run | NOT RUN | Not available | |
| T22 | Corrected loan amount | Use latest amount | Not run | NOT RUN | Not available | |
| T23 | Salaried with bank income | Capture both details | Not run | NOT RUN | Not available | |
| T24 | Self-employed with bank income | Capture both details | Not run | NOT RUN | Not available | |
| T25 | Missing checklist item | Prevent premature handoff | Not run | NOT RUN | Not available | |

## Defect Log

For every failed or blocked test, record:

- Defect ID:
- Test ID:
- Summary:
- Steps to reproduce:
- Expected behaviour:
- Actual behaviour:
- Severity:
- Recording or transcript link:
- Corrective action:
- Retest result:

## Final Summary

- Total scenarios: 25
- Passed: 0
- Failed: 0
- Blocked: 0
- Not run: 25

Update these counts after executing the tests. Do not report untested scenarios as passed.

## Evidence

Store the actual recording and transcript links for each executed test. Confirm that the evaluator can access the shared links before submission.