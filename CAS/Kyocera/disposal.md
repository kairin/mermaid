```mermaid
graph TD
    A[New Toner Issued for W7F3601570] --> B{Is Device Black Toner 0%?}
    B -- Yes --> C[Replace with New Toner]
    B -- No --> J[No Action Needed]
    C --> D[Empty Black Toner Cartridge = Waste Toner]
    D --> E[Place Waste Toner in Plastic Bag]
    E -- Waste Toner Below 25% --> F[Request Collection from Supplier (Roziah's Email)]
    E -- Waste Toner Full --> G[Return Full Waste Toner to Kairin SIMO]
    G --> H[No Disposal Required at School]
    H --> I[Return Any Unused Toner to Kairin SIMO]
    F --> K[End]
    J --> K
    I --> K
    %% Optional: Node styling (may not take effect on GitHub)
    classDef start fill:#fff,stroke:#333,stroke-width:2px;
    classDef action fill:#def,stroke:#036,stroke-width:2px;
    classDef end fill:#cfc,stroke:#393,stroke-width:2px;
    classDef process fill:#ffe,stroke:#cb3,stroke-width:2px;
    classDef info fill:#eef,stroke:#36c,stroke-width:2px;
    class A start;
    class C,F,G,I action;
    class K end;
    class D,E process;
    class H info;
