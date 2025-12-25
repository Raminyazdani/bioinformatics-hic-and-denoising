# Bioinformatics Data Processing Pipeline

**Computational analysis of biological datasets**

**Stack:** Python, Jupyter Notebook

## Overview

This project implements two bioinformatics data processing workflows:

1. **Image Denoising** - Applies a homogeneous 2D diffusion filter to remove noise from images
2. **Hi-C Analysis** - Processes and analyzes chromatin contact matrices from Hi-C experiments

The implementations demonstrate computational techniques for signal processing and genomic data analysis.

## Problem & Approach

**Problems:**
1. Remove noise from images while preserving important features
2. Analyze 3D genome organization through Hi-C contact matrices

**Approaches:**
- **Diffusion Filter**: Implement finite difference method for 2D diffusion equation with periodic boundary conditions
- **Hi-C Processing**: Load contact matrices, apply iterative correction (ICE normalization), analyze contact patterns

## Tech Stack

- Python 3.x
- Jupyter Notebook
- NumPy (numerical computing)
- Pandas (data manipulation)
- Matplotlib (visualization)
- Cooler (Hi-C data format)
- Cooltools (Hi-C analysis utilities)

## Folder Structure

```
assignment 3/
├── code/
│   ├── assignment_3_1.ipynb  # Image denoising with diffusion filter
│   └── assignment_3_2.ipynb  # Hi-C contact matrix analysis
├── data/
│   └── noise.csv             # Input data for image denoising
├── requirements.txt
└── README.md
```

## Setup / Installation

```bash
pip install -r requirements.txt
```

## How to Run

```bash
cd "assignment 3/code"
jupyter notebook
```

## Data / Inputs

**Notebook 1 (Image Denoising):**
- `data/noise.csv` - Noisy 2D image matrix (96x86 pixels)

**Notebook 2 (Hi-C Analysis):**
- Hi-C contact matrices loaded via Cooler format from public repositories
- Chromosome contact data at various resolutions

## Outputs

**Notebook 1:**
- Denoised images at various time steps
- Visualization of diffusion process
- Comparison of different parameter settings

**Notebook 2:**
- Normalized Hi-C contact matrices
- Contact frequency heatmaps
- Statistical analysis of chromatin interactions

## Reproducibility Notes

- All paths relative
- Originally created in an academic setting

## Notes

- Two notebooks covering different analysis aspects
- Comprehensive bioinformatics workflow
