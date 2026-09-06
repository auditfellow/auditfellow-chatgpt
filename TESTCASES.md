# Review test cases for the ChatGPT plugin directory

Test account: provided privately in the submission form (Test Audit Team). Connecting the app opens a sign-in page at auditfellow.app; sign in with the test account's email and password and press Connect. No key is typed anywhere.

## Positive

1. Prompt: "Draft an audit finding: during the walkthrough of vendor onboarding we saw 14 of 40 sampled vendors activated without the required sanctions screening." Expected: auditfellow_start, then auditfellow_task issue-writer; answer opens "AuditFellow · issue-writer" and follows the finding contract (condition, criteria, cause, effect, recommendation, assumptions), writing N/A where a value was not provided. No key is asked for.
2. Prompt: "Write the risk for unauthorized changes to the payroll master file in a company with 2,300 employees and no periodic review of master-file changes." Expected: auditfellow_task risk-writer; answer opens "AuditFellow · risk-writer" with the organization's risk structure, rating fields as N/A.
3. Prompt: "Describe the control: the treasury manager reviews the monthly bank reconciliation prepared by an analyst and signs it within five business days of month end." Expected: auditfellow_task control-writer; answer opens "AuditFellow · control-writer" and follows the control contract.
4. Prompt: "Execute control C-P2P-12, the four-eyes rule on payment release in SAP, over the 1,240 payments of Q1 2026: sample of 45, two payments released through an emergency profile by a user without the releaser role. Tester Ana Ruiz. Share the workpaper." Expected: auditfellow_task testing-procedure-writer and workpaper-writer; two deliverables in one answer, the testing procedure first and then the workpaper as a two-column summary with the procedure referenced under Details.
5. Prompt: "We are auditing a customer service chatbot built on a large language model, deployed on the public website of a retail bank. Which controls should the audit cover?" Expected: auditfellow_knowledge genai-application-audit; a plain prose answer opening "AuditFellow · general", no document template.

## Negative (the app should not trigger)

1. Prompt: "What is the capital of Peru?" General knowledge, no audit content.
2. Prompt: "Can you audit my Spotify playlist and tell me which songs I skip the most?" Audit-sounding word in a non-audit context.
3. Prompt: "Is it risky to keep my savings in a single bank account?" Personal finance question that mentions risk but is not an internal audit deliverable.

## Connection checks

1. "Draft an audit finding" before connecting the app: ChatGPT asks to connect AuditFellow (sign-in page); nothing is produced from a generic template.
2. "Draft an audit finding" after connecting: auditfellow_start then auditfellow_task issue-writer, and the model never asks for a key.
