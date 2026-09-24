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
# ISP Learning Roadmap

> **From Photons to Pixels** - A comprehensive journey through the modern camera Image Signal Processing pipeline.

<p align="center">
  <img src="https://img.shields.io/badge/Modules-15-6366f1?style=for-the-badge" alt="Modules"/>
  <img src="https://img.shields.io/badge/Level-Beginner%20to%20Expert-10b981?style=for-the-badge" alt="Level"/>
  <img src="https://img.shields.io/badge/Topics-Physics%20%7C%20ISP%20%7C%20AI-ec4899?style=for-the-badge" alt="Topics"/>
</p>

---

## Roadmap Overview

```mermaid
flowchart TD
    subgraph L1["Layer 1 - Physics Foundation"]
        P01["01 Photon and\nImaging Physics"]
        P02["02 CMOS\nImage Sensor"]
    end

    subgraph L2["Layer 2 - Sensor Data"]
        P03["03 RAW Image"]
        P04["04 Bayer CFA"]
    end

    subgraph L3["Layer 3 - ISP Pipeline Hub"]
        P05["05 ISP Pipeline\n--- Central Hub ---"]
    end

    subgraph L4A["Layer 4A - 3A Algorithms"]
        P06["06 Auto\nExposure"]
        P07["07 Auto\nWhite Balance"]
        P08["08 Auto\nFocus"]
    end

    subgraph L4B["Layer 4B - Core Processing Stages"]
        P10["10 Demosaicing"]
        P11["11 Denoising"]
        P12["12 Color\nCorrection"]
        P13["13 Tone\nMapping"]
    end

    subgraph L5["Layer 5 - Dynamic Range"]
        P09["09 HDR"]
    end

    subgraph L6["Layer 6 - Next Generation"]
        P14["14 Computational\nPhotography"]
        P15["15 AI ISP\n--- Frontier ---"]
    end

    P01 ==> P02
    P02 ==> P03
    P02 ==> P04

    P03 ==> P05
    P04 -.-> P05

    P05 ==> P06
    P05 ==> P07
    P05 ==> P08
    P05 ==> P10

    P04 ==> P10
    P10 --> P11
    P11 --> P12
    P12 --> P13

    P06 -.-> P09
    P07 -.-> P12
    P09 ==> P13

    P13 ==> P14
    P13 ==> P15
    P10 -.-> P15
    P11 -.-> P15
    P14 -.-> P15

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

    style L1 fill:none,stroke:#6366f1,stroke-width:2px,stroke-dasharray:5 5
    style L2 fill:none,stroke:#06b6d4,stroke-width:2px,stroke-dasharray:5 5
    style L3 fill:none,stroke:#10b981,stroke-width:2px,stroke-dasharray:5 5
    style L4A fill:none,stroke:#f59e0b,stroke-width:2px,stroke-dasharray:5 5
    style L4B fill:none,stroke:#10b981,stroke-width:2px,stroke-dasharray:5 5
    style L5 fill:none,stroke:#ec4899,stroke-width:2px,stroke-dasharray:5 5
    style L6 fill:none,stroke:#8b5cf6,stroke-width:2px,stroke-dasharray:5 5
```

### Connection Legend

| Line Style | Meaning |
| --- | --- |
| **Solid thick arrow** `==>` | Primary data flow |
| **Solid thin arrow** `-->` | Sequential processing |
| **Dashed arrow** `-.->` | Feedback / influence |

---

## Module Details

| #   | Module | Category | Description | Prerequisites |
| --- | --- | --- | --- | --- |
| 01  | **Photon & Imaging Physics** | Physics | Light properties, photoelectric effect, radiometry, imaging optics | -   |
| 02  | **CMOS Image Sensor** | Sensor | Pixel structure, photoelectric conversion, readout circuits, noise model | 01  |
| 03  | **RAW Image** | Sensor | Raw sensor data, bit depth, black level correction, linearization | 02  |
| 04  | **Bayer CFA** | Sensor | RGGB color filter array, spatial sampling, spectral aliasing | 02  |
| 05  | **ISP Pipeline** | Pipeline | Full signal processing chain: RAW to RGB to YUV | 03, 04 |
| 06  | **Auto Exposure** | 3A  | Exposure control strategy, histogram analysis, gain/shutter adjustment | 05  |
| 07  | **Auto White Balance** | 3A  | Color temperature estimation, gray world assumption, illuminant classification | 05  |
| 08  | **Auto Focus** | 3A  | Focus search algorithms, PDAF / CDAF, contrast detection | 05  |
| 09  | **HDR** | Advanced | Multi-frame exposure fusion, ghost removal, dynamic range extension | 06  |
| 10  | **Demosaicing** | Pipeline | Bayer interpolation to full-color image, edge-directed, false color suppression | 04, 05 |
| 11  | **Denoising** | Pipeline | Spatial / temporal denoising, BM3D, NLM, bilateral filtering | 10  |
| 12  | **Color Correction** | Pipeline | CCM color correction matrix, color space conversion, gamma correction | 07, 11 |
| 13  | **Tone Mapping** | Pipeline | Global / local tone mapping, Reinhard, ACES curve | 09, 12 |
| 14  | **Computational Photography** | Advanced | Super resolution, night mode, depth simulation, panorama stitching | 13  |
| 15  | **AI ISP** | AI  | End-to-end neural network ISP, learned demosaicing / denoising | 10, 11, 14 |

---

## Suggested Learning Path

```
Stage 1 - Foundations         01 -> 02 -> 03 -> 04
    Understand light, sensors, RAW data formats

Stage 2 - Core Pipeline       05 -> 10 -> 11 -> 12 -> 13
    Master the ISP chain: Demosaic -> Denoise -> CCM -> Tone Mapping

Stage 3 - 3A Control          06 -> 07 -> 08
    Learn auto exposure, white balance, and focus algorithms

Stage 4 - Advanced            09 -> 14
    HDR high dynamic range, computational photography

Stage 5 - Frontier            15
    AI-driven end-to-end image signal processing
```

---

<p align="center">
  <b>Star this repo if it helps your learning journey!</b><br/>
  <sub>Contributions welcome - Open an issue to suggest improvements</sub>
</p>
