# Git History Reconstruction: bioinformatics-hic-and-denoising

This document describes the reconstructed development history for the Hi-C Contact Matrix Analysis and Image Denoising project.

## Overview

This git history represents a plausible development path for a bioinformatics researcher building computational tools for Hi-C genomic data analysis and image denoising. The history reflects iterative development, starting from project setup through implementing two major analysis workflows, with refinements and documentation improvements.

## Development Timeline

### Step 01: Initial Repository Setup
**Commit Message:** `Initial commit: project setup`

**Description:** Initialize repository with basic structure and documentation.

**Files Created:**
- `README.md` - Initial project description
- `.gitignore` - Python/Jupyter ignore patterns
- `requirements.txt` - Initial dependency list

**Rationale:** Every project starts with initialization. The developer sets up the repository with a minimal README outlining the project goals and creates a .gitignore for Python development.

---

### Step 02: Add Data Directory and Sample Data
**Commit Message:** `Add data directory with noisy image dataset`

**Description:** Add the data directory structure and the noisy image CSV file for the denoising workflow.

**Files Created:**
- `data/noise.csv` - Noisy 2D image matrix (96x86 pixels)

**Rationale:** Before implementing analysis, the developer adds the input data. The noise.csv file contains a real noisy image that will be used for testing the diffusion filter implementation.

---

### Step 03: Implement Image Denoising Workflow
**Commit Message:** `Implement diffusion-based image denoising`

**Description:** Create the first analysis notebook implementing a 2D diffusion equation for image denoising.

**Files Created:**
- `code/image_denoising.ipynb` - Complete implementation of diffusion filter

**Content Includes:**
- Import statements and setup
- Loading and visualizing noisy image
- Diffusion step implementation (explicit finite difference scheme)
- Efficient diffusion runner with snapshot capture
- Parameter exploration (different time steps)
- Analysis and visualization of results
- Discussion of why diffusion is suitable for denoising

**Rationale:** The developer starts with the image denoising component, implementing the mathematical diffusion equation using finite differences. The notebook includes visualization and parameter exploration to understand the behavior of the filter.

---

### Step 04: Implement Hi-C Analysis Workflow
**Commit Message:** `Implement Hi-C contact matrix analysis pipeline`

**Description:** Create the second analysis notebook for Hi-C genomic contact matrix analysis.

**Files Created:**
- `code/hic_analysis.ipynb` - Complete Hi-C analysis pipeline

**Content Includes:**
- Import statements for cooler and cooltools
- Fetching hESC Micro-C data (Chromosome 2, 1 Mb resolution)
- Visualizing raw contact heatmaps (before bias removal)
- Vanilla coverage normalization implementation
- ICE normalization (Iterative Correction and Eigenvector decomposition)
- Comparative visualizations of normalization methods

**Rationale:** After completing the denoising workflow, the developer implements the Hi-C analysis component. This involves fetching real genomic data from public repositories and applying normalization techniques to correct for systematic biases.

---

### Step 05: Update Dependencies
**Commit Message:** `Update requirements with Hi-C analysis libraries`

**Description:** Add specialized bioinformatics libraries needed for Hi-C analysis.

**Files Modified:**
- `requirements.txt` - Add cooler and cooltools packages

**Rationale:** As the Hi-C workflow is developed, the developer realizes additional specialized libraries are needed and updates the requirements file accordingly.

---

### Step 06: Enhance Documentation
**Commit Message:** `Improve README with detailed setup and usage instructions`

**Description:** Expand README with comprehensive documentation including setup instructions, data descriptions, and output examples.

**Files Modified:**
- `README.md` - Enhanced with detailed sections

**Enhancements:**
- More detailed problem and approach descriptions
- Clear repository structure diagram
- Explicit setup/installation instructions
- Detailed input/output descriptions for each notebook
- Reproducibility notes

**Rationale:** With both workflows implemented, the developer enhances documentation to make the project accessible to others. This includes clear instructions for running the notebooks and understanding the inputs/outputs.

---

### Step 07: Final Polish and Portfolio Preparation
**Commit Message:** `Final documentation polish for portfolio presentation`

**Description:** Final refinements to present the project professionally.

**Files Modified:**
- `README.md` - Polish title and descriptions
- `code/image_denoising.ipynb` - Clean up section headers
- `code/hic_analysis.ipynb` - Clean up section headers

**Changes:**
- Ensure all section headers are professional and descriptive
- Verify all cross-references are clear
- Confirm consistent terminology throughout

**Rationale:** Before considering the project complete, the developer does a final review to ensure all documentation and code presentation is polished and professional.

---

## Development Methodology

This history reflects realistic research software development:

1. **Iterative Development**: Start with setup, add data, implement features one at a time
2. **Working Code First**: Implement functionality before extensive documentation
3. **Continuous Refinement**: Update dependencies and documentation as the project evolves
4. **Portfolio Readiness**: Final polish to present professionally

## Technical Notes

- All commits represent complete, working states
- Each step builds upon the previous
- No broken intermediate states
- Realistic commit messages that describe intent
- Natural progression from simple to complex

## Snapshot Structure

Each step is provided as a complete snapshot in `history/steps/step_XX/` containing all files that should exist at that point in the project history. This allows for complete reconstruction of the development timeline.

---

**Total Steps:** 7
**Development Arc:** Setup → Data → Feature 1 → Feature 2 → Dependencies → Documentation → Polish
