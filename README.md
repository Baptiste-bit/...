%% 优化后交易架构（Mermaid代码）
graph TD
    subgraph 能源贸易层
    A1[NNPC] -->|原油销售合同<br>（FOB条款）| B1[CCOC]
    B1 -.->|L/C支付<br>（CBN 204指令）| B2[花旗银行拉各斯分行]
    end

    subgraph 资金监管层
    B1 -->|不可撤销付款指令| C1[COVEC]
    C1 -->|设立监管账户| C2[项目专用账户<br>（渣打银行+区块链存证）]
    C2 -.->|资金释放审批| C3[三方协调委员会]
    C3 -.->|交通部核准| C4[交通部]
    end

    subgraph 工程实施层
    C1 -->|EPC总承包协议<br>（FIDIC红皮书）| D1[石油基建项目]
    D1 -.->|进度验收| D2[独立工程师]
    D2 -.->|支付证书| C3
    end

    %% 新增合规模块
    subgraph 合规控制
    C2 -.->|反洗钱审查| R1[EFCC]
    C3 -.->|环境评估| R2[NESREA]
    C4 -.->|外汇申报| R3[CBN]
    end

    %% 风险控制增强
    C2 -->|支付限额| RL1[单笔≤500万美元]
    C2 -->|资金归集| RL2[每月15日强制回流]
    style RL1 fill:#FFD700,stroke:#FFA500
    style RL2 fill:#9B59B6,stroke:#1A3659
