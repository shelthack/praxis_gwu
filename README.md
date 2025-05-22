# praxis_gwu
Private repo for my GWU doctoral praxis “Leveraging AutoML for Advanced Network‑Traffic Analysis &amp; Intrusion Detection.” Holds notebooks, code, models, and appendix artifacts. Will become public after my 2025 defense to foster open, reproducible cybersecurity + AutoML research.

# praxis_gwu

*Leveraging AutoML for Advanced Network‑Traffic Analysis and Intrusion Detection*  
Doctoral Praxis – George Washington University, School of Engineering & Applied Science  
Author: **Chibuike Abana** (D.Eng. Candidate, Cybersecurity Analytics)  

---

## Overview
This repository hosts the full research artefacts behind my doctoral praxis.  
It includes:

- **Jupyter Notebooks** used to clean data, engineer features, and train/evaluate models across AutoML platforms (AutoGluon, AWS Autopilot, Azure AutoML).  
- **Source Code (`src/`)** for custom preprocessing, metric utilities, deployment scripts, and evaluation helpers.  
- **Datasets / Partitions (`data/`)** — sanitized splits of the corrected CSE‑CIC‑IDS2018 dataset plus metadata describing resampling procedures.  
- **Trained Models (`models/`)** — serialized model artefacts and configuration files.  
- **Experiment Logs (`artifacts/`)** containing output summaries, confusion matrices, and detailed metrics used in Chapters 3–4.  
- **Appendix Material (`docs/appendix/`)** – PDF/Markdown exports cross‑referenced in the dissertation’s Appendix.  

Everything you need to reproduce results or extend the work is here.

---

## Repository structure


Large binary artefacts are tracked with **Git LFS** to keep clone size reasonable.

---

## Quick‑start

```bash
# 1. Clone (with LFS) and create conda env
git clone --recurse-submodules https://github.com/<user>/praxis_gwu.git
cd praxis_gwu
conda env create -f environment.yml
conda activate praxis-gwu

# 2. Launch JupyterLab
jupyter lab
