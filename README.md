# OPV-performance-prediction

## 📘 A Data-Driven Framework for Morphology–Performance Mapping  
**Virtual Instruments, High Performance Computing, 3D Microstructures**

This repository contains the code and input data associated with the research paper:  
**"A Data-Driven Framework for Morphology–Performance Mapping: Virtual Instruments, High Performance Computing, 3D Microstructures"**, submitted to *Journal of Materials Research*.

---

## 📄 Paper  
📌 DOI / Preprint: *To be added upon publication*

---

## 🧪 What This Code Does

This code implements a two-stage modeling framework to predict organic photovoltaic (OPV) performance metrics — **J<sub>sc</sub>** and **Fill Factor (FF)** — from 3D morphology descriptors using a **Random Forest regressor**.

The full pipeline is applied independently to two material systems: **P3HT:PCBM** and **PM6:Y6**.

### 🔁 Modeling Workflow:
1. **Standardize** input features and target values.
2. **Cluster the full dataset** in joint feature–target space using KMeans (k=5).
3. **Perform a cluster-stratified train–test split** (80% train / 20% test).
4. **Run Forward Feature Selection** using only training data to minimize MSE.
5. **Train a Random Forest model** with grid search for hyperparameter tuning.
6. **Evaluate on held-out test set** with R² and MSE.
7. **Repeat the workflow across 100 random seed combinations.**
8. **Evaluate on dataset sizes of 25, 50, 100, and 150 morphologies.**

---

## 🚀 How to Run the Code

### ▶️ Option 1: Run on Google Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/your-repo/blob/main/morphology_rf_feature_selection.ipynb)

> No setup needed — upload the input files when prompted.

### 💻 Option 2: Run Locally

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
pip install -r requirements.txt
jupyter notebook morphology_rf_feature_selection.ipynb

## ⚙️ Notebook Instructions

In # Load data, change the filename based on your material and target.
In # Separate features and target, select your desired target (Jsc or FF) and comment out the others.
In # Set up RandomForestRegressor, set n_estimators depending on dataset size:
ex:
50 morphologies: [2, 5, 10, 20, 25, 30, 40, 50]
150 morphologies: [2, 5, ..., 150]
In # Plot prediction, choose the right metric to visualize and comment out the other.


## 📂 Repository Structure
📁 input/
 ├── Features_jsc_P3HT_PCBM.csv
 ├── Features_jsc_PM6_Y6.csv
 ├── Features_FF_P3HT_PCBM.csv
 ├── Features_FF_PM6_Y6.csv
 ├── Random_seeds_jsc_P3HT_PCBM.csv
 ├── Random_seeds_jsc_PM6_Y6.csv
 ├── Random_seeds_FF_P3HT_PCBM.csv
 ├── Random_seeds_FF_PM6_Y6.csv
 ├── config_P3HT_PCBM.txt
 └── config_PM6_Y6.txt
📓 morphology_rf_feature_selection.ipynb
📄 requirements.txt
📘 README.md


## 📥 Input Files Description
### 📊 Morphology Descriptor CSVs (for model training)
Files with 150 samples each, 17 features, and one target (Jsc or FF). Use subsets of 25, 50, or 100 morphologies if needed.

### 🎻 Random Seed CSVs (for Violin Plots)
These store R² or MSE scores across 100 random seeds.
Used to generate violin plots (plotting code not included).

### 🛠️ Config Files
Text files with simulation parameters (mobility, V<sub>oc</sub>, solver settings, etc.) used by XDD for each material system.

## 📊 Output
Feature selection summary
Final model performance on test set (R² and MSE)
Feature importance plots
Parity plots for predictions

## 🤝 Citation
Please cite the paper once it’s published. Citation details will be added here.

## 📬 Contact
marjansd@iastate.edu
https://github.com/marjansd
