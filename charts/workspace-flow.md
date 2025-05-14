```mermaid
flowchart LR
    A[Define Goal<br/>e.g. Add OAuth2] --> B[Brainstorm]
    B --> C[Summarize Code]
    B --> D[Ask Clarifying Questions]
    D --> E[User Responds]
    E --> F[Plan]
    F --> G[Task List<br/>e.g. Edit auth.py]
    F --> H[Show Affected Files]
    H --> I[Implement]
    I --> J[Suggest Code Changes]
    J --> K{Accept / Edit / Reject}
    K -- Accept --> L[Save Code]
    K -- Edit --> L
    K -- Reject --> M[Regenerate / Skip]
    L --> N[Review]
    N --> O[Bundle for Commit]
    O --> P[Generate Commit Message]
    P --> Q[Done]
