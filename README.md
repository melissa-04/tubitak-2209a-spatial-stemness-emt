# tubitak-2209a-spatial-stemness-emt
# Breast Cancer Spatial Transcriptomics — Stemness & EMT at the Invasive Front

Spatial transcriptomic analysis of cancer stem cell potential (stemness) and the
epithelial–mesenchymal transition (EMT) program in breast cancer, comparing the
**invasive front** with the **tumor core**. Built in Python (scanpy ecosystem) on
10x Visium and scRNA-seq data.

**TÜBİTAK 2209-A Undergraduate Research Project**

## Research Question
How are cancer stem cell potential (stemness) and the EMT program spatially
distributed across breast cancer tissue, and how do they relate to each other —
particularly at the invasive front versus the tumor core?

## Approach
- **Stemness** is a single-cell property → estimated on scRNA-seq epithelial cells with **CytoTRACE 2**.
- **EMT** is scored per Visium spot from its own expression (gene-signature scoring).
- **Bridge:** single cells are mapped back onto Visium spots with **CytoSPACE**, using
  per-spot cell-type proportions from **deconvolution**, so each spot inherits a spatial
  stemness score.
- **Statistics** are run at the **patient level** (not pooled spots) and reported as
  exploratory / hypothesis-generating.

## Repository Structure
- `notebooks/` — numbered analysis notebooks (run in order)
- `src/` — reusable helper functions (added as the project grows)
- `data/`, `figures/`, `results/` — local outputs (not tracked; kept in Drive)

## Analysis Steps
0. Setup and data exploration
1. Region labeling (invasive front vs. tumor core)
2. scRNA-seq preparation
3. CytoTRACE 2 — cell-level stemness
4a. Deconvolution — per-spot cell-type proportions
4b. CytoSPACE — assign cells to spots (spatial stemness)
5. EMT scoring (per spot)
6. Patient-level statistics
7. Figures and report

## Setup
```bash
pip install -r requirements.txt
```

## Open in Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/melissa-04/tubitak-2209a-spatial-stemness-emt/blob/main/notebooks/00_setup_and_exploration.ipynb)

## Data Source
Wu SZ, Al-Eryani G, Roden DL, ..., Swarbrick A. *Nature Genetics* 53(9):1334–1347 (2021).
DOI: 10.1038/s41588-021-00911-1 (GEO: GSE176078). Both Visium and scRNA-seq are from this study.

## License
MIT
