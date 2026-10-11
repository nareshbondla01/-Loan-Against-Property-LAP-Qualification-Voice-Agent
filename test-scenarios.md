# Home Credit AI Voice Agent — Test Scenarios

## Purpose

Use these scenarios to verify the agent's business logic, conversation handling, eligibility decisions, and call-ending behaviour.

Run each scenario as a separate test call. Record the actual result in `test-results.md`.

## Test 1 — Fully Eligible Customer

**Customer responses**

- Property: Residential.
- Ownership: Sole.
- Original documents: Available.
- Loan amount: ₹50 lakh.
- Occupation: Salaried.
- Income mode: Bank.
- Property market value: ₹1 crore.
- Tenure: 10 years.

**Expected result**

The agent captures all seven checklist items, recognises that the stated criteria are met, gives the senior-expert callback message, and ends the call.

## Test 2 — Agricultural Property

**Customer:** "My property is agricultural land."

**Expected result**

Immediate disqualification message and call termination. No further eligibility questions.

## Test 3 — Original Documents Unavailable

**Customer:** "I don't have the original property documents available."

**Expected result**

Immediate disqualification and call termination.

## Test 4 — Cash Income

**Customer:** "I'm self-employed, and my income comes in cash."

**Expected result**

Immediate disqualification and call termination.

## Test 5 — Tenure Below Minimum

**Customer:** "I want to repay the loan in two years."

**Expected result**

Immediate disqualification and call termination.

## Test 6 — Tenure Above Maximum

**Customer:** "I would like a repayment period of twenty years."

**Expected result**

Immediate disqualification and call termination.

## Test 7 — Loan Request Above ₹75 Lakh, Customer Agrees

**Customer:** "I need ₹90 lakh."

**Expected result**

The agent explains the ₹75 lakh limit and asks whether the customer would like to proceed with ₹75 lakh.

**Customer:** "Yes, ₹75 lakh is fine."

The agent records ₹75 lakh and continues the qualification process.

## Test 8 — Loan Request Above ₹75 Lakh, Customer Declines

**Customer:** "I need ₹90 lakh."

**Agent:** Explains the maximum and offers ₹75 lakh.

**Customer:** "No, I need the full ₹90 lakh."

**Expected result**

The agent thanks the customer and ends the call.

## Test 9 — Joint Ownership

**Customer:** "The property is jointly owned by me and my wife."

**Expected result**

Joint ownership is accepted. The agent continues the qualification process.

## Test 10 — Existing Property Loan

**Customer:** "I already have a loan against this property."

**Expected result**

The agent directs the customer to a loan-transfer specialist and ends the call without continuing the fresh-loan checklist.

## Test 11 — EMI Reduction Request

**Customer:** "I want to reduce my existing EMI."

**Expected result**

The agent directs the customer to a loan-transfer specialist and ends the call.

## Test 12 — Busy Customer

**Customer:** "I'm in a meeting right now."

**Expected result**

The agent asks for a convenient callback time, acknowledges the answer if provided, and ends the current call.

## Test 13 — Out-of-Order Answers

**Customer:** "It's a residential house, jointly owned with my wife, and worth about ₹1.2 crore."

**Expected result**

The agent remembers property type, ownership, and market value. It must not ask those questions again and should ask the earliest missing checklist item.

## Test 14 — Multiple Answers in One Response

**Customer:** "It's my own residential house. I have the original documents, need ₹40 lakh, and prefer ten years."

**Expected result**

The agent captures property type, ownership, document availability, loan amount, and tenure. It asks only for the remaining missing information, including occupation, income mode, and market value.

## Test 15 — Customer Asks About Interest Rates

**Customer:** "What is the exact interest rate?"

**Expected result**

The agent does not invent a rate. It explains that the senior loan expert will provide the exact rate and then resumes the earliest missing checklist question.

## Test 16 — Ambiguous Document Availability

**Customer:** "I think the original papers are somewhere at home."

**Expected result**

The agent clarifies whether the original documents are available for verification. It must not assume they are available.

## Test 17 — Corrected Property Type

**Customer:** "It's a residential property. Actually, sorry, it's agricultural land."

**Expected result**

The agent recognises the latest clear answer and immediately disqualifies the customer.

## Test 18 — Market Value Without a Threshold

**Customer:** "My property is worth around ₹20 lakh."

**Expected result**

The agent records the estimated value. It must not disqualify the customer based on an invented market-value threshold.

## Test 19 — Maximum Tenure Boundary

**Customer:** "I want fifteen years to repay the loan."

**Expected result**

The tenure is accepted. The agent continues collecting any missing information.

## Test 20 — Minimum Tenure Boundary

**Customer:** "I want three years to repay the loan."

**Expected result**

The tenure is accepted. The agent continues collecting any missing information.

## Test 21 — Customer Declines the Offer

**Customer:** "I'm not interested."

**Expected result**

The agent respects the decision, thanks the customer, and ends the call.

## Test 22 — Customer Changes Loan Amount

**Customer:** "I need ₹30 lakh. Actually, make it ₹40 lakh."

**Expected result**

The agent records ₹40 lakh as the latest requested amount.

## Test 23 — Bank Income With Salaried Occupation

**Customer:** "I'm salaried, and my salary is credited to my bank account."

**Expected result**

Both occupation and income mode are recorded. The agent does not ask either question again.

## Test 24 — Bank Income With Self-Employment

**Customer:** "I run a business, and my income is received in my bank account."

**Expected result**

Self-employment and bank income are accepted. The agent continues the checklist.

## Test 25 — Premature Handoff Prevention

Provide some eligible answers but deliberately leave one checklist item unanswered.

**Expected result**

The agent must ask for the missing information. It must not give the final qualification handoff until all seven checklist items have been answered and all applicable criteria have passed.

## Test Execution Rules

- Do not mark a scenario as passed until an actual call has been tested.
- Record the observed response and call evidence.
- If the result differs from the expected result, record the issue and retest after correction.
- Use the platform's actual call-ending and recording capabilities.
- Do not use real customer data without appropriate authorisation.