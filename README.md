# MultiVeg Dataset

This repository is reserved for the MultiVeg dataset, which is associated with an academic publication.

🚧 Data availability notice 🚧

The dataset is currently under revision for a journal submission and will be made publicly available after the acceptance and publication of the corresponding paper.

- Current status: Repository placeholder
- Planned release: Upon paper publication
- License: To be announced

Please stay tuned.
26.04.18. Changhui Lee


<div align="center">

# MultiVeg: A Very High-Resolution Benchmark for Deep Learning-Based Multi-Class Vegetation Segmentation

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](https://www.genspark.ai/api/files/s/pa3tq0oO)
[![Dataset](https://img.shields.io/badge/Dataset-GitHub-blue)](https://github.com/pang914/MultiVeg)
[![Lab](https://img.shields.io/badge/RSIP-SeoulTech-green)](https://sites.google.com/view/rsip/home)

<!-- Optional: replace with your teaser figure -->
<!-- ![MultiVeg teaser](./assets/multiveg_teaser.png) -->

</div>

---

## Introduction

**MultiVeg** is a very high-resolution satellite benchmark for **multi-class vegetation segmentation**.  
Unlike conventional binary vegetation mapping, MultiVeg distinguishes **Tree** and **Low Vegetation** from **Background**, enabling more detailed urban ecological analysis and vegetation monitoring.

The dataset is built from **KOMPSAT-3 / KOMPSAT-3A** satellite imagery and contains **RGB + NIR** bands, which help separate vegetation from spectrally confusing surfaces such as shadows, asphalt, and dark roofs.

---

## Why MultiVeg

- **Very high spatial resolution**: 0.5 m GSD
- **Multi-class vegetation segmentation**: Background / Tree / Low Vegetation
- **Multi-spectral input**: RGB + NIR
- **Geographic diversity in South Korea**: Seoul, Incheon, and Jeju
- **Expert-annotated benchmark** for deep learning-based semantic segmentation
- **Baseline benchmarking** with CNN- and Transformer-based models

---

## Dataset Overview

| Item | Description |
|---|---|
| Satellite | KOMPSAT-3, KOMPSAT-3A |
| Spatial resolution | 0.5 m |
| Spectral bands | RGB + NIR |
| Acquisition years | 2014–2023 |
| Regions | Seoul, Incheon, Jeju |
| Patch size | 512 × 512 pixels |
| Total patches | 6,677 |
| File format | PNG (8-bit) |
| Classes | 3 |

### Regional Distribution

| Region | # Patches | Ratio |
|---|---:|---:|
| Incheon | 2,859 | 42.8% |
| Jeju | 2,518 | 37.7% |
| Seoul | 1,300 | 19.5% |
| **Total** | **6,677** | **100.0%** |

---

## Class Definition

| Class | Description |
|---|---|
| **Background** | Non-vegetated surfaces such as roads, buildings, bare soil, water, and other non-vegetation objects |
| **Tree** | Vegetation with coarse and irregular texture, often associated with canopy structures and distinct shadow patterns |
| **Low Vegetation** | Grass, shrubs, cropland, and other relatively smooth and homogeneous vegetation surfaces |

> **Note**  
> In MultiVeg, vegetation classes are distinguished primarily by **texture and spatial context** observed in very high-resolution satellite imagery, rather than absolute height.

---

## Data Preparation

The MultiVeg dataset was prepared through the following pipeline:

1. **Image collection** from KOMPSAT-3 / 3A satellite imagery
2. **Spatial resolution harmonization** to 0.5 m
3. **Radiometric normalization** using linear stretching
4. **Patch extraction** into 512 × 512 image tiles
5. **Manual annotation** by remote sensing experts
6. **Quality control** to remove unusable or ambiguous patches

### Annotation and Quality Control

- Annotations were conducted using expert knowledge of high-resolution remote sensing imagery.
- Labeling focused on semantic separation of **Tree**, **Low Vegetation**, and **Background**.
- Ambiguous cases were reviewed through expert discussion and cross-checking.
- Inter-annotator agreement was evaluated using **Fleiss’s Kappa**.
- Patches with severe cloud/shadow obstruction, blur, or image distortion were excluded.

---

## Benchmark Results

MultiVeg was evaluated with representative semantic segmentation models, including:

- **CNN-based models**: DeepLabV3+, HRNet, PSPNet, UPerNet, ConvNeXt
- **Transformer-based models**: Swin Transformer, SegFormer, ViT, MIFNet

### Main Observation

- Transformer-based models generally showed stronger performance than conventional CNN-based models.
- **Swin Transformer** achieved the best overall result with:

| Metric | Score |
|---|---:|
| mIoU | **78.88%** |
| mF1 | **87.58%** |
| OA | **92.33%** |

MultiVeg also showed robust performance across different seasons and geographic settings, supporting its utility as a practical benchmark for vegetation mapping in diverse environments.

---

## Dataset Access

The dataset is available through the following channels:

- **GitHub repository**: https://github.com/pang914/MultiVeg
- **RSIP Lab website**: https://sites.google.com/view/rsip/home

> **Data split policy**  
> The dataset is provided as a unified collection of patches, and users may define their own **train / validation / test** split depending on the research protocol.

<!-- Optional:
## Download

- [Download Link 1](TODO)
- [Download Link 2](TODO)
-->

---

## Repository Structure

```text
MultiVeg/
├── README.md
├── images/
│   ├── region_01_xxxx.png
│   └── ...
├── labels/
│   ├── region_01_xxxx.png
│   └── ...
├── splits/
│   ├── train.txt
│   ├── val.txt
│   └── test.txt
└── assets/
    ├── multiveg_teaser.png
    ├── class_legend.png
    └── benchmark_overview.png
