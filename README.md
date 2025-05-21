graph TD  
    subgraph 能源贸易层  
    NNPC((NNPC)) -->|销售协议| CCOC((CCOC))  
    CCOC -.->|L/C支付| Bank1[国际银行]  
    end  
  
    subgraph 资金监管层  
    CCOC -.->|不可撤销指令| COVEC((COVEC))  
    COVEC -->|设立监管账户| Account[项目专用账户<br>（独立托管）]  
    Account -.->|资金释放审批| JointCommittee[三方协调委员会]  
    JointCommittee -.->|交通部核准| Ministry[交通部]  
    end  
  
    subgraph 工程实施层  
    COVEC -->|EPC协议| Project[石油基建项目]  
    Project -.->|进度验收| Engineer[监理工程师]  
    Engineer -.->|支付证书| JointCommittee  
    end  
  
    %% 高级样式定义  
    style NNPC fill:#2A5CAA,stroke:#1A3659  
    style CCOC fill:#4ECDC4,stroke:#1A3659  
    style COVEC fill:#FF6B6B,stroke:#1A3659  
    style Account fill:#FFD700,stroke:#1A3659  
    style JointCommittee fill:#9B59B6,stroke:#1A3659  
    style Ministry fill:#2C3E50,stroke:#1A3659  
  
    %% 交互注释  
    Account:::flow -->|资金流向| COVEC:::contract  
    JointCommittee:::flow -.->|监管条件| Account  
