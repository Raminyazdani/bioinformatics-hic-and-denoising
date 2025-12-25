# Portfolio Readiness Report

## Project: bioinformatics-hic-and-denoising

### Phase 0: Initial Setup
- Created report.md, suggestion.txt, suggestions_done.txt, project_identity.md
- .github/copilot-instructions.md already exists

### Phase 1: Understanding the Project

#### Repository Structure (Current State)
```
bioinformatics-hic-and-denoising/
├── .github/
│   ├── copilot-instructions.md
│   └── ISSUE_TEMPLATE/
├── code/
│   ├── assignment_3_1.ipynb  (Image denoising with diffusion filter)
│   └── assignment_3_2.ipynb  (Hi-C contact matrix analysis)
├── data/
│   └── noise.csv (96x86 noisy image data)
├── README.md
├── requirements.txt
├── project_identity.md
├── report.md
├── suggestion.txt
└── suggestions_done.txt
```

#### Project Understanding
**Domain**: Bioinformatics computational analysis

**Two Main Workflows**:
1. **Image Denoising**: Implements homogeneous 2D diffusion equation using finite difference method with periodic boundary conditions to denoise biological images
2. **Hi-C Analysis**: Processes chromatin contact matrices from Hi-C experiments, applies ICE normalization, analyzes 3D genome organization

**Tech Stack**: Python 3.x, Jupyter Notebook, NumPy, Pandas, Matplotlib, Cooler, Cooltools

**How it runs**: Via Jupyter notebooks (two notebooks, one per workflow)

**Current naming issues detected**:
- Notebook filenames contain "assignment_3_1" and "assignment_3_2"
- README references "assignment 3/" folder structure
- Notebooks contain assignment-style section headers ("Part (a)", "part(b)", etc.)
- README mentions "Originally created in an academic setting"

#### Professional Identity (from project_identity.md)
- **Display Title**: Hi-C Contact Matrix Analysis and Image Denoising
- **Repo Slug**: bioinformatics-hic-and-denoising
- **Tagline**: Computational analysis of Hi-C genomic contact matrices and diffusion-based image denoising
- **Primary Focus**: Bioinformatics pipeline for genomic data analysis and biological image processing

#### Naming Alignment Plan
**Conservative approach - minimal safe renames**:
1. Rename notebooks:
   - `assignment_3_1.ipynb` → `image_denoising.ipynb`
   - `assignment_3_2.ipynb` → `hic_analysis.ipynb`
2. Update notebook internal content:
   - Replace "Part (a)", "Part (b)", etc. with professional section headers
   - Remove cross-references to "part (a)" in text
3. Update README.md:
   - Remove "assignment 3/" folder references
   - Remove "Originally created in an academic setting" line
   - Update file paths and descriptions
4. Create .gitignore (missing, needed for Python/Jupyter projects)

**Safe**: All renames are file-level or text-only. No code logic changes. Relative paths in notebooks already use `../data/noise.csv` which will continue to work.

### Phase 2: Pre-Change Audit (suggestion.txt)
Completed comprehensive scan. Findings:
- **26 total issues** identified and logged to suggestion.txt
- **7 RENAME** items (2 notebook files)
- **19 TRACE** items (assignment references in README and notebooks)
- **1 DOC** item (academic setting reference)
- **1 STRUCTURE** item (.gitignore missing)
- **0 PATH** issues (all paths are already relative and safe)

Key findings:
- No absolute paths found (good!)
- No brittle Windows/Unix paths (good!)
- Main issues are assignment-style naming and section headers
- All issues are text/naming related, no code logic to fix

