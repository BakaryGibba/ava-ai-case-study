[Back to README](../README.md)

# Appendix

## Glossary

| Term | Meaning |
| --- | --- |
| RAG | Retrieval-Augmented Generation, where retrieved context grounds model output |
| HRIS | Human Resources Information System |
| Tenant | A company or organization using the platform |
| Handover | Transfer from AI assistant to human HR support |
| Vector store | Database optimized for similarity search over embeddings |
| Embedding | Numeric representation of text used for semantic retrieval |
| Usage attribution | Recording AI usage by provider, model, tenant, user, and operation |

## Privacy Notes

This case study should not include:

- `.env` files or credentials.
- Uploaded HR documents.
- Database dumps or backups.
- Real employee names, emails, payroll, leave, claims, or chat content.
- Source code excerpts beyond high-level pseudocode or architecture descriptions.

## Reviewer Checklist

| Reviewer | What To Look For |
| --- | --- |
| Recruiter | Clear product story, technical scope, and contribution narrative |
| AI engineer | RAG design, provider abstraction, evaluation roadmap, safety decisions |
| Backend engineer | Modular service boundaries, auth, tenancy, usage governance |
| UX reviewer | Role-specific workflows, trust cues, escalation design |
| Academic supervisor | Problem framing, system design, trade-offs, future research directions |

## Repository Hygiene

The case study is generated as a sibling folder outside the existing `backend/` and `frontend/` repositories. This keeps it untracked by those repos while preserving access to the same workspace.

