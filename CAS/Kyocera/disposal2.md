```mermaid

graph TD

    %% Main Flow
    A[New Toner Issued] --> B{Is Device Black Toner 0%?}
    B -- Yes --> C[Replace with New Toner]
    C --> D[Empty Black Toner Cartridge = Waste Toner]
    D --> E[Place Waste Toner in Plastic Bag]

    B -- No --> L{Is Waste Toner Below 25%?}
    L -- Yes --> M[Request Supplier to Deliver New Toner]
    M --> K[End – Reminder: any disposal pass to CAS Kairin]
    L -- No --> J[No Action Needed]
    J --> K

    E -- Waste Toner Full --> G[Return to CAS Kairin]
    G --> H[CAS will Dispose]
    H --> I[Return Any Unused Toner]
    I --> K

    %% Subgraphs for grouping (optional, but not required for rendering)
    subgraph "Reference to W7F3601570"
        A
    end

    subgraph "For Full Waste Toner"
        E
        G
        H
        I
    end

    %% Class Definitions for Styling
    classDef important fill:#FFD700,stroke:#B8860B,stroke-width:2px; %% Gold for important steps
    classDef decision fill:#ADD8E6,stroke:#4682B4,stroke-width:2px; %% Light Blue for decisions
    classDef process fill:#D3F3EE,stroke:#66CDAA,stroke-width:2px; %% Light Teal for processes
    classDef disposal fill:#FFC0CB,stroke:#FF69B4,stroke-width:2px; %% Pink for disposal steps
    classDef endNode fill:#DCDCDC,stroke:#808080,stroke-width:2px; %% Light Gray for end nodes

    %% Applying Classes to Nodes
    A:::important
    C:::important
    D:::process
    E:::process
    G:::disposal
    H:::disposal
    M:::important
    K:::endNode
    B:::decision
    L:::decision

```
