```mermaid


%%{init: {'theme': 'neutral'}}%%
graph TD
    subgraph Data Sources
        A[Email Notifications] -->|New Hire/Rehire| B(Workday System)
        B -->|Staff Details Report| C(Apollo PowerBI)
    end

    subgraph Power Automate Flows - Data Ingestion and Conversion
        A -- Parse Email Body --> PA1[Extract Email Data]
        PA1 --> JSON1[Convert to JSON String]
        
        B -- Export & Read Report --> PA2[Process Workday Data]
        PA2 --> JSON2[Convert to JSON String]
        
        C -- Read File --> PA3[Process Spreadsheet Data]
        PA3 --> JSON3[Convert to JSON String]
    end

    subgraph SharePoint Lists - Centralized Storage
        JSON1 --> SP1[SP List: Email New Hires]
        JSON2 --> SP2[SP List: Workday Staff Data]
        JSON3 --> SP3[SP List: External Staff Data]
    end

    subgraph Business Continuity Management Trigger
        BCM_Trigger[BCM Scheduled Check] -->|Initiate Data Review| PA4_Start
    end

    subgraph Power Automate Flow - Data Matching and Analysis
        PA4_Start((Start Matching Flow)) --> PA4[Match Data Flow]
        PA4 -->|Get records from| SP2
        PA4 -->|Get records from| SP1
        PA4 -->|Get records from| SP3
    end

    subgraph Matching Logic
        PA4 --> D{Match Found by ID?}
        D -- Yes --> E[Data Consistent?]
        E -- Yes --> F[Log Successful Match]
        E -- No (Discrepancy) --> G[Flag Discrepancy]
        D -- No (No Match) --> H[Flag New/Unmatched Record]
    end

    subgraph Follow-up and Notifications
        G --> SP4[Any other CAS Processes]
        H --> SP4
        SP4 -- BCM Update processes --> PA5[Send Notification to DOSes for approval? else send to Kairin for Review]
        PA5 --> I[END]
    end

    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#f9f,stroke:#333,stroke-width:2px
    style PA1 fill:#9cf,stroke:#333,stroke-width:2px
    style PA2 fill:#9cf,stroke:#333,stroke-width:2px
    style PA3 fill:#9cf,stroke:#333,stroke-width:2px
    style JSON1 fill:#ffc,stroke:#333,stroke-width:2px
    style JSON2 fill:#ffc,stroke:#333,stroke-width:2px
    style JSON3 fill:#ffc,stroke:#333,stroke-width:2px
    style SP1 fill:#bbf,stroke:#333,stroke-width:2px
    style SP2 fill:#bbf,stroke:#333,stroke-width:2px
    style SP3 fill:#bbf,stroke:#333,stroke-width:2px
    style PA4 fill:#9cf,stroke:#333,stroke-width:2px
    style PA4_Start fill:#ccf,stroke:#333,stroke-width:2px,stroke-dasharray: 5 5
    style BCM_Trigger fill:#ccf,stroke:#333,stroke-width:2px
    style D fill:#fc9,stroke:#333,stroke-width:2px
    style E fill:#fc9,stroke:#333,stroke-width:2px
    style F fill:#afa,stroke:#333,stroke-width:2px
    style G fill:#f99,stroke:#333,stroke-width:2px
    style H fill:#f99,stroke:#333,stroke-width:2px
    style SP4 fill:#bbf,stroke:#333,stroke-width:2px
    style PA5 fill:#9cf,stroke:#333,stroke-width:2px
    style I fill:#ffc,stroke:#333,stroke-width:2px


```
