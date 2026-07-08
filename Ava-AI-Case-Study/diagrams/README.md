[Back to README](../README.md)

# Diagrams Plan

This folder contains editable Mermaid source files for the case-study diagrams. The same diagrams also appear inside the Markdown docs for GitHub rendering.

## Diagram Inventory

| Mermaid Source | Optional Export | Source Document | Diagram Type | Purpose |
| --- | --- | --- | --- |
| [`architecture.mmd`](architecture.mmd) | `architecture.png` | `docs/03-system-architecture.md` | System architecture | Shows frontend, backend, database, Qdrant, AI providers, and HRIS |
| [`workflow.mmd`](workflow.mmd) | `workflow.png` | `docs/04-ai-workflow.md` | RAG workflow | Shows document ingestion through answer generation |
| [`sequence.mmd`](sequence.mmd) | `sequence.png` | `docs/04-ai-workflow.md` | Sequence diagram | Shows employee chat request lifecycle |
| [`handover-sequence.mmd`](handover-sequence.mmd) | `handover-sequence.png` | `docs/04-ai-workflow.md` | Sequence diagram | Shows AI-to-HR handover |
| [`erd.mmd`](erd.mmd) | `erd.png` | `docs/06-database.md` | ER diagram | Shows core data model relationships |
| [`state.mmd`](state.mmd) | `state.png` | `docs/06-database.md` | State diagram | Shows chat and handover lifecycle |
| [`journey.mmd`](journey.mmd) | `journey.png` | `docs/02-business-problem.md` | User journey | Shows employee, HR admin, and superadmin flows |
| [`decision-flow.mmd`](decision-flow.mmd) | `decision-flow.png` | `docs/09-engineering-decisions.md` | Decision flow | Shows routing between HRIS, RAG, refusal, and handover |

## Export Guidance

If image exports are needed for a presentation or visual README gallery:

1. Open the `.mmd` file in a Mermaid-compatible editor.
2. Export the rendered diagram as PNG or SVG.
3. Save it with the optional export filename above.
4. Do not include real employee data or private tenant names in any diagram.

## Quality Bar

Each exported image should be readable at 1440px width, use neutral labels, and avoid implementation-specific secrets or internal hostnames.
