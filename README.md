# praxis_gwu
Private repo for my GWU doctoral praxis “Leveraging AutoML for Advanced Network‑Traffic Analysis &amp; Intrusion Detection.” Holds notebooks, code, models, and appendix artifacts. Will become public after my 2025 defense to foster open, reproducible cybersecurity + AutoML research.

# praxis_gwu

*Leveraging AutoML for Advanced Network Traffic Analysis and Intrusion Detection by Enhancing Security with a Multi-Feature IDS Dataset![image](https://github.com/user-attachments/assets/13f4a561-65d5-4a47-a7f6-a1c90aa15877)*  
Doctoral Praxis – George Washington University, School of Engineering & Applied Science  
Author: **Chibuike Abana** (D.Eng. Candidate, Cybersecurity Analytics)  

---

## Overview
This repository hosts the full research artefacts behind my doctoral praxis.  
It includes:

- **Jupyter Notebooks** used to clean data, engineer features, and train/evaluate models across AutoML platforms (AutoGluon, AWS Autopilot, Azure AutoML).  
- **Datasets / Partitions (`data/`)** — sanitized splits of the corrected CSE‑CIC‑IDS2018 dataset plus metadata describing resampling procedures.  
- **Trained Models (`models/`)** — serialized model artefacts and configuration files.  
- **Experiment Logs (`Research Metrics/`)** containing output summaries, confusion matrices, and detailed metrics used in Chapters 3–4.  
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
Abana, C. S. (2025). Leveraging AutoML for Advanced Network Traffic Analysis and Intrusion Detection by Enhancing Security With a Multi-Feature IDS Dataset (Order No. 32166548). Available from Dissertations & Theses @ George Washington University - WRLC; ProQuest Dissertations & Theses Global. (3233907683). https://www.proquest.com/dissertations-theses/leveraging-automl-advanced-network-traffic/docview/3233907683/se-2
```

### BibTeX
@phdthesis{
author={Abana,Chibuike S.},
year={2025},
title={Leveraging AutoML for Advanced Network Traffic Analysis and Intrusion Detection by Enhancing Security With a Multi-Feature IDS Dataset},
journal={ProQuest Dissertations and Theses},
pages={179},
note={Copyright - Database copyright ProQuest LLC; ProQuest does not claim copyright in the individual underlying works; Last updated - 2025-09-03},
abstract={This research explores how AutoML enhances network-based intrusion detection by reducing false alarms, eliminating manual tuning, and enhancing model adaptability. AutoML automates key machine learning processes such as preprocessing, algorithm selection, feature engineering, and hyperparameter tuning, thereby improving the efficiency and detection accuracy of IDS.The research employs an enhanced, multi-feature version of the CSE-CIC-IDS2018 dataset. Comprehensive preprocessing was undertaken to eliminate issues like missing values, duplicate records, mislabeling, and irrelevant features. To address severe class imbalance, a multi-phase resampling strategy was employed, combining undersampling, SMOTE, and SMOTEENN, which improved the representation of the minority class.Three AutoML platforms AutoGluon, AWS Autopilot, and Azure AutoML were evaluated using stratified sampling with consistent validation and testing sets. Model performance was measured using metrics such as accuracy, balanced accuracy, precision, recall, F1-score, false positive rate (FPR), and Matthews Correlation Coefficient (MCC).All frameworks achieved exceptional results, with accuracy exceeding 0.99999, balanced accuracy above 0.99980, F1-score, precision, and recall above 0.99999, and MCC above 0.99995, alongside near-zero false positive rates. Statistical validation using the non-parametric Mann-Whitney U test confirmed that the proposed AutoML models achieved a statistically significant improvement in accuracy (p = 0.002), a statistically significant reduction in FPR (p = 0.004), and a statistically significant reduction in model development time (p = 0.014) compared to benchmark studies. ROC and precision-recall curves yielded perfect AUC and AP scores of 1.00.The results show that the proposed AutoML models make intrusion detection better, increase accuracy, shorten development time, and make it easier to scale IDS deployment. These findings highlight AutoML's practical value for organizations looking to rapidly implement adaptable and accurate intrusion detection solutions.},
keywords={Automated Machine Learning; Class imbalance; Cybersecurity; Intrusion detection system; Network traffic analysis; Computer science; Engineering; Information technology; 0489:Information Technology; 0537:Engineering; 0984:Computer science},
isbn={9798288883750},
language={English},
url={https://www.proquest.com/dissertations-theses/leveraging-automl-advanced-network-traffic/docview/3233907683/se-2},
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


