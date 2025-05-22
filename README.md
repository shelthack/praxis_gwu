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
git clone --recurse-submodules https://github.com/shelthack/praxis_gwu.git
cd praxis_gwu
conda env create -f environment.yml
conda activate praxis-gwu

# 2. Launch JupyterLab
jupyter lab

```

## License

The code is released under the MIT License to maximise reuse, with one condition:

***Citation Required – If you build upon this work (code, data, or results), you must cite the original praxis (see below).***

The dataset portion (data/) inherits its own upstream licenses and must be used in accordance with CSE‑CIC terms.



## How to cite

Please cite both the praxis and this repository. Example formats:

### APA 7

```
Abana, C. S. (2025). Leveraging AutoML for Advanced Network‑Traffic Analysis and Intrusion Detection (Doctoral praxis, George Washington University). https://doi.org/10.XXXXX/zenodo.XXXXXX
```

### BibTeX

@phdthesis{YourLastName2025Praxis,
  author       = {Chibuike S. Abana},
  title        = {Leveraging AutoML for Advanced Network-Traffic Analysis and Intrusion Detection},
  school       = {George Washington University},
  year         = 2025,
  doi          = {10.XXXXX/zenodo.XXXXXX},
  note         = {Code and artefacts available at https://github.com/shelthack/praxis_gwu}
}
> A machine‑readable CITATION.cff file is provided so GitHub can auto‑generate proper citation snippets.

## Contributing

At present, the repository is read‑only. Once public, pull requests are welcome for:
	•	Reproducibility fixes (environment, paths, small bugs)
	•	Extensions (additional datasets, concept‑drift experiments, deployment scripts)

Please open an issue first to discuss major changes.

## Contact

Questions, suggestions, or collaboration ideas?
Email: preciouschydos@gmail.com   


