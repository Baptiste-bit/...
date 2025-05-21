graph TD
    %% Core Components
    subgraph Upstream[Upstream Layer]
        A1[NNPC] -->|Sales Agreement| B1[CCOC]
        B1 -.->|L/C/DLC| B2[International Bank]
        style A1 fill:#2A5CAA,stroke:#1A3659
        style B1 fill:#4ECDC4,stroke:#1A3659
    end

    subgraph Midstream[Midstream Layer]
        B1 -->|Irrevocable Payment Instruction| C1[COVEC]
        C1 -->|Escrow Account Setup| C2[Project Escrow Account<br> (Independent Custody)]
        C2 -.->|Disbursement Approval| C3[Joint Steering Committee]
        C3 -.->|Regulatory Clearance| C4[Nigeria Ministry of Transport]
        style C1 fill:#FF6B6B,stroke:#1A3659
        style C2 fill:#FFD700,stroke:#FFA500
    end

    subgraph Downstream[Downstream Layer]
        C1 -->|EPC Contract| D1[Petroleum Infrastructure Project]
        D1 -.->|Progress Certification| D2[Independent Engineer]
        D2 -.->|Payment Release| C3
        style D1 fill:#9B59B6,stroke:#1A3659
        style D2 fill:#2C3E50,stroke:#1A3659
    end

    %% Enhanced Styling
    classDef process fill:#F8F9FA,stroke:#6C757D,stroke-width:2px;
    classDef decision fill:#FFF3E0,stroke:#FD7E14,stroke-width:2px;
    classDef system fill:#E3F2FD,stroke:#2196F3,stroke-width:2px;

    %% Compliance Annotations
    C3 -.->|Regulatory Requirements| R1[NEITI Act 2007]
    C4 -.->|Approval Workflow| R2[Federal Inland Revenue Service]
    style R1 fill:#FFEBEE,stroke:#E57373
    style R2 fill:#FCE4EC,stroke:#EF5350

    %% Technical Specifications
    %% Payment Triggers
    D2 -.->|Certification Criteria| TC1[ASME B31.3]
    D2 -.->|Documentation| TC2[ISO 10209]
    style TC1 fill:#E8F5E9,stroke:#4CAF50
    style TC2 fill:#E3F2FD,stroke:#2196F3

    %% Risk Controls
    C2 -.->|Escrow Conditions| RC1[Performance Bond]
    C2 -.->|Force Majeure| RC2[World Bank Guidelines]
    style RC1 fill:#F0F4C3,stroke:#AFB42B
    style RC2 fill:#FCE4EC,stroke:#EF5350
