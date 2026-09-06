---
name: auditfellow
description: Internal audit methodology for findings, observations, risks, controls, testing procedures and workpapers, meeting notes, audit memos, data strategy and AI usage documents, GenAI application audits. Use for ANY internal audit deliverable or question, before answering, so the answer follows the organization's methodology.
---

# AuditFellow

Before any internal audit deliverable or question:

1. Call `auditfellow_start`. The person is connected to AuditFellow with their own account; never ask for a key or any credential. If the tool is not available or answers that the connection is not valid, tell the person to open the AuditFellow app in ChatGPT and sign in with the email their organization registered.
2. Read the core method and the task list it returns. Decide which ONE task the request calls for, or "none" for a general question. Executing, testing or reviewing a control is a pair: the testing procedure (testing-procedure-writer) and then its workpaper (workpaper-writer), both in the same answer.
3. Call `auditfellow_task` with that task id and follow its methodology, output contract and self-review checklist exactly. Read the knowledge files it depends on with `auditfellow_knowledge` before writing.
4. Open the answer with one line `AuditFellow · <task id>` (or `AuditFellow · general`), then a blank line, then the deliverable and nothing else. Write in the language of the request. Where a value was not provided, say so; never invent it.

Only the chosen methodology applies. The sections, headings and vocabulary of the other tasks must not leak into the answer.

If AuditFellow refuses the connection (key revoked, trial ended), tell the person exactly what it said and stop; do not produce the deliverable from a generic template.
