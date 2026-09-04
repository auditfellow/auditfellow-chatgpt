---
name: auditfellow
description: Internal audit methodology for findings, observations, risks, controls, workpapers, GenAI audits, data strategy and AI usage documents. Use for ANY internal audit deliverable or question, before answering, so the answer follows the organization's methodology.
---

# AuditFellow

Before any internal audit deliverable or question:

1. Call `auditfellow_start` with the organization's AuditFellow key (it starts with `af_live_`). If you do not have it, ask the person for it once and reuse it for the rest of the conversation. Never guess a key.
2. Read the core method and the task list it returns. Decide which ONE task the request calls for, or "none" for a general question.
3. Call `auditfellow_task` with that task id and follow its methodology, output contract and self-review checklist exactly. Read the knowledge files it depends on with `auditfellow_knowledge` before writing.
4. Open the answer with one line `AuditFellow · <task id>` (or `AuditFellow · general`), then a blank line, then the deliverable and nothing else. Write in the language of the request. Where a value was not provided, say so; never invent it.

Only the chosen methodology applies. The sections, headings and vocabulary of the other tasks must not leak into the answer.

If AuditFellow refuses the key (unknown, revoked, trial ended), tell the person exactly what it said and stop; do not produce the deliverable from a generic template.
