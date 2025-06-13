```mermaid
graph TD
subgraph Reference to W7F3601570
    A[New Toner Issued] --> B{Is Device Black Toner 0%}
    B -- Yes --> C[Replace with New Toner]
    B -- No --> L{Is Waste Toner Below 25%}
end
    C --> D[Empty Black Toner Cartridge = Waste Toner]
    D --> E[Place Waste Toner in Plastic Bag]
subgraph For Full Waste Toner
    E -- Waste Toner Full --> G[Return CAS Kairin]
    G --> H[No Disposal Required at School]
    H --> I[Return Any Unused Toner]
end
    L -- Yes --> M[Request Supplier to Deliver New Toner]
    L -- No --> J[No Action Needed]
    J --> K[End – Reminder any disposal pass to CAS Kairin]
    I --> K
    M --> K
```
