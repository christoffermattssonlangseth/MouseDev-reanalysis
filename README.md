# Mouse Brain Development Reanalysis

Reanalysis workspace for an existing mouse brain development dataset, intended to showcase the complexity of Karospace. This repository starts minimal and will evolve as analyses, figures, and documentation are added.

## Goals
- Reanalyze an older dataset with modern tooling and reproducible workflows
- Document findings, pipeline steps, and key outputs
- Provide a clear, navigable project structure for others to follow

## Getting Started
1. Add the dataset or data pointers in `data/` (use `.gitignore` to keep large/raw files out of git).
2. Capture provenance and any preprocessing steps in `docs/`.
3. Keep analysis notebooks/scripts in `analysis/` and `scripts/`.

## Proposed Structure
- `analysis/` — notebooks and exploratory analyses
- `scripts/` — reusable scripts and pipelines
- `data/` — raw/processed data (gitignored)
- `docs/` — notes, data dictionaries, references
- `figures/` — generated plots and figures

## Current Workflow
The analysis is driven by notebooks in `analysis/`:
- `analysis/00-data-wrangling.ipynb` — load `spots.pkl`, build `spots_df`, export per-section CSVs
- `analysis/01-run-baysor.ipynb` — run Baysor on each section CSV, writing outputs to each section’s `m20_s31/` folder
- `analysis/02-baysor-to-h5ad.ipynb` — build per-section `.h5ad` files from Baysor outputs
- `analysis/03-single-cell-workflow.ipynb` — concatenate per-section `.h5ad` files and run a standard Scanpy workflow

## Data Layout (Expected)
- `/Volumes/processing2/nature-dev-mouse-reanalysis/data/section_*/spots.csv`
- `/Volumes/processing2/nature-dev-mouse-reanalysis/data/section_*/m20_s31/` (Baysor outputs)
- `/Volumes/processing2/nature-dev-mouse-reanalysis/data/h5ad/` (per-section and concatenated `.h5ad`)

## Notes
This is a starting scaffold; adjust folders as the project takes shape.
