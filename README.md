<div align="center">

# MultiVeg: A Very High-Resolution Benchmark for Deep Learning-Based Multi-Class Vegetation Segmentation

![GitHub stars](https://img.shields.io/github/stars/pang914/MultiVeg?style=social)
![Visitors](https://komarev.com/ghpvc/?username=pang914&label=Visitors)
[![Paper](https://img.shields.io/badge/Paper-Remote%20Sensing-B31B1B)](https://doi.org/10.3390/rs18010028)
[![Dataset](https://img.shields.io/badge/Dataset-MultiVeg-1F6FEB)](#dataset-access)
[![RSIP Lab](https://img.shields.io/badge/RSIP_LAB-SeoulTech-0A66C2)](https://sites.google.com/view/rsip/home)
<br>
[![Data License](https://img.shields.io/badge/Data%20License-Mixed-blueviolet)](#license)
[![Images License](https://img.shields.io/badge/Images-CC%20BY--NC%204.0-orange)](https://creativecommons.org/licenses/by-nc/4.0/)
[![Masks License](https://img.shields.io/badge/Masks-CC%20BY%204.0-brightgreen)](https://creativecommons.org/licenses/by/4.0/)

<br>

<!-- Representative image -->
<img src="./assets/multiveg_banner.png" alt="MultiVeg banner" width="92%">

**Figure 1.** Overview of the **MultiVeg** dataset.  
A very high-resolution satellite benchmark for **multi-class vegetation segmentation** using **RGB + NIR** imagery from **KOMPSAT-3 / KOMPSAT-3A**.

</div>

---

## If you find MultiVeg useful in your research, please consider giving this repository a star ⭐

This repository is the official release of **MultiVeg**, a very high-resolution benchmark dataset for deep learning-based multi-class vegetation segmentation.  
The associated paper can be accessed here: [Remote Sensing paper](https://doi.org/10.3390/rs18010028).

If you have any questions about the dataset, please feel free to open an issue or contact the repository maintainer:

- **Changhui Lee**  
- **Email**: ckdgml914@seoultech.ac.kr

We also welcome suggestions, academic discussions, and potential collaborations.

---

## Table of Contents

- [Updates](#updates)
- [Introduction](#introduction)
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
- [Acknowledgement](#acknowledgement)

---

## Updates

- **2026.04.19** — README reorganized with polished project layout, mixed-license clarification, updated dataset access, and visual documentation sections.
- **2025.12.22** — The MultiVeg paper was officially published in *Remote Sensing*. [Paper](https://doi.org/10.3390/rs18010028)
- **2025.12.15** — The MultiVeg paper was accepted for publication in *Remote Sensing*.

> Future updates, including dataset revisions, additional benchmark results, and repository improvements, will be tracked in this section.

---

## Introduction

**MultiVeg** is a very high-resolution satellite benchmark dataset for **deep learning-based multi-class vegetation segmentation**.  
Unlike conventional binary vegetation mapping, MultiVeg explicitly separates **Tree** and **Low Vegetation** from **Background**, enabling finer-grained vegetation analysis for remote sensing, urban ecological monitoring, and environmental applications.

Built from **KOMPSAT-3 / KOMPSAT-3A** imagery, MultiVeg provides **RGB + NIR** bands at **0.5 m spatial resolution**.  
By incorporating NIR information, the dataset improves vegetation discrimination in challenging cases such as shadows, asphalt, and other spectrally confusing surfaces.

The official publication is available in *Remote Sensing*: [https://doi.org/10.3390/rs18010028](https://doi.org/10.3390/rs18010028).

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
|<span class="cursor">█</span>
