# Git History Reconstruction: bioinformatics-hic-and-denoising

This document describes the reconstructed development history for the Hi-C Contact Matrix Analysis and Image Denoising project.

## History Expansion Note

**Previous Run:**
- Old step count (N_old): 7
- Previous steps covered: Initial setup → Data → Image denoising → Hi-C analysis → Dependencies → Documentation → Polish

**Current Run:**
- Target step count (N_target): 11 (ceil(7 × 1.5) = 11)
- Achieved step count: 11
- Achieved multiplier: 1.57× (11/7 = 1.571)

**Mapping from Old Steps to New Steps:**

| Old Step | Description | New Steps | Expansion Strategy |
|----------|-------------|-----------|-------------------|
| Old 01 | Initial repository setup | New 01-03 | Split into: basic README (01), .gitignore (02), requirements (03) |
| Old 02 | Add data directory | New 04 | Direct mapping |
| Old 03 | Implement image denoising | New 05-07 | Split into: implementation (05), oops-typo (06), hotfix (07) |
| Old 04 | Implement Hi-C analysis | New 08 | Direct mapping |
| Old 05 | Update dependencies | New 09 | Direct mapping |
| Old 06 | Enhance documentation | New 10 | Direct mapping |
| Old 07 | Final polish | New 11 | Direct mapping |

**Expansion Strategies Used:**
1. **Split large steps**: Old step 01 split into 3 commits (01, 02, 03) for setup components
2. **Insert oops→hotfix**: Steps 06-07 represent a realistic mistake and correction
3. **Maintain coherence**: Each new step is a logical, atomic commit

---

## Overview

This git history represents a plausible development path for a bioinformatics researcher building computational tools for Hi-C genomic data analysis and image denoising. The history reflects iterative development with realistic mistakes and fixes, starting from project initialization through implementing two major analysis workflows.

## Development Timeline

### Step 01: Initial Repository Setup
**Commit Message:** `Initial commit: create basic README`

**Description:** Initialize repository with a minimal README outlining project goals.

**Files Created:**
- `README.md` - Basic project description with overview and planned features

**Rationale:** Every project starts with a README. The developer creates a simple document stating what the project will do, keeping it minimal at first.

---

### Step 02: Add Python Gitignore
**Commit Message:** `Add .gitignore for Python/Jupyter development`

**Description:** Add .gitignore to prevent committing temporary and generated files.

**Files Created:**
- `.gitignore` - Standard Python/Jupyter ignore patterns

**Rationale:** After creating the README, the developer immediately sets up .gitignore before adding any code, following best practices to avoid accidentally committing temporary files or caches.

---

### Step 03: Add Initial Dependencies
**Commit Message:** `Add requirements.txt with core dependencies`

**Description:** Create requirements.txt with basic scientific computing libraries.

**Files Created:**
- `requirements.txt` - numpy, pandas, matplotlib, jupyter

**Rationale:** Before writing code, the developer specifies the core dependencies needed for numerical computing and visualization. Hi-C specific libraries will be added later when that workflow is implemented.

---

### Step 04: Add Data Directory and Sample Data
**Commit Message:** `Add data directory with noisy image dataset`

**Description:** Add the data directory structure and the noisy image CSV file for the denoising workflow.

**Files Created:**
- `data/noise.csv` - Noisy 2D image matrix (96x86 pixels)

**Rationale:** With the basic setup complete, the developer adds the input data before implementing the analysis. The noise.csv file contains a real noisy image that will be used for testing the diffusion filter.

---

### Step 05: Implement Image Denoising Workflow
**Commit Message:** `Implement diffusion-based image denoising notebook`

**Description:** Create the first analysis notebook implementing a 2D diffusion equation for image denoising.

**Files Created:**
- `code/image_denoising.ipynb` - Complete implementation of diffusion filter

**Content Includes:**
- Import statements and setup
- Loading and visualizing noisy image from `../data/noise.csv`
- Diffusion step implementation (explicit finite difference scheme)
- Efficient diffusion runner with snapshot capture
- Parameter exploration (different time steps: dt=0.1, 0.25, 0.4)
- Analysis and visualization of results
- Discussion of why diffusion is suitable for denoising

**Rationale:** The developer starts with the image denoising component, implementing the mathematical diffusion equation using finite differences. The notebook includes visualization and parameter exploration.

---

### Step 06: Oops - Data Path Typo
**Commit Message:** `Fix data loading path in image denoising notebook`

**Description:** While testing the notebook, the developer accidentally introduces a typo in the data file path.

**Files Modified:**
- `code/image_denoising.ipynb` - Changed `../data/noise.csv` to `../data/noisy.csv`

**What Broke:**
The notebook now tries to load `../data/noisy.csv` instead of `../data/noise.csv`, causing a FileNotFoundError when trying to read the data.

**How It Was Noticed:**
After committing, the developer tried to run the notebook from scratch and got:
```
FileNotFoundError: [Errno 2] No such file or directory: '../data/noisy.csv'
```

**Rationale:** This represents a realistic mistake - a simple typo that slips through while making edits. The developer commits without running the full notebook first, a common occurrence in rapid development.

---

### Step 07: Hotfix - Correct Data Path
**Commit Message:** `Hotfix: correct data path back to noise.csv`

**Description:** Immediately fix the typo after discovering it broke the notebook.

**Files Modified:**
- `code/image_denoising.ipynb` - Corrected `../data/noisy.csv` back to `../data/noise.csv`

**What Fixed It:**
Changed all references from `noisy.csv` back to the correct filename `noise.csv`.

**Verification:**
The developer ran the first few cells of the notebook to verify the data loads correctly before committing the fix.

**Rationale:** Quick hotfix to restore working state. The developer prioritizes getting the code working again before moving on to the next feature.

---

### Step 08: Implement Hi-C Analysis Workflow
**Commit Message:** `Implement Hi-C contact matrix analysis pipeline`

**Description:** With image denoising working correctly, create the second analysis notebook for Hi-C genomic contact matrix analysis.

**Files Created:**
- `code/hic_analysis.ipynb` - Complete Hi-C analysis pipeline

**Content Includes:**
- Import statements for cooler and cooltools
- Fetching hESC Micro-C data (Chromosome 2, 1 Mb resolution)
- Visualizing raw contact heatmaps (before bias removal)
- Vanilla coverage normalization implementation
- ICE normalization (Iterative Correction and Eigenvector decomposition)
- Comparative visualizations of normalization methods

**Rationale:** After completing and fixing the denoising workflow, the developer implements the Hi-C analysis component. This involves fetching real genomic data from public repositories and applying normalization techniques to correct for systematic biases.

---

### Step 09: Update Dependencies for Hi-C
**Commit Message:** `Add cooler and cooltools for Hi-C analysis`

**Description:** Update requirements.txt with specialized bioinformatics libraries needed for Hi-C workflow.

**Files Modified:**
- `requirements.txt` - Added cooler>=0.8.0 and cooltools>=0.5.0

**Rationale:** After implementing the Hi-C analysis notebook, the developer updates the dependency file to include the specialized libraries. This ensures anyone setting up the project has all the necessary packages.

---

### Step 10: Enhance Documentation
**Commit Message:** `Improve README with detailed setup and usage instructions`

**Description:** Expand README with comprehensive documentation including setup instructions, repository structure, data descriptions, and output examples.

**Files Modified:**
- `README.md` - Significantly enhanced with detailed sections

**Enhancements:**
- More detailed problem and approach descriptions
- Clear repository structure diagram
- Explicit setup/installation instructions (`pip install -r requirements.txt`)
- Step-by-step "How to Run" instructions
- Detailed input descriptions for each notebook
- Expected outputs and visualizations
- Notes on reproducibility

**Rationale:** With both workflows fully implemented, the developer enhances documentation to make the project accessible to others. This includes clear instructions for running the notebooks and understanding the inputs/outputs.

---

### Step 11: Final Polish and Portfolio Preparation
**Commit Message:** `Final polish: enhance README sections and formatting`

**Description:** Final refinements to present the project professionally with more polished language and comprehensive information.

**Files Modified:**
- `README.md` - Final polish with enhanced descriptions

**Changes:**
- More professional tagline
- Enhanced "Problem & Approach" section
- More detailed tech stack descriptions
- Added "Reproducibility Notes" section
- Improved formatting and clarity throughout

**Rationale:** Before considering the project complete, the developer does a final review to ensure all documentation is polished, professional, and provides a complete picture of the project's capabilities.

---

## Development Methodology

This history reflects realistic research software development:

1. **Incremental Setup**: Start small (README) then add infrastructure pieces (gitignore, dependencies) one at a time
2. **Data-Driven**: Add data before implementing algorithms
3. **Iterative Development**: Implement features one at a time, test, then move forward
4. **Mistakes Happen**: Real developers make typos and catch them later (steps 06-07)
5. **Dependency Management**: Add specialized dependencies as they're needed, not all upfront
6. **Documentation Evolution**: Start with basics, enhance as the project grows, polish at the end
7. **Working Code First**: Implement functionality before extensive documentation
8. **Portfolio Readiness**: Final polish to present professionally

## Technical Notes

- All commits represent complete snapshots (not diffs)
- Each step builds naturally upon the previous one
- Steps 06-07 demonstrate realistic mistake/fix cycle
- Final state (step_11) matches the actual project exactly
- No broken intermediate states (except step_06, which is immediately fixed in step_07)
- Realistic commit messages that describe developer intent
- Natural progression from simple to complex

## Snapshot Structure

Each step is provided as a complete snapshot in `history/steps/step_XX/` containing all files that should exist at that point in the project history. This allows for complete reconstruction of the development timeline.

- Step snapshots do NOT include `.git/` directory
- Step snapshots do NOT include `history/` directory  
- Each snapshot represents a complete, working state of the project at that commit
- Portfolio meta-files (project_identity.md, report.md, suggestion.txt, suggestions_done.txt) are NOT included in snapshots as they are meta-documentation, not part of the project itself

---

## Snapshot Statistics

- **Total steps:** 11
- **Development arc:** Setup (01-03) → Data (04) → Feature 1 (05-07, with fix) → Feature 2 (08) → Dependencies (09) → Documentation (10) → Polish (11)
- **Realistic elements:** 1 oops→hotfix pair (steps 06-07)
- **Step splitting:** 3 steps for initial setup (was 1), 3 steps for image denoising with fix (was 1)
- **Final state:** Matches current repository exactly (excluding portfolio meta-files)

---

**Expansion Achievement:**
- Required: 11 steps minimum (1.5× of 7)
- Delivered: 11 steps
- Multiplier: 1.57× ✓
- Oops→hotfix pairs: 1 ✓
- Final snapshot match: Exact ✓
