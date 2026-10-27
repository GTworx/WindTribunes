---
title: "Defect detection and classification of offshore wind turbine rotor blades"
source: "https://www.tandfonline.com/doi/full/10.1080/10589759.2023.2234554"
author:
  - "[[Liwei Deng]]"
  - "[[Shanshan Liu]]"
  - "[[Wei Shi]]"
  - "[[Jiazhong Xu]]"
published: 2024-05-18
created: 2026-10-25
description: "1. The WTRB is an important part of the wind turbine. Lightning, sand and dust, irregular loading, and mis-operation in production can all cause damage to the WTRB [1,2]. Small cracks found early c..."
tags:
  - "clippings"
---
## ABSTRACT

With increasing demand for electricity, wind turbines have gained significant attention from the public. Offshore wind power generation has emerged as a popular choice due to its potential to reduce power transmission losses and minimal impact on humans and organisms. However, it also presents challenges in detecting defects in Wind Turbine Rotor Blades (WTRB) and repairing them. To address this issue, this paper proposes an improved wavelet-based S-U-Net network to denoise WTRB images followed by a weakly supervised CNN method for removing background parts that could affect defective feature extraction. Defective features are then extracted using VGG16 network on a deep learning server platform, while an enhanced Particle Swarm Optimization (PSO) algorithm combined with K-means is used to classify defect features of WTRBs. Experimental results demonstrate that classification accuracy of unlabelled blade defect datasets improved significantly from 62.6% using only Kmeans clustering method up to 96.4% using our proposed algorithm approach. This study applies improved PSO and Kmeans algorithms towards offshore Wind Turbine Rotor Blade condition monitoring with precise detection test results enabling early-stage detection of Wind Turbine Rotor Blades defects leading to timely repairs.

KEYWORDS:

### Acknowledgments

This research was funded by the Natural Science Foundation of Heilongjiang Province (LH2019F024), China, 2019–2022, “Research on The Key Technology of Defect Detection of Wind Turbine Rotor Blade Based on Unmanned Aerial Vehicle-Taken Images.” This research was also funded by the Key R&D Program Guidance Projects of Heilongjiang Province (Grant No. GZ20210065)2021-2024, “Research and development of intelligent winding equipment for hydrogen cylinders based on robots.”

## Disclosure statement

No potential conflict of interest was reported by the author(s).

## Data availability statement

This paper uses the Outdoor Training Set dataset from the RESIDE database. The data that support the findings of this study are openly available in RESIDE database at [https://datasets.activeloop.ai/docs/ml/datasets/reside-dataset](https://datasets.activeloop.ai/docs/ml/datasets/reside-dataset).

## CRediT authorship contribution statement

L.D: Conceptualization, Methodology, Visualization, Formal analysis, Funding acquisition, Investigation, Supervision. S.L: Conceptualization, Software, Visualization, Formal analysis, Data curation, Writing – Original Draft. W.S: Visualization, Investigation, Resources, Writing – Review & Editing. J.X: Visualization, Project administration. All the authors read and approved the final manuscript.