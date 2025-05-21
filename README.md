%% 铁路项目石油资金联动架构（Mermaid代码）
graph TD
    subgraph 石油贸易层
    A1[NNPC] -->|长期销售协议<br>（FOB条款）| B1[CCOC]
    B1 -.->|L/C支付<br>（CBN 204指令）| B2[渣打银行伦敦分行]
    end

    subgraph 资金监管层
    B1 -->|不可撤销付款指令| C1[COVEC]
    C1 -->|设立监管账户| C2[项目专用账户<br>（渣打银行+区块链存证）]
    C2 -.->|资金释放审批| C3[三方协调委员会]
    C3 -.->|交通部核准| C4[FMOT]
    end

    subgraph 项目实施层
    C1 -->|EPC总承包协议<br>（FIDIC红皮书）| D1[铁路基建项目]
    D1 -.->|进度验收| D2[独立工程师]
    D2 -.->|支付证书| C3
    end

    subgraph 合规支持层
    C2 -.->|反洗钱审查| R1[EFCC]
    C3 -.->|环境评估| R2[NESREA]
    C4 -.->|外汇申报| R3[CBN]
    end
