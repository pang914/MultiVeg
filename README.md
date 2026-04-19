<div align="center">

# MultiVeg: A Very High-Resolution Benchmark for Deep Learning-Based Multi-Class Vegetation Segmentation

[![Project Page](https://img.shields.io/badge/Project%20Page-GitHub-181717?logo=github)](https://github.com/pang914/MultiVeg)
[![Paper](https://img.shields.io/badge/Paper-Remote%20Sensing-B31B1B)](#citation)
[![Dataset](https://img.shields.io/badge/Dataset-MultiVeg-1F6FEB)](#dataset-access)
[![RSIP Lab](https://img.shields.io/badge/RSIP-SeoulTech-0A66C2)](https://sites.google.com/view/rsip/home)
[![License](https://img.shields.io/badge/License-See%20Section-9E9E9E)](#license)

<br>

<!-- Representative image -->
<img src="./assets/multiveg_banner.png" alt="MultiVeg banner" width="92%">

**Figure 1.** Overview of the **MultiVeg** dataset.  
A very high-resolution satellite benchmark for **multi-class vegetation segmentation** using **RGB + NIR** imagery from **KOMPSAT-3 / KOMPSAT-3A**.

</div>

---

## Introduction

**MultiVeg** is a very high-resolution satellite benchmark dataset for **deep learning-based multi-class vegetation segmentation**.  
Unlike conventional binary vegetation mapping, MultiVeg explicitly separates **Tree** and **Low Vegetation** from **Background**, enabling finer-grained vegetation analysis for remote sensing, urban ecological monitoring, and environmental applications.

Built from **KOMPSAT-3 / KOMPSAT-3A** imagery, MultiVeg provides **RGB + NIR** bands at **0.5 m spatial resolution**.  
By incorporating NIR information, the dataset improves vegetation discrimination in challenging cases such as shadows, asphalt, and other spectrally confusing surfaces.

---

## Table of Contents

- [Highlights](#highlights)
- [Dataset Overview](#dataset-overview)
- [Class Definition](#class-definition)
- [Dataset Details](#dataset-details)
  - [Image Pre-processing](#image-pre-processing)
  - [Annotation and Quality Control](#annotation-and-quality-control)
- [Sample Visualization](#sample-visualization)
- [Benchmark Experiments](#benchmark-experiments)
- [Dataset Access](#dataset-access)
- [Repository Structure](#repository-structure)
- [Recommended Usage](#recommended-usage)
- [Citation](#citation)
- [License](#license)
- [Contact](#contact)
- [Acknowledgement](#acknowledgement)

---

## Highlights

- **Very high-resolution benchmark** based on satellite imagery at **0.5 m GSD**
- **Multi-class vegetation segmentation** with three semantic classes:
  - **Background**
  - **Tree**
  - **Low Vegetation**
- **RGB + NIR** multi-spectral imagery for improved vegetation discrimination
- **Expert-annotated dataset** with quality control and inter-annotator agreement analysis
- Benchmarking with representative **CNN-based** and **Transformer-based** segmentation models
- Diverse scenes collected across **Seoul, Incheon, and Jeju** from **2014 to 2023**

---

## Dataset Overview

| Item | Description |
|---|---|
| Dataset name | MultiVeg |
| Task | Multi-class vegetation segmentation |
| Satellite platform | KOMPSAT-3, KOMPSAT-3A |
| Spatial resolution | 0.5 m |
| Spectral bands | RGB + NIR |
| Acquisition period | 2014–2023 |
| Study regions | Seoul, Incheon, Jeju (Republic of Korea) |
| Patch size | 512 × 512 pixels |
| Number of patches | 6,677 |
| Number of classes | 3 |
| File format | PNG (8-bit) |

### Regional Distribution

| Region | Number of Patches | Ratio |
|---|---:|---:|
| Incheon | 2,859 | 42.8% |
| Jeju | 2,518 | 37.7% |
| Seoul | 1,300 | 19.5% |
| **Total** | **6,677** | **100.0%** |

---

## Class Definition

MultiVeg defines vegetation classes primarily based on **texture** and **spatial context** observed in very high-resolution satellite imagery.

| Class | Description |
|---|---|
| **Background** | Non-vegetated surfaces such as buildings, roads, bare land, water, and other non-vegetation objects |
| **Tree** | Vegetation with coarse and irregular texture, often associated with canopy structure and distinct shadow patterns |
| **Low Vegetation** | Grass, shrubs, cropland, and other relatively smooth and homogeneous vegetation surfaces |

> **Note**  
> Since satellite imagery does not directly provide absolute object height, the distinction between **Tree** and **Low Vegetation** is defined by image texture and contextual appearance rather than explicit height measurements.

### Class Legend

<!-- Optional class legend image -->
<p align="center">
  <img src="./assets/class_legend.png" alt="Class legend of MultiVeg" width="60%">
</p>

<p align="center">
  <em>Figure 2. Class legend of MultiVeg: Background, Tree, and Low Vegetation.</em>
</p>

---

## Dataset Details

### Image Pre-processing

The MultiVeg dataset was prepared through the following procedure:

1. Collection of very high-resolution KOMPSAT-3 / KOMPSAT-3A satellite imagery  
2. Resolution harmonization to **0.5 m**  
3. Radiometric normalization using **linear stretching**  
4. Conversion to **8-bit PNG** format for efficient storage and model training  
5. Patch extraction into **512 × 512** tiles  
6. Quality screening to remove unusable or ambiguous samples  

### Annotation and Quality Control

- All labels were generated by experts in remote sensing image interpretation.
- Each pixel was annotated as **Background**, **Tree**, or **Low Vegetation**.
- Ambiguous cases were reviewed through expert discussion and cross-checking.
- Annotation consistency was assessed using **Fleiss’s Kappa**.
- The reported inter-annotator agreement indicates substantial consistency (**Fleiss’s Kappa = 0.6172**).
- Patches severely affected by cloud cover, extreme shadow obstruction, blur, or radiometric distortion were excluded from the final dataset.

---

## Sample Visualization

<p align="center">
  <img src="./assets/multiveg_samples.png" alt="Qualitative examples of MultiVeg patches and labels" width="92%">
</p>

<p align="center">
  <em>Figure 3. Representative examples from MultiVeg. Each example may include an RGB or RGB+NIR composite image and its corresponding pixel-wise annotation mask.</em>
</p>

---

## Benchmark Experiments

MultiVeg was benchmarked using representative deep learning segmentation models, including both CNN-based and Transformer-based architectures.

### Evaluated Models

- **CNN-based models**
  - DeepLabV3+
  - HRNet
  - PSPNet
  - UPerNet
  - ConvNeXt

- **Transformer-based models**
  - Swin Transformer
  - SegFormer
  - Vision Transformer (ViT)
  - MIFNet

### Main Results

Transformer-based models generally showed stronger overall performance than conventional CNN-based models on the MultiVeg benchmark.

| Best Model | mIoU | mF1 | OA |
|---|---:|---:|---:|
| **Swin Transformer** | **78.88** | **87.58** | **92.33** |

### Key Observations

- **Swin Transformer** achieved the best overall segmentation performance on MultiVeg.
- **Tree** and **Background** were segmented more reliably than **Low Vegetation**.
- **Low Vegetation** remains more challenging due to class imbalance and spectral ambiguity in complex urban scenes.
- The inclusion of **NIR** bands improves the discrimination of vegetation from confusing non-vegetated surfaces.
- The dataset shows robust performance across different seasons and geographic settings.

<p align="center">
  <img src="./assets/benchmark_results.png" alt="Benchmark performance on MultiVeg" width="78%">
</p>

<p align="center">
  <em>Figure 4. Benchmark comparison of representative semantic segmentation models on the MultiVeg dataset.</em>
</p>

---

## Dataset Access

The MultiVeg dataset is available through the following channels:

- **GitHub repository**: [https://github.com/pang914/MultiVeg](https://github.com/pang914/MultiVeg)
- **RSIP Lab website**: [https://sites.google.com/view/rsip/home](https://sites.google.com/view/rsip/home)

> **Split policy**  
> MultiVeg is provided as a unified collection of image patches.  
> Users may define their own **train / validation / test** split depending on their research protocol.

<!-- Optional official download links -->
<!--
### Download

- [Download Link 1](TODO)
- [Download Link 2](TODO)
-->

---

## Repository Structure

```text
MultiVeg/
├── README.md
├── assets/
│   ├── multiveg_banner.png
│   ├── multiveg_samples.png
│   ├── class_legend.png
│   └── benchmark_results.png
├── images/
│   ├── *.png
│   └── ...
├── labels/
│   ├── *.png
│   └── ...
├── splits/
│   ├── train.txt
│   ├── val.txt
│   └── test.txt
└── docs/
    └── ...
```
---

## Recommended Usage

MultiVeg can be used for:
 - Multi-class vegetation segmentation
 - Urban green space monitoring
 - Ecological and envirionmental remote sensing
 - RGB vs. RGB+NIR comparative experiments
 - Benchmarking semantic segmentation models on very high-resolution imagery

---
## Citation

If you use **MultiVeg** in your research, please cite the associated paper:

```text
@article{lee2025multiveg,
  title={MultiVeg: A Very High-Resolution Benchmark for Deep Learning-Based Multi-Class Vegetation Segmentation},
  author={Lee, Changhui and Han, Youkyung and Lee, Jinmin and Kim, Taeheon and Lee, Hyunjin and Javed, Aisha and Chung, Minkyung},
  journal={Remote Sensing},
  year={2025}
}
```
---

## License

The MultiVeg dataset is released under **component-wise licenses**:

- **Image patches (`images/`)**: [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)
- **Annotation masks (`masks/`)**: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

### What this means

- The **image patches** may be shared and adapted for **non-commercial purposes only**, with appropriate attribution.
- The **annotation masks** may be shared and adapted, including for **commercial use**, with appropriate attribution.

### Attribution Requirement

If you use MultiVeg in your research or project, please:

1. Give appropriate credit to the MultiVeg project and authors
2. Provide a link to the corresponding license
3. Indicate whether changes were made
4. Cite the associated publication

### Important Note

These licenses apply to the distributed components of the MultiVeg dataset as released in this repository.  
Users are responsible for complying with any additional terms or restrictions that may apply to upstream or third-party source imagery, if relevant.

---

## Contact

If you have any question or requirement regarding the MultiVeg, please contact:
 - *Changhui Lee*
 - **Email**: ckdgml914@seoultech.ac.kr

---



