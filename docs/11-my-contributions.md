[Back to README](../README.md)

# 11 My Contributions

> [!NOTE]
> Built with the engineering team at Apping Technology Sdn. Bhd. during my AI Engineering internship (2026). This page describes my part of the work.

## Contribution Summary

My work on Ava AI was end-to-end: product reasoning, architecture, backend implementation, frontend UX, AI workflow design, data modeling, and governance.

## Contribution Areas

| Area | Contribution |
| --- | --- |
| Product architecture | Defined the multi-role HR assistant model for employees, HR admins, and superadmins |
| AI workflow | Designed RAG ingestion, scoped retrieval, provider abstraction, and answer routing |
| Backend engineering | Built modular services for chat, documents, usage, settings, organizations, and realtime events |
| Data modeling | Structured tenants, users, chat sessions, documents, settings, usage, and audit concepts |
| Frontend UX | Created role-specific consoles for chat, admin operations, and platform oversight |
| Safety design | Added handover, out-of-scope handling, usage limits, and privacy-aware boundaries |
| Portfolio documentation | Converted the implementation into a readable architecture case study |

## Technical Narrative

The strongest engineering contribution is the system boundary design. Ava AI does not treat the LLM as the product. The product is the workflow around the model: document ingestion, retrieval scope, HRIS data access, role-based review, usage governance, and escalation.

## Engineering Judgment

- Separated policy knowledge from live employee facts.
- Added provider switching without changing feature-level UX.
- Treated AI usage as an accountable platform resource.
- Designed realtime handover so unresolved questions become HR workflows.
- Documented the architecture in a way that is readable to both technical and non-technical reviewers.

## Screenshot

![Ava AI API usage dashboard](../screenshots/super-api-usage.png)

The API usage dashboard supports the contribution story around governance and production-minded AI engineering.
