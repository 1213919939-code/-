graph TD
    %% 顶部输入 (PA 路径)
    PA[<b>棕榈酸 PA</b>] --> TLR4[TLR4 组分]
    PA --> CD36[CD36 受体/转运体]

    %% 脂代谢路径 (Section III)
    subgraph Lipid_Path [脂代谢与氧化应激放大器]
    CD36 --> Beta_Ox[β-氧化]
    Beta_Ox --> ROS[产生 ROS]
    ROS -- "+" --> SRC[SRC 激酶家族 <br/>Fyn / Lyn]
    end

    %% 核心激活路径 (Section I)
    TLR4 --> SRC
    CD36 --> SRC
    SRC -- "+" --> BCAR1[<b>BCAR1 / p130Cas</b>]

    %% 下游效应 (Visual Diagram)
    subgraph Downstream [下游炎症信号转导]
    BCAR1 --> TRAF6[TRAF6]
    TRAF6 --> TAK1_IKB[TAK1 / IKB]
    TAK1_IKB --> P65(((p65 / NF-κB)))
    end

    %% *关键调节机制* (Section II) - 替换为毛蕊异黄酮
    subgraph Regulation [毛蕊异黄酮代谢调节器]
    Calycosin[<b>毛蕊异黄酮<br/>Calycosin</b>] -- "+" --> AMPK[AMPK 激活]
    AMPK -- "-" --> CD36_FASN[CD36 / FASN]
    CD36_FASN -. 抑制下调 .-> BCAR1
    end

    %% 样式美化
    style PA fill:#f96,stroke:#333,stroke-width:2px,color:white
    style Calycosin fill:#ff9,stroke:#333,stroke-width:2px
    style BCAR1 fill:#69f,stroke:#333,stroke-width:2px,color:white
    style P65 fill:#f66,stroke:#333,stroke-width:2px,color:white
    style Regulation fill:#eee,stroke-dasharray: 5 5# -
