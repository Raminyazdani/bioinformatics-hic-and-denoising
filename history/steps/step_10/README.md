# Hi-C Contact Matrix Analysis and Image Denoising

**Computational analysis of Hi-C genomic contact matrices and diffusion-based image denoising**

## Overview

This project implements two bioinformatics data processing workflows:

1. **Image Denoising** - Applies a 2D diffusion filter to remove noise from images
2. **Hi-C Analysis** - Processes and analyzes chromatin contact matrices from Hi-C experiments

## Tech Stack

- Python 3.x
- Jupyter Notebook
- NumPy, Pandas, Matplotlib
- Cooler, Cooltools (Hi-C analysis)

## Repository Structure

```
bioinformatics-hic-and-denoising/
├── code/
│   ├── image_denoising.ipynb
│   └── hic_analysis.ipynb
├── data/
│   └── noise.csv
├── requirements.txt
└── README.md
```

## Setup

```bash
pip install -r requirements.txt
```

## How to Run

```bash
cd code
jupyter notebook
```

Then open either `image_denoising.ipynb` or `hic_analysis.ipynb` in your browser.

## Data

**Notebook 1:** Uses `data/noise.csv` - a noisy 2D image matrix

**Notebook 2:** Fetches Hi-C contact matrices from public repositories via Cooler format

## Outputs

- Denoised images at various time steps
- Normalized Hi-C contact matrices
- Statistical analysis and visualizations
