```mermaid
graph TD
    A[Start] --> B(Log into VPN);
    B --> C(Log into Another Server);
    C -- Server checks VPN connection --> D{Access Granted?};
    D -- Yes --> E(Access IPtel Dashboard);
    E --> F(Assign IP Phone Numbers);
    F --> G[End];
    D -- No --> H(Access Denied: VPN not detected);
    H --> C;
// Optional: Loop back to try logging into server again or to VPN
```
