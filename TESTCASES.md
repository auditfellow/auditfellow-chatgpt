# Review test cases for the ChatGPT plugin directory

Test key: provided privately in the submission form (Test Audit Team, coordinator profile).

## Positive

1. Prompt: "Draft an audit finding: during the walkthrough of vendor onboarding we saw 14 of 40 sampled vendors activated without the required sanctions screening." Expected: auditfellow_start, then auditfellow_task issue-writer; answer opens "AuditFellow · issue-writer" and follows the issue contract (condition, criteria, cause, effect, recommendation), stating what was not provided.
2. Prompt: "Write the risk for unauthorized changes to the payroll master file." Expected: auditfellow_task risk-writer; answer opens "AuditFellow · risk-writer" with the organization's risk structure and rating fields.
3. Prompt: "Describe the control: monthly reconciliation of bank accounts reviewed by the treasury manager." Expected: auditfellow_task control-writer; answer opens "AuditFellow · control-writer" and follows the control contract.
4. Prompt: "Prepare the workpaper for a test of 25 purchase orders against the approval matrix, 2 exceptions found." Expected: auditfellow_task workpaper-writer; answer opens "AuditFellow · workpaper-writer" and reads foundations-workpapers first.
5. Prompt: "We are auditing a customer service chatbot built on a large language model. What should the audit program cover?" Expected: auditfellow_task genai-audit; answer opens "AuditFellow · genai-audit" and reads genai-application-audit knowledge.

## Negative

1. Prompt: "Draft an audit finding" with no key in the conversation. Expected: the model asks for the AuditFellow key and does not produce the finding from a generic template. Reason: the methodology belongs to the organization and is only served to a valid key.
2. Prompt: "Use key af_live_0000 and write a risk." Expected: the tool returns "AuditFellow refused the key: unknown key." and the model reports that verbatim and stops. Reason: unknown keys must not receive the methodology.
3. Prompt: "What is the capital of Peru?" Expected: no task applies; the model answers plainly, at most opening with "AuditFellow · general", and imposes no audit template. Reason: the harness must not force a methodology on general questions.
