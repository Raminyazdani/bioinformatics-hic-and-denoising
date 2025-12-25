# Hi-C Contact Matrix Analysis and Image Denoising

**Computational analysis of Hi-C genomic contact matrices and diffusion-based image denoising**

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

## Repository Structure

```
bioinformatics-hic-and-denoising/
├── code/
│   ├── image_denoising.ipynb  # Image denoising with diffusion filter
│   └── hic_analysis.ipynb     # Hi-C contact matrix analysis
├── data/
│   └── noise.csv              # Input data for image denoising
├── requirements.txt
└── README.md
```

## Setup / Installation

```bash
pip install -r requirements.txt
```

## How to Run

```bash
cd code
jupyter notebook
```

Then open either `image_denoising.ipynb` or `hic_analysis.ipynb` in your browser.

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

- All paths are relative to the repository root
- Python dependencies are specified in `requirements.txt`
- Notebooks include visualization of intermediate results

## Notes

- Two notebooks covering different analysis aspects
- Comprehensive bioinformatics workflow

