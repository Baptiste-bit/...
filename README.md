graph TD
    subgraph 能源贸易层
    NNPC((NNPC)) -->|石油销售合同| CCOC((CCOC))
    CCOC -.->|L/C/DLC支付| Bank1[国际银行]
    end

    subgraph 资金监管层
    CCOC -.->|不可撤销付款指令| COVEC((COVEC))
    COVEC -->|设立监管账户| Account[项目专用账户<br>（独立托管）]
    Account -.->|资金释放审批| JointCommittee[三方协调委员会]
    JointCommittee -.->|尼日利亚交通部核准| Ministry[尼日利亚交通部]
    end

    subgraph 工程实施层
    COVEC -->|EPC总承包协议| Project[石油基础设施项目]
    Project -.->|工程进度款申请| Engineer[监理工程师]
    Engineer -.->|支付证书签发| JointCommittee
    end

    style NNPC fill:#4A90E2,stroke:#333
    style CCOC fill:#4ECDC4,stroke:#333
    style COVEC fill:#FF6B6B,stroke:#333
    style Account fill:#FFD93D,stroke:#333
    style JointCommittee fill:#9B59B6,stroke:#333
