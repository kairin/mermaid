# simple-signage-solution Dockerised Flow

```mermaid

graph LR
    Title["<b>Dockerised Flow</b>"]:::title
    Title 
    A(simple-signage-solution <b>Start Here</b>)
    A --> B

    subgraph Dockerised VPN Flow Prerequisite Steps
        B[Log into ITE VPN]:::vpnstep --> C[simple-signage needs to download new posters from Sharepoint Server]:::vpnstep
        C --> D{ITE Server verifies VPN}:::vpnstep
        D -- No --> X[Access Denied: VPN not detected]
    end

    D -- Yes --> E[Access Sharepoint Dashboard]
    E --> F[Download Latest Posters]
    F --> H[Disconnect from SharePoint server]
    subgraph Daily Rebuild [Daily Rebuild Cycle]
        R1[Trigger rebuild of simple-signage-solution]
        R2[Build new image with latest posters/videos]
        R3[Ready for next day's display]
        R1 --> R2 --> R3 --> I
    end

    H --> R1

    I --> B
    H --> Y[Not connected to ITE's server]
    X --> Y

    classDef title fill:#fff,stroke:#fff,color:#222,font-size:20px
    classDef vpnstep fill:#e0f7fa,stroke:#00796b,stroke-width:4px
    class B,C,D vpnstep
    style D fill:#ccf,stroke:#333,stroke-width:2px,stroke-dasharray: 5 5
    style X fill:#fcc,stroke:#333,stroke-width:2px
    style A fill:#fff,stroke:#333,stroke-width:2px
    style F fill:#fff,stroke:#333,stroke-width:2px
    style H fill:#fff,stroke:#333,stroke-width:2px

```
