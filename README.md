# OPV-performance-prediction
from pathlib import Path

readme_content = A Data-Driven Framework for Morphology–Performance Mapping  
**Virtual Instruments, High Performance Computing, 3D Microstructures**

This repository contains the code and input data associated with the research paper:  
**"A Data-Driven Framework for Morphology–Performance Mapping: Virtual Instruments, High Performance Computing, 3D Microstructures"**, submitted to *Journal of Materials Research*.

---

## 📄 Paper  
📌 DOI / Preprint: *To be added upon publication*

---

## 🧪 Code Overview

The core code performs **forward feature selection using Random Forest regression** to predict photovoltaic performance metrics (**J<sub>sc</sub>** and **FF**) from **morphology descriptors** of organic solar cells. The code supports two material systems:
- **P3HT:PCBM**
- **PM6:Y6**

> 📓 **Notebook Name: morphology_rf_feature_selection.ipynb`

---

## 📂 Repository Structure

```plaintext
📁 input/
 ├── Morphs_jsc_P3HT:PCBM.csv
 ├── Morphs_jsc_PM6:Y6.csv
 ├── Morphs_FF_P3HT:PCBM.csv
 ├── Morphs_FF_PM6:Y6.csv
 ├── Random_seeds_jsc_P3HT:PCBM.csv
 ├── Random_seeds_jsc_PM6:Y6.csv
 ├── Random_seeds_FF_P3HT:PCBM.csv
 ├── Random_seeds_FF_PM6:Y6.csv
 ├── config_P3HT:PCBM.txt
 └── config_PM6:Y6.txt
📓 morphology_performance traits predcition_RF.ipynb
📄 requirements.txt
📘 README.md
