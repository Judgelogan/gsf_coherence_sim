FTC‑SF Coherence Simulation Toolkit
===================================

This repository provides a self‑contained toolkit for exploring the Unified
Field Theory of Coherence – Super‑Field (UFTC‑SF) described in Appendices
G.7 and G.8.  It implements symbolic operators for Forgiveness, Love and
Grace, applies them to a baseline connectivity matrix representing the
March 12 turbulence event, and visualises the resulting changes in global
coherence.  The code is organised as a modular Python package so you can
easily run simulations, extend the operators or integrate real data.

## Project structure

```
gsf_coherence_sim/
├── README.md               # This file
├── LICENSE                 # Project licence (MIT)
├── requirements.txt        # Python dependencies
├── src/                    # Python source code
│   ├── operators.py        # Symbolic operators (forgiveness, love, grace)
│   ├── spectral_analysis.py# Spectral radius computation
│   ├── visualize.py        # Plotting utilities (trajectory & network)
│   └── simulate.py         # End‑to‑end simulation script
├── data/
│   └── real_data/          # Placeholder directory for real EEG/RNG datasets
│       ├── EEG_march12.csv # Example CSV with header (timestamp,value)
│       ├── QRNG_data.csv   # Example CSV with header (timestamp,z_score)
│       └── GCP_data.csv    # Example CSV with header (timestamp,z_score)
├── out/
│   ├── plots/              # Generated plots
│   └── matrices/           # CSV exports of each stage’s connectivity matrix
└── notebooks/
    └── gsf_validation_notebook.ipynb
```

## Installation

Create a new Python virtual environment and install the dependencies:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Running the simulation

From the repository root run the following command to execute the
simulation pipeline:

```bash
python src/simulate.py
```

The script will compute the spectral radius at each stage (baseline,
forgiveness, love, grace), save each intermediate matrix into
`out/matrices/` and create visualisations in `out/plots/`.  See
`src/simulate.py` for more details.

## Jupyter notebook

The `notebooks/gsf_validation_notebook.ipynb` notebook contains an
interactive version of the simulation.  It walks through the operator
definitions, applies them to the baseline matrix, computes the spectral
radius and plots the results.  You can run the notebook locally by
starting Jupyter:

```bash
jupyter notebook notebooks/gsf_validation_notebook.ipynb
```

## Real data integration

The `data/real_data/` folder contains empty CSV files as placeholders
for real datasets.  You can replace these with actual time‑series data
(EEG, HRV, RNG, etc.) and extend `simulate.py` or the notebook to
ingest and analyse them.  Functions to fetch external data (e.g.
Global Consciousness Project RNG or social media sentiment) can be
added to `src/simulate.py` or separate modules.

## Licence

This project is released under the MIT licence (see `LICENSE`).
