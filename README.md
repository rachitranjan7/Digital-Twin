# Digital-Twin
# Phenotypic Digital Twin Simulator 🧬

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-EE4C2C)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)

A deep learning pipeline that builds a "phenotypic digital twin" to simulate biological progression. By analyzing longitudinal cell-free RNA (cfRNA) microarray data, this PyTorch-based LSTM model forecasts maternal gene expression trajectories across the three trimesters of pregnancy and post-partum.

## 📖 Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Key Features](#key-features)
- [Project Architecture](#project-architecture)
- [Installation & Usage](#installation--usage)
- [Results](#results)

## 🔬 Overview
Creating a digital twin in healthcare requires mapping complex, high-dimensional physiological states into predictive computational models. This project utilizes a Long Short-Term Memory (LSTM) neural network to learn the temporal signatures of cfRNA in maternal blood. By feeding the twin an initial biological state, it successfully predicts the continuous, multi-step progression of critical gene biomarkers over time.

## 📊 Dataset
This project uses the **[GSE56899](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE56899)** dataset from the NCBI Gene Expression Omnibus (GEO).
* **Data Type:** Cell-free RNA microarray expression matrix.
* **Target Phenotypes:** 4 chronological time steps (Trimester 1, Trimester 2, Trimester 3, Post Partum).
* **Input Size:** Tens of thousands of raw genetic probes, reduced via statistical selection.

## ✨ Key Features
* **Automated Data Ingestion:** Directly fetches and parses raw GEO datasets and unstructured metadata using `GEOparse`.
* **Statistical Feature Selection:** Implements Vectorized One-Way ANOVA to isolate the top 500 statistically significant genes (p < 0.1), preventing the curse of dimensionality and optimizing tensor memory.
* **Sequence-to-Sequence Modeling:** Uses a PyTorch LSTM architecture built to handle chronological 3D biological tensors `[Subjects, Time_steps, Features]`.
* **Automated Dashboarding:** Generates comprehensive, subject-specific visual comparisons between actual biological baselines and the digital twin's simulations.

## 🧠 Project Architecture

1. **Preprocessing:** Dynamic alignment of sample metadata and transposition of 2D expression matrices.
2. **Dimensionality Reduction:** Filtering features via $F$-statistics to extract only biologically relevant, time-varying biomarkers.
3. **Tensor Formatting:** Standard scaling and restructuring into sequential inputs (T1, T2, T3) and targets (T2, T3, PP).
4. **Model Training:** Training the `DigitalTwinLSTM` using Mean Squared Error (MSE) loss and the Adam optimizer.
5. **Inference & Evaluation:** Simulating full trajectories for unseen physiological states.

## 🚀 Installation & Usage

This project is optimized to run in **Google Colab** with zero local setup required.

1. Clone this repository:
   ```bash
   git clone [https://github.com/YourUsername/cfRNA-Digital-Twin.git](https://github.com/YourUsername/cfRNA-Digital-Twin.git)
   cd cfRNA-Digital-Twin

