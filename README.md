graph TD
    %% 能源贸易层
    subgraph 能源贸易层
    A1[NNPC] -->|石油销售合同| B1[CCOC]
    B1 -.->|L/C/DLC支付| B2[国际银行]
    end

    %% 资金监管层
    subgraph 资金监管层
    B1 -->|不可撤销付款指令| C1[COVEC]
    C1 -->|设立监管账户| C2[项目专用账户<br>（独立托管）]
    C2 -.->|资金释放审批| C3[三方协调委员会]
    C3 -.->|尼日利亚交通部核准| C4[交通部]
    end

    %% 工程实施层
    subgraph 工程实施层
    C1 -->|EPC总承包协议| D1[石油基建项目]
    D1 -.->|进度验收| D2[监理工程师]
    D2 -.->|支付证书| C3
    end

    %% 高级样式定义
    style A1 fill:#2A5CAA,stroke:#1A3659
    style B1 fill:#4ECDC4,stroke:#1A3659
    style C1 fill:#FF6B6B,stroke:#1A3659
    style C2 fill:#FFD700,stroke:#FFA500
    style C3 fill:#9B59B6,stroke:#1A3659
    style C4 fill:#2C3E50,stroke:#1A3659

    %% 动态注释
    C2:::flow -->|资金流向| C1:::contract
    C3:::flow -.->|监管条件| C2
