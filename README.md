# first-repository-on-github
# xyz
better change  
<br>
...
<br>
!!!

graph TB
    subgraph "Frontend Applications"
        TA[Tenant App]
        OA[Owner App]
    end

    subgraph "Backend Services"
        API[API Gateway]
        AS[Authentication Service]
        PS[Property Service]
        BS[Booking Service]
        FS[Financial Service]
        IS[Issue Management Service]
        RS[Rating Service]
        NS[Notification Service]
    end

    subgraph "Data Storage"
        DB[(Main Database)]
        Cache[(Cache)]
    end

    subgraph "External Services"
        PS[Payment Service]
        MPS[Map Service]
    end

    TA --> API
    OA --> API
    API --> AS
    API --> PS
    API --> BS
    API --> FS
    API --> IS
    API --> RS
    API --> NS

    PS --> DB
    BS --> DB
    FS --> DB
    IS --> DB
    RS --> DB

    PS --> Cache
    BS --> Cache

    BS --> PS
    FS --> PS
    
    PS --> MPS

    subgraph "Real-time Communication"
        WS[WebSocket Server]
    end

    TA --> WS
    OA --> WS
    WS --> NS
