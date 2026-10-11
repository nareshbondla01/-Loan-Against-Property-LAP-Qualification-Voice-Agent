# Home Credit AI Voice Agent — Loan Against Property (LAP)

## Live Voice Agent Demo

**Platform:** Retell AI

**Published Agent:** [Try the Loan Against Property (LAP) Qualification Voice Agent](https://agent.retellai.com/orb/agent_c220a67249d75495f5e18a46b1?token=5371d5bc36759eecde484748f4425a67)



## 1. Project Overview

This project implements an AI-powered voice agent for preliminary customer qualification for Home Credit's Loan Against Property (LAP) offering.

The agent conducts a natural voice conversation with prospective customers, explains the purpose of the call, collects the required eligibility information, evaluates mandatory screening criteria, and directs potentially eligible customers to a human loan specialist for further assessment.

The agent is designed to handle natural conversations, interruptions, out-of-order responses, clarification requests, customer objections, callback requests, and call termination.

The agent performs preliminary screening only. It does not make final credit decisions, guarantee loan approval, or independently sanction loans.

## 2. Project Objectives

The primary objectives of this project are:

- Verify that the intended customer is available to speak.
- Introduce the Loan Against Property offering professionally.
- Collect and validate the required eligibility checklist information.
- Remember information provided out of order and avoid repeatedly asking the same questions.
- Identify mandatory disqualification conditions.
- Handle loan amount and repayment tenure requirements.
- Identify existing property loans, balance-transfer requests, and EMI-reduction enquiries.
- Handle busy customers and record their preferred callback details when supported.
- Escalate cases requiring human assessment.
- Provide clear, polite closing messages for completed conversations.
- End calls through the platform's configured call-termination functionality.
- Validate the agent through structured test scenarios and recorded test calls.

## 3. Technology Stack

| Component | Technology |
|---|---|
| Voice agent platform | Retell AI |
| Conversation instructions | System prompt |
| Prompt file | `system-prompt.txt` |
| Test scenarios | `test-scenarios.md` |
| Test execution records | `test-results.md` |
| Submission tracking | `submission-checklist.md` |
| Documentation | Markdown |
| Version control | Git and GitHub |

A separate frontend or backend is not required for the assignment unless requested by the evaluator or needed for an additional integration.

## 4. Loan Against Property Qualification

The agent collects the following seven checklist items during the conversation.

| No. | Checklist item | Required screening |
|---|---|---|
| 1 | Property type | Identify whether the property is residential, commercial, industrial, or another category covered by the assignment's approved rules. |
| 2 | Property ownership | Establish whether ownership is sole or joint. |
| 3 | Original property documents | Confirm whether the required original property documents are available. |
| 4 | Requested loan amount | Record the requested amount and check it against the assignment's stated maximum offer of ₹75 lakh. |
| 5 | Occupation and income mode | Identify whether the customer is salaried or self-employed and whether the income is received through a bank rather than only in cash. |
| 6 | Property market value | Record the customer's estimated property value without inventing a minimum valuation threshold. |
| 7 | Preferred repayment tenure | Confirm the requested tenure and apply the assignment's permitted range of 3–15 years. |

The agent should collect missing information naturally, remember details already provided, and ask clarifying questions when an answer is ambiguous.

## 5. Eligibility Screening Rules

The agent follows the assignment's mandatory screening requirements.

### Property type
The agent identifies the property category and applies the assignment's approved property rules. Agricultural property must be handled according to the assignment's disqualification criteria.

### Ownership
The agent records whether the property is solely or jointly owned. Ownership information is collected for further assessment; the agent must not independently confirm legal title.

### Original documents
The agent checks whether the required original property documents are available. If a mandatory document requirement is not satisfied, the agent follows the assignment's disqualification flow.

### Loan amount
The maximum offer specified in the assignment is ₹75,00,000 (₹75 lakh).

If the customer requests more than the permitted maximum, the agent explains the limit and asks whether the customer wants to proceed within it, as required by the assignment.

A minimum loan amount should be applied only if it is confirmed in the assignment or an approved product policy.

### Occupation and income
The agent identifies the customer's occupation and how the income is received. Customers whose income is received only in cash must be handled according to the assignment's mandatory disqualification rule.

### Property value
The agent records the customer's estimated property market value. It must not invent a minimum property-value requirement or guarantee a loan amount based on the customer's estimate.

### Repayment tenure
The permitted range for this assignment is 3–15 years, inclusive.

Requests below three years or above fifteen years must be handled according to the assignment's tenure validation flow. The agent must not treat an out-of-range tenure as eligible.

### Important limitation
The voice agent performs preliminary screening. Human credit assessment, document verification, property valuation, and any final lending decision remain outside the agent's authority.

## 6. Conversation Workflow

The agent follows this general workflow:

1. Greet the customer and introduce the purpose of the call.
2. Confirm whether the customer is available to speak.
3. Offer a callback option if the customer is busy, using the available platform functionality.
4. Explain the LAP offering without promising approval.
5. Collect the seven eligibility checklist items.
6. Clarify ambiguous answers and confirm important values.
7. Apply the mandatory screening rules.
8. Identify existing property loans, balance-transfer requests, or EMI-reduction enquiries and direct these to the appropriate human specialist.
9. Summarize the collected information and explain the next step.
10. Close the conversation politely and trigger the configured end-call action.

The agent should handle interruptions, remember information shared earlier, and avoid repeating questions unnecessarily.

## 7. Language and Voice Behaviour

The agent is configured for natural voice interaction in English and Hindi.

Its conversation behaviour includes:

- Short, clear, conversational responses.
- One question at a time.
- Polite clarification of unclear or inconsistent answers.
- Appropriate handling of customer interruptions.
- Professional responses to objections and requests for a human representative.
- No unsupported promises about interest rates, approval, disbursement, or callback scheduling.

The final supported languages must match the deployed Retell configuration.

## 8. Call Termination

The agent has explicit closing instructions for completed and disqualified conversations.

The intended behaviour is to:

- Provide a brief, appropriate closing message.
- Avoid repeatedly asking whether the customer is still present after a terminal outcome.
- Avoid restarting qualification after the conversation has concluded.
- Trigger the configured Retell call-ending action.

The prompt instructions alone do not guarantee that a telephone call or browser voice session will disconnect. Actual termination depends on the configured platform functionality and must be verified during testing.

## 9. Testing and Quality Assurance

Testing is performed using structured scenarios documented in `test-scenarios.md`.

The scenarios cover:

- Eligible customer journeys.
- Mandatory disqualification conditions.
- Loan amount boundary conditions.
- Tenure boundary conditions.
- Missing or unclear customer information.
- Out-of-order responses and interruptions.
- Busy customers and callback requests.
- Existing property loans and balance-transfer enquiries.
- Customer requests for human assistance.
- English and Hindi interactions.
- Closing messages and actual call termination.
- Unsupported policy questions and cases requiring escalation.

Actual outcomes are recorded in `test-results.md`.

Each test result should distinguish between the expected behaviour and the behaviour observed during the call. Failed scenarios should be documented and retested after the relevant correction.

## 10. Project Structure

The repository contains the following documentation and test files:

```text
home-credit-voice-agent/
├── README.md
├── system-prompt.txt
├── test-scenarios.md
├── test-results.md
└── submission-checklist.md
```

### File descriptions

- `README.md`: Project overview, requirements, workflow, and testing approach.
- `system-prompt.txt`: Complete system prompt used by the deployed Retell agent.
- `test-scenarios.md`: Planned test cases and expected behaviour.
- `test-results.md`: Actual test outcomes, observations, and failures.
- `submission-checklist.md`: Final submission and evidence checklist.

The system prompt stored in the repository should match the final prompt deployed in Retell AI.

## 11. Deployment and Demo

**Voice Agent Platform:** Retell AI

**Live Voice Agent Demo:** [Insert the Retell Voice Orb shareable link]

**GitHub Repository:** [Insert the GitHub repository URL]

The Retell shareable link should be tested before submission to confirm that the evaluator can access the voice demo.

A shareable browser voice demo is not necessarily a telephone number. If telephone access is required, the relevant calling configuration must also be available.

## 12. Test Evidence

The assignment evidence should include:

- Call recordings for representative scenarios.
- Corresponding conversation transcripts.
- Test results documenting expected and actual behaviour.
- Evidence of mandatory disqualification flows.
- Evidence of eligible-customer handling and human handoff.
- Evidence that completed conversations terminate correctly.

**Call Recordings and Transcripts:** [Insert the publicly accessible evidence link]

Only authorised test calls and appropriate test customer data should be used. Evidence-sharing permissions should be checked before submission.

## 13. Limitations and Responsible Behaviour

- The agent performs preliminary qualification and does not approve or sanction loans.
- It must not invent interest rates, charges, minimum property values, or other unconfirmed product rules.
- A callback must not be represented as scheduled unless a functioning scheduling mechanism confirms it.
- The agent must not request OTPs, PINs, passwords, or other prohibited sensitive information.
- Personal and financial information must be handled according to applicable privacy requirements and authorised company processes.
- Uncertain eligibility cases should be escalated rather than receiving unsupported guarantees.
- Final decisions remain subject to the lender's verification and assessment procedures.

## 14. Deliverables

The final submission includes:

1. The complete system prompt used by the voice agent.
2. The configured Retell AI voice agent and its demo or calling access.
3. A public link to the required call recordings and call logs.
4. Audio recordings and transcripts demonstrating the tested scenarios.
5. Test scenarios and actual test results.
6. Project documentation and repository link.

## 15. Conclusion

This project demonstrates the configuration and testing of an AI-powered voice agent for preliminary Loan Against Property customer qualification.

The agent combines structured eligibility screening with natural conversational behaviour, clarification handling, human escalation, and call-termination requirements.

The objective is to provide a professional and consistent initial customer interaction while keeping final lending decisions and unconfirmed policy matters under human and authorised company control.