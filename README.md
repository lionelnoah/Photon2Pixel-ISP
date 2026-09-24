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

# 📷 ISP Learning Roadmap

> **From Photons to Pixels** — A comprehensive journey through the modern camera Image Signal Processing pipeline.

<p align="center">
  <img src="https://img.shields.io/badge/Modules-15-6366f1?style=for-the-badge&logo=bookstack&logoColor=white" alt="Modules"/>
  <img src="https://img.shields.io/badge/Level-Beginner%20→%20Expert-10b981?style=for-the-badge&logo=target&logoColor=white" alt="Level"/>
  <img src="https://img.shields.io/badge/Topics-Physics%20|%20ISP%20|%20AI-ec4899?style=for-the-badge&logo=camera&logoColor=white" alt="Topics"/>
</p>

---

## 🗺️ Roadmap Overview

```mermaid
%%{init: {'theme': 'base', 'themeVariables': {'primaryColor': '#6366f1', 'primaryTextColor': '#fff', 'primaryBorderColor': '#4f46e5', 'lineColor': '#94a3b8', 'secondaryColor': '#06b6d4', 'tertiaryColor': '#10b981', 'fontSize': '14px'}}}%%

flowchart TD
    %% ──────── Layer 1: Physics Foundation ────────
    subgraph L1["🔬 Layer 1 · Physics Foundation"]
        direction LR
        P01["🔬 01 Photon &<br/>Imaging Physics"]
        P02["📡 02 CMOS<br/>Image Sensor"]
    end

    %% ──────── Layer 2: Sensor Data ────────
    subgraph L2["📸 Layer 2 · Sensor Data"]
        direction LR
        P03["📸 03 RAW Image"]
        P04["🟩 04 Bayer CFA"]
    end

    %% ──────── Layer 3: ISP Pipeline Hub ────────
    subgraph L3["⚙️ Layer 3 · ISP Pipeline Hub"]
        P05["⚙️ 05 ISP Pipeline<br/>━━━━━━━━━━━<br/>🔗 Central Processing Hub"]
    end

    %% ──────── Layer 4A: 3A Algorithms ────────
    subgraph L4A["☀️ Layer 4A · 3A Algorithms"]
        direction LR
        P06["☀️ 06 Auto<br/>Exposure"]
        P07["🎨 07 Auto<br/>White Balance"]
        P08["🎯 08 Auto<br/>Focus"]
    end

    %% ──────── Layer 4B: Core Processing ────────
    subgraph L4B["🧩 Layer 4B · Core Processing Stages"]
        direction LR
        P10["🧩 10 Demosaicing"] --> P11["✨ 11 Denoising"]
        P11 --> P12["🌈 12 Color<br/>Correction"]
        P12 --> P13["🎛️ 13 Tone<br/>Mapping"]
    end

    %% ──────── Layer 5: Advanced ────────
    subgraph L5["🌅 Layer 5 · Dynamic Range"]
        P09["🌅 09 HDR"]
    end

    %% ──────── Layer 6: Next Gen ────────
    subgraph L6["🤖 Layer 6 · Next Generation"]
        direction LR
        P14["📐 14 Computational<br/>Photography"]
        P15["🤖 15 AI ISP<br/>━━━━━━━━━<br/>🔥 Frontier"]
    end

    %% ──────── CONNECTIONS ────────
    %% Foundation flow
    P01 ==>|"光电效应"| P02
    P02 ==>|"传感器输出"| P03
    P02 ==>|"滤色器"| P04

    %% Into ISP
    P03 ==>|"原始数据"| P05
    P04 -.->|"CFA Pattern"| P05

    %% ISP branches
    P05 ==>|"控制反馈"| L4A
    P05 ==>|"图像处理"| P10

    %% 3A feedback
    P06 -.->|"曝光控制"| P09
    P07 -.->|"白平衡增益"| P12

    %% Bayer → Demosaic
    P04 ==>|"马赛克数据"| P10

    %% HDR connection
    P09 ==>|"HDR 合成"| P13

    %% Output to Next Gen
    P13 ==>|"最终输出"| P14
    P13 ==>|"传统 Pipeline"| P15

    %% AI replaces traditional
    P10 -.->|"AI 替代"| P15
    P11 -.->|"AI 替代"| P15
    P14 -.->|"融合演进"| P15

    %% ──────── STYLING ────────
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

## 📋 Module Details

| # | Module | Category | Description | Prerequisites |
|:---:|:---|:---:|:---|:---:|
| 01 | **Photon & Imaging Physics** | 🔬 Physics | 光子特性、光电效应、辐射度量学、成像光学基础 | — |
| 02 | **CMOS Image Sensor** | 📡 Sensor | 像素结构、光电转换、读出电路、噪声模型 | 01 |
| 03 | **RAW Image** | 📸 Sensor | 传感器原始数据、位深度、黑电平校正、线性化 | 02 |
| 04 | **Bayer CFA** | 🟩 Sensor | RGGB 色彩滤波阵列、空间采样、频谱混叠 | 02 |
| 05 | **ISP Pipeline** | ⚙️ Pipeline | 完整信号处理链路：RAW → RGB → YUV，串联所有模块 | 03, 04 |
| 06 | **Auto Exposure** | ☀️ 3A | 曝光控制策略、直方图分析、增益/快门调节 | 05 |
| 07 | **Auto White Balance** | 🎨 3A | 色温估计、灰世界假设、完美反射、光源分类 | 05 |
| 08 | **Auto Focus** | 🎯 3A | 对焦搜索算法、PDAF / CDAF、对比度检测 | 05 |
| 09 | **HDR** | 🌅 Advanced | 多帧曝光融合、Ghost 去除、动态范围扩展 | 06 |
| 10 | **Demosaicing** | 🧩 Pipeline | Bayer 插值重建全彩图像、边缘导向、伪彩抑制 | 04, 05 |
| 11 | **Denoising** | ✨ Pipeline | 空域 / 时域降噪、BM3D、NLM、双边滤波 | 10 |
| 12 | **Color Correction** | 🌈 Pipeline | CCM 色彩校正矩阵、色彩空间转换、Gamma 校正 | 07, 11 |
| 13 | **Tone Mapping** | 🎛️ Pipeline | 全局 / 局部色调映射、Reinhard、ACES 曲线 | 09, 12 |
| 14 | **Computational Photography** | 📐 Advanced | 超分辨率、夜景模式、景深模拟、全景拼接 | 13 |
| 15 | **AI ISP** | 🤖 AI | 端到端神经网络 ISP、learned demosaicing / denoising | 10, 11, 14 |

---

## 🛤️ Suggested Learning Path

```
 ╔══════════════════════════════════════════════════════════════╗
 ║                    🎓 LEARNING STAGES                        ║
 ╠══════════════════════════════════════════════════════════════╣
 ║                                                              ║
 ║  Stage 1 ·  Foundations        01 → 02 → 03 → 04             ║
 ║  ─────────────────────────────────────────────               ║
 ║  理解光的本质、传感器工作原理、RAW 数据格式                   ║
 ║                                                              ║
 ║  Stage 2 ·  Core Pipeline      05 → 10 → 11 → 12 → 13        ║
 ║  ─────────────────────────────────────────────               ║
 ║  掌握 ISP 主处理链路：去马赛克 → 降噪 → 色彩校正 → 色调映射   ║
 ║                                                              ║
 ║  Stage 3 ·  3A Control         06 → 07 → 08                  ║
 ║  ─────────────────────────────────────────────               ║
 ║  学习自动曝光、白平衡、对焦的控制算法                         ║
 ║                                                              ║
 ║  Stage 4 ·  Advanced           09 → 14                       ║
 ║  ─────────────────────────────────────────────               ║
 ║  HDR 高动态范围、计算摄影前沿技术                             ║
 ║                                                              ║
 ║  Stage 5 ·  Frontier           15                            ║
 ║  ─────────────────────────────────────────────               ║
 ║  AI 驱动的端到端图像信号处理                                  ║
 ║                                                              ║
 ╚══════════════════════════════════════════════════════════════╝
```

---

<p align="center">
  <b>⭐ Star this repo if it helps your learning journey!</b><br/>
  <sub>Contributions welcome · Open an issue to suggest improvements</sub>
</p>
