%%{init: {'theme': 'default', 'themeVariables': { 'background': '#fff' }}}%%
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
    F --> End[End]
    J --> End
    I --> End
