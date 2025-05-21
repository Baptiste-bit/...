graph LR
    %% 主体层
    subgraph 参与主体
        A[NNPC<br>（尼日利亚国家石油公司）]:::entity
        B[CCOC<br>（石油采购方）]:::entity
        C[COVEC<br>（承包商）]:::entity
        D[尼日利亚交通部<br>（监管方）]:::entity
    end

    %% 流程层
    A -->|1. 石油销售| B
    B -->|2. 结算款支付| C
    C -->|3. 设立专用账户| E((项目专用账户)):::fund
    E -->|4. 资金用于EPC施工| F[施工方]:::entity

    %% 协议层
    D -->|5. 签署<br>三方协议| C
    A -->|5. 签署<br>三方协议| C

    %% 样式优化
    classDef entity fill:#007BFF,stroke:#fff,stroke-width:2px,color:white,rounded:yes,font-weight:bold
    classDef fund fill:#FFD700,stroke:#000,stroke-width:1px,shadow:3px,font-style:italic
    classDef process fill:#E0F3FF,stroke:#007BFF,stroke-width:1px,color:#333,rounded:yes
    linkStyle default stroke:#007BFF,stroke-width:2px,arrowhead=vee,arrowtail=open

    %% 注释标注
    note1[石油实物流]:::process --> A --> B
    note2[资金流]:::process --> B --> C --> E --> F
    note3[协议约束]:::process --> D & A --> C
