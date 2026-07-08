[Back to README](../README.md)

# 04 AI Workflow

## Workflow Summary

Ava AI uses retrieval-augmented generation for policy answers and live HRIS queries for employee-specific facts. This separation is the core safety decision: the model should explain and synthesize, but the system should decide which sources are trusted.

## Document Ingestion

```mermaid
flowchart TD
    Upload[HR admin uploads PDF or DOCX] --> Validate[Validate file type and ownership]
    Validate --> Extract[Extract text]
    Extract --> Chunk[Split into overlapping chunks]
    Chunk --> Embed[Generate embeddings]
    Embed --> Store[Store vectors with document metadata]
    Store --> Ready[Document available for scoped retrieval]
```

Key characteristics:

| Step | Purpose |
| --- | --- |
| Validation | Prevent unsupported or oversized files from entering the workflow |
| Chunking | Keep retrieval units small enough for relevant context |
| Embedding | Convert policy text into searchable vector representations |
| Metadata | Preserve document, category, owner, organization, and HRIS company scope |

## Employee Question Flow

```mermaid
sequenceDiagram
    participant Employee
    participant Frontend
    participant API
    participant HRIS
    participant Qdrant
    participant AI
    participant DB

    Employee->>Frontend: Ask HR question
    Frontend->>API: Send message with session context
    API->>DB: Store employee message
    API->>API: Classify intent and resolve scope
    alt Personal HRIS question
        API->>HRIS: Fetch employee-specific record
        API->>AI: Generate concise answer from HRIS facts
    else Policy question
        API->>Qdrant: Hybrid vector and text search
        Qdrant-->>API: Relevant policy chunks
        API->>AI: Generate grounded response
    else Out of scope
        API->>DB: Store safe refusal
    end
    API->>DB: Store assistant message and usage
    API-->>Frontend: Return answer
```

## Handover Flow

```mermaid
sequenceDiagram
    participant Employee
    participant Assistant
    participant API
    participant HRAdmin
    participant Realtime

    Employee->>Assistant: Asks unresolved or sensitive question
    Assistant->>API: Offer HR handover
    API->>Realtime: Notify admin escalation views
    Employee->>API: Accepts handover
    API->>Realtime: Mark session open for HR
    HRAdmin->>API: Sends reply in same session
    API->>Realtime: Deliver reply to employee console
```

## Provider Strategy

Ava AI abstracts AI providers behind chat and embedding services. The platform can use OpenAI or Gemini based on settings, while usage attribution remains consistent.

| Decision | Benefit |
| --- | --- |
| Provider abstraction | Reduces lock-in and supports operational switching |
| Usage attribution | Makes cost and credit controls enforceable |
| Temporary-unavailable handling | Gives users a clear fallback when providers fail |
| Development embedding override | Supports local testing without relying on production providers |

## Screenshot

![Ava AI grounded employee answer](../screenshots/employee-chat-answer.png)

This employee chat example demonstrates the central AI value proposition: a practical HR answer in a confidential assistant interface.
