
### 4. Optional: Node Styling for Clarity
You can style specific nodes directly, for example:

```mermaid
graph TD
    A([New Toner Issued for W7F3601570]):::start --> B{Is Device Black Toner 0%?}
    B -- Yes --> C([Replace with New Toner]):::action
    B -- No --> J([No Action Needed]):::end
    C --> D([Empty Black Toner Cartridge = Waste Toner]):::process
    D --> E([Place Waste Toner in Plastic Bag]):::process
    E -- Waste Toner Below 25% --> F([Request Collection from Supplier (Roziah's Email)]):::action
    E -- Waste Toner Full --> G([Return Full Waste Toner to Kairin SIMO]):::action
    G --> H([No Disposal Required at School]):::info
    H --> I([Return Any Unused Toner to Kairin SIMO]):::action
    F --> End([End]):::end
    J --> End
    I --> End
    classDef start fill:#fff,stroke:#333,stroke-width:2px;
    classDef action fill:#def,stroke:#036,stroke-width:2px;
    classDef end fill:#cfc,stroke:#393,stroke-width:2px;
    classDef process fill:#ffe,stroke:#cb3,stroke-width:2px;
    classDef info fill:#eef,stroke:#36c,stroke-width:2px;
