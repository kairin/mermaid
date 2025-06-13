graph TD
    A[New Toner Issued] --> B{Is Device Black Toner 0%?}
    B -- Yes --> C[Replace with New Toner]
    C --> D[Empty Black Toner Cartridge = Waste Toner]
    D --> E[Place Waste Toner in Plastic Bag]
    B -- No --> L{Is Device Toner Below 25%?}
    L -- Yes --> M[Request Supplier to Deliver New Toner]
    M --> K[End – Return to CAS Kairin]
    L -- No --> J[No Action Needed]
    J --> K
    E -- Waste Toner Full --> G[Return to CAS Kairin]
    G --> H[CAS will Dispose]
    H --> I[Return Any Unused Toner]
    I --> K
    F1 --> C
    F2 --> K


    subgraph "Kyocera issue new Toner"
        A
        B
    end
    subgraph "Replace Full Waste Toner"
    D
    end
    subgraph "For Full Waste Toner"
        E
        G
        H
        I
    end
    subgraph "REMINDER DO NOT DISPOSE"
        K
    end
    subgraph "CMYK for Colour Device (a)"
        F1[Only K toner = Waste Toner]
    end
    subgraph "CMYK for Colour Device (b)"
        F2[CMY = not recycled]
    end
    subgraph "CMYK for Colour Device (c)"
        F3[C = Cyan]
        F4[M = Magenta]
        F5[Y = Yellow]
    end
    subgraph "CMYK for Colour Device (d)"
        F6[K = Black, Waste Toner]
    end

    %% Improved Class Definitions for Styling
    classDef important fill:#FFD700,stroke:#B8860B,stroke-width:2px,color:#222
    classDef decision fill:#4682B4,stroke:#274472,stroke-width:2px,color:#fff
    classDef process fill:#30bfa3,stroke:#17806D,stroke-width:2px,color:#fff
    classDef disposal fill:#FF69B4,stroke:#B22267,stroke-width:2px,color:#fff
    classDef endNode fill:#888888,stroke:#444444,stroke-width:2px,color:#fff

    %% Applying Classes to Nodes
    class A,C,M important
    class B,L decision
    class D,E process
    class G,H disposal
    class K endNode
