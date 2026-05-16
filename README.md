# ARMA-C3: Contrastive Graph Representation Learning for Biomedical Imaging

Official implementation of **ARMA-C$^3$**, a graph-based framework for unsupervised clustering and semi-supervised classification on multimodal biomedical datasets.

---

## Abstract

In biomedical and neurodegenerative disorders, accurate and early disease identification remains challenging due to limited labeled data and complex imaging patterns. To address these challenges, we propose **ARMA-C$^3$**, a unified unsupervised and semi-supervised graph learning framework based on contrastive learning and graph cut optimization for learning structurally meaningful and discriminative representations. By modeling subjects or images as graph nodes and leveraging inter-subject relationships, the proposed framework captures cohort-level dependencies often ignored by conventional machine learning methods.

We evaluate ARMA-C$^3$ across five clinically relevant datasets, including the Alzheimer’s Disease Neuroimaging Initiative (ADNI), Neuroimaging in Frontotemporal Dementia (NIFD), BreastMNIST, PneumoniaMNIST, and a Liver Tumor Ultrasound dataset. Experimental results demonstrate that ARMA-C$^3$ consistently outperforms classical clustering approaches, state-of-the-art machine learning baselines, and existing graph-based deep learning methods in both unsupervised and semi-supervised settings, highlighting its robustness, generalizability, and potential clinical applicability.

---

## Overview

ARMA-C$^3$ combines:

* Graph neural networks (GCN, GAT, ARMA)
* Graph partitioning objectives (Modularity / Normalized Cut)
* Contrastive representation learning (DGI, MERIT)
* Medical imaging feature extraction using DINO and ResNet backbones

The framework is evaluated on:

* ADNI (CN vs MCI vs AD)
* NIFD
* BreastMNIST
* PneumoniaMNIST
* Liver Tumor Ultrasound Dataset

---

## Repository Structure

```text
ARMAC3_2026/
│
├── Unsupervised_Clustering/
├── Semisupervised_Classification/
├── Feature_Extraction/
├── Dataset_examples/
├── figures/
├── requirements.txt
└── README.md
```

---

## Installation

Clone repository:

```bash
git clone https://github.com/tejaswi-abburi1083/ARMAC4-2026.git
cd ARMAC4-2026
```

Create environment:

```bash
conda create -n armac3 python=3.10
conda activate armac3
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Datasets

### ADNI

Alzheimer’s Disease Neuroimaging Initiative diffusion MRI cohort.

### NIFD

Frontotemporal dementia diffusion MRI cohort.

### BreastMNIST

Ultrasound breast tumor classification dataset.

### PneumoniaMNIST

Pediatric chest X-ray classification dataset.

### Liver Tumor Ultrasound Dataset

Annotated liver ultrasound dataset containing benign and malignant liver tumor images.

> Due to licensing and privacy restrictions, datasets are not included in this repository.

---

## Feature Extraction

DINO ViT features:

```bash
python extract_dino_features.py
```

ResNet features:

```bash
python extract_resnet_features.py
```

---

## Unsupervised Clustering

Example:

```bash
python train_unsupervised.py
```

Implemented variants:

* Modularity
* Normalized Cut
* DGI + Mod
* DGI + Cut
* MERIT + Mod
* MERIT + Cut

Backbones:

* GCN
* GAT
* ARMA

---

## Semi-Supervised Classification

Example:

```bash
python train_semisupervised.py
```

Supported models:

* ARMA
* GAT
* APPNP
* JacobiConv
* SVC
* Random Forest
* XGBoost
* MLP

---

## Results

ARMA-C$^3$ demonstrates strong performance across multimodal biomedical datasets under both unsupervised and semi-supervised settings.

Representative metrics include:

| Dataset          | Setting         | Best F1 Score |
| ---------------- | --------------- | ------------- |
| BreastMNIST      | Semi-supervised | 0.841         |
| PneumoniaMNIST   | Semi-supervised | 0.827         |
| Liver Ultrasound | Unsupervised    | 0.817         |
| NIFD             | Semi-supervised | 0.789         |

---

## Citation

If you use this repository, please cite:

```bibtex
@article{abburi2026armac3,
  title={ARMAC3: Contrastive Graph Representation Learning for Biomedical Imaging},
  author={Abburi, Tejaswi and collaborators},
  journal={Under Review},
  year={2026}
}
```

---

## Acknowledgements

This work utilizes publicly available biomedical datasets including ADNI, NIFD, MedMNIST, and Liver Ultrasound datasets.

---

## Contact

Tejaswi Abburi
Shiv Nadar University
Email: [va797@snu.edu.in](mailto:va797@snu.edu.in)
