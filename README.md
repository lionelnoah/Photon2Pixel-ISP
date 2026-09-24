# Photon2Pixel-ISP
From Photon to Pixel.

Photon2Pixel is a long-term project for studying and implementing the complete imaging pipeline:

Photon
→ Optics
→ CMOS Sensor
→ RAW
→ ISP
→ Computational Photography
→ AI ISP
→ RGB Image
# 馃摲 ISP Learning Roadmap

> **From Photons to Pixels** 鈥?A comprehensive journey through the modern camera Image Signal Processing pipeline.

<p align="center">
  <img src="https://img.shields.io/badge/Modules-15-6366f1?style=for-the-badge&logo=bookstack&logoColor=white" alt="Modules"/>
  <img src="https://img.shields.io/badge/Level-Beginner%20鈫?20Expert-10b981?style=for-the-badge&logo=target&logoColor=white" alt="Level"/>
  <img src="https://img.shields.io/badge/Topics-Physics%20|%20ISP%20|%20AI-ec4899?style=for-the-badge&logo=camera&logoColor=white" alt="Topics"/>
</p>

---

## 馃椇锔?Roadmap Overview

```mermaid
%%{init: {'theme': 'base', 'themeVariables': {'primaryColor': '#6366f1', 'primaryTextColor': '#fff', 'primaryBorderColor': '#4f46e5', 'lineColor': '#94a3b8', 'secondaryColor': '#06b6d4', 'tertiaryColor': '#10b981', 'fontSize': '14px'}}}%%

flowchart TD
    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ Layer 1: Physics Foundation 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    subgraph L1["馃敩 Layer 1 路 Physics Foundation"]
        direction LR
        P01["馃敩 01 Photon &<br/>Imaging Physics"]
        P02["馃摗 02 CMOS<br/>Image Sensor"]
    end

    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ Layer 2: Sensor Data 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    subgraph L2["馃摳 Layer 2 路 Sensor Data"]
        direction LR
        P03["馃摳 03 RAW Image"]
        P04["馃煩 04 Bayer CFA"]
    end

    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ Layer 3: ISP Pipeline Hub 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    subgraph L3["鈿欙笍 Layer 3 路 ISP Pipeline Hub"]
        P05["鈿欙笍 05 ISP Pipeline<br/>鈹佲攣鈹佲攣鈹佲攣鈹佲攣鈹佲攣鈹?br/>馃敆 Central Processing Hub"]
    end

    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ Layer 4A: 3A Algorithms 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    subgraph L4A["鈽€锔?Layer 4A 路 3A Algorithms"]
        direction LR
        P06["鈽€锔?06 Auto<br/>Exposure"]
        P07["馃帹 07 Auto<br/>White Balance"]
        P08["馃幆 08 Auto<br/>Focus"]
    end

    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ Layer 4B: Core Processing 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    subgraph L4B["馃З Layer 4B 路 Core Processing Stages"]
        direction LR
        P10["馃З 10 Demosaicing"] --> P11["鉁?11 Denoising"]
        P11 --> P12["馃寛 12 Color<br/>Correction"]
        P12 --> P13["馃帥锔?13 Tone<br/>Mapping"]
    end

    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ Layer 5: Advanced 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    subgraph L5["馃寘 Layer 5 路 Dynamic Range"]
        P09["馃寘 09 HDR"]
    end

    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ Layer 6: Next Gen 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    subgraph L6["馃 Layer 6 路 Next Generation"]
        direction LR
        P14["馃搻 14 Computational<br/>Photography"]
        P15["馃 15 AI ISP<br/>鈹佲攣鈹佲攣鈹佲攣鈹佲攣鈹?br/>馃敟 Frontier"]
    end

    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ CONNECTIONS 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    %% Foundation flow
    P01 ==>|"鍏夌數鏁堝簲"| P02
    P02 ==>|"浼犳劅鍣ㄨ緭鍑?| P03
    P02 ==>|"婊よ壊鍣?| P04

    %% Into ISP
    P03 ==>|"鍘熷鏁版嵁"| P05
    P04 -.->|"CFA Pattern"| P05

    %% ISP branches
    P05 ==>|"鎺у埗鍙嶉"| L4A
    P05 ==>|"鍥惧儚澶勭悊"| P10

    %% 3A feedback
    P06 -.->|"鏇濆厜鎺у埗"| P09
    P07 -.->|"鐧藉钩琛″鐩?| P12

    %% Bayer 鈫?Demosaic
    P04 ==>|"椹禌鍏嬫暟鎹?| P10

    %% HDR connection
    P09 ==>|"HDR 鍚堟垚"| P13

    %% Output to Next Gen
    P13 ==>|"鏈€缁堣緭鍑?| P14
    P13 ==>|"浼犵粺 Pipeline"| P15

    %% AI replaces traditional
    P10 -.->|"AI 鏇夸唬"| P15
    P11 -.->|"AI 鏇夸唬"| P15
    P14 -.->|"铻嶅悎婕旇繘"| P15

    %% 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€ STYLING 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€
    classDef physics fill:#6366f1,stroke:#4f46e5,color:#fff,stroke-width:2px
    classDef sensor fill:#06b6d4,stroke:#0891b2,color:#fff,stroke-width:2px
    classDef threeA fill:#f59e0b,stroke:#d97706,color:#fff,stroke-width:2px
    classDef pipeline fill:#10b981,stroke:#059669,color:#fff,stroke-width:2px
    classDef advanced fill:#ec4899,stroke:#db2777,color:#fff,stroke-width:2px
    classDef ai fill:#8b5cf6,stroke:#7c3aed,color:#fff,stroke-width:3px
    classDef hub fill:#10b981,stroke:#059669,color:#fff,stroke-width:3px

    class P01 physics
    class P02 sensor
    class P03,P04 sensor
    class P05 hub
    class P06,P07,P08 threeA
    class P09 advanced
    class P10,P11,P12,P13 pipeline
    class P14 advanced
    class P15 ai

    style L1 fill:transparent,stroke:#6366f1,stroke-width:2px,stroke-dasharray:5 5,color:#6366f1
    style L2 fill:transparent,stroke:#06b6d4,stroke-width:2px,stroke-dasharray:5 5,color:#06b6d4
    style L3 fill:transparent,stroke:#10b981,stroke-width:2px,stroke-dasharray:5 5,color:#10b981
    style L4A fill:transparent,stroke:#f59e0b,stroke-width:2px,stroke-dasharray:5 5,color:#f59e0b
    style L4B fill:transparent,stroke:#10b981,stroke-width:2px,stroke-dasharray:5 5,color:#10b981
    style L5 fill:transparent,stroke:#ec4899,stroke-width:2px,stroke-dasharray:5 5,color:#ec4899
    style L6 fill:transparent,stroke:#8b5cf6,stroke-width:2px,stroke-dasharray:5 5,color:#8b5cf6
```

---

## 馃搵 Module Details

| #   | Module                        | Category     | Description                                 | Prerequisites |
|:---:|:----------------------------- |:------------:|:------------------------------------------- |:-------------:|
| 01  | **Photon & Imaging Physics**  | 馃敩 Physics   | 鍏夊瓙鐗规€с€佸厜鐢垫晥搴斻€佽緪灏勫害閲忓銆佹垚鍍忓厜瀛﹀熀纭€                      | 鈥?            |
| 02  | **CMOS Image Sensor**         | 馃摗 Sensor    | 鍍忕礌缁撴瀯銆佸厜鐢佃浆鎹€佽鍑虹數璺€佸櫔澹版ā鍨?                        | 01            |
| 03  | **RAW Image**                 | 馃摳 Sensor    | 浼犳劅鍣ㄥ師濮嬫暟鎹€佷綅娣卞害銆侀粦鐢靛钩鏍℃銆佺嚎鎬у寲                       | 02            |
| 04  | **Bayer CFA**                 | 馃煩 Sensor    | RGGB 鑹插僵婊ゆ尝闃靛垪銆佺┖闂撮噰鏍枫€侀璋辨贩鍙?                      | 02            |
| 05  | **ISP Pipeline**              | 鈿欙笍 Pipeline  | 瀹屾暣淇″彿澶勭悊閾捐矾锛歊AW 鈫?RGB 鈫?YUV锛屼覆鑱旀墍鏈夋ā鍧?            | 03, 04        |
| 06  | **Auto Exposure**             | 鈽€锔?3A        | 鏇濆厜鎺у埗绛栫暐銆佺洿鏂瑰浘鍒嗘瀽銆佸鐩?蹇棬璋冭妭                        | 05            |
| 07  | **Auto White Balance**        | 馃帹 3A        | 鑹叉俯浼拌銆佺伆涓栫晫鍋囪銆佸畬缇庡弽灏勩€佸厜婧愬垎绫?                       | 05            |
| 08  | **Auto Focus**                | 馃幆 3A        | 瀵圭劍鎼滅储绠楁硶銆丳DAF / CDAF銆佸姣斿害妫€娴?                   | 05            |
| 09  | **HDR**                       | 馃寘 Advanced  | 澶氬抚鏇濆厜铻嶅悎銆丟host 鍘婚櫎銆佸姩鎬佽寖鍥存墿灞?                     | 06            |
| 10  | **Demosaicing**               | 馃З Pipeline  | Bayer 鎻掑€奸噸寤哄叏褰╁浘鍍忋€佽竟缂樺鍚戙€佷吉褰╂姂鍒?                   | 04, 05        |
| 11  | **Denoising**                 | 鉁?Pipeline   | 绌哄煙 / 鏃跺煙闄嶅櫔銆丅M3D銆丯LM銆佸弻杈规护娉?                    | 10            |
| 12  | **Color Correction**          | 馃寛 Pipeline  | CCM 鑹插僵鏍℃鐭╅樀銆佽壊褰╃┖闂磋浆鎹€丟amma 鏍℃                  | 07, 11        |
| 13  | **Tone Mapping**              | 馃帥锔?Pipeline | 鍏ㄥ眬 / 灞€閮ㄨ壊璋冩槧灏勩€丷einhard銆丄CES 鏇茬嚎                | 09, 12        |
| 14  | **Computational Photography** | 馃搻 Advanced  | 瓒呭垎杈ㄧ巼銆佸鏅ā寮忋€佹櫙娣辨ā鎷熴€佸叏鏅嫾鎺?                        | 13            |
| 15  | **AI ISP**                    | 馃 AI        | 绔埌绔缁忕綉缁?ISP銆乴earned demosaicing / denoising | 10, 11, 14    |

---

## 馃洡锔?Suggested Learning Path

```
 鈺斺晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晽
 鈺?                   馃帗 LEARNING STAGES                       鈺? 鈺犫晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨暎
 鈺?                                                             鈺? 鈺? Stage 1 路  Foundations        01 鈫?02 鈫?03 鈫?04            鈺? 鈺? 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€               鈺? 鈺? 鐞嗚В鍏夌殑鏈川銆佷紶鎰熷櫒宸ヤ綔鍘熺悊銆丷AW 鏁版嵁鏍煎紡                       鈺? 鈺?                                                             鈺? 鈺? Stage 2 路  Core Pipeline      05 鈫?10 鈫?11 鈫?12 鈫?13      鈺? 鈺? 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€               鈺? 鈺? 鎺屾彙 ISP 涓诲鐞嗛摼璺細鍘婚┈璧涘厠 鈫?闄嶅櫔 鈫?鑹插僵鏍℃ 鈫?鑹茶皟鏄犲皠       鈺? 鈺?                                                             鈺? 鈺? Stage 3 路  3A Control         06 鈫?07 鈫?08                 鈺? 鈺? 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€               鈺? 鈺? 瀛︿範鑷姩鏇濆厜銆佺櫧骞宠　銆佸鐒︾殑鎺у埗绠楁硶                             鈺? 鈺?                                                             鈺? 鈺? Stage 4 路  Advanced           09 鈫?14                      鈺? 鈺? 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€               鈺? 鈺? HDR 楂樺姩鎬佽寖鍥淬€佽绠楁憚褰卞墠娌挎妧鏈?                               鈺? 鈺?                                                             鈺? 鈺? Stage 5 路  Frontier           15                            鈺? 鈺? 鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€鈹€               鈺? 鈺? AI 椹卞姩鐨勭鍒扮鍥惧儚淇″彿澶勭悊                                    鈺? 鈺?                                                             鈺? 鈺氣晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨晲鈺愨暆
```

---

<p align="center">
  <b>猸?Star this repo if it helps your learning journey!</b><br/>
  <sub>Contributions welcome 路 Open an issue to suggest improvements</sub>
</p>
