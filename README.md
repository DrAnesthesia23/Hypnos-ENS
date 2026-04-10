# Hypnos-ENS
Hypnos-ENS: Project Documentation and Resources  This repository contains all information and resources related to the Hypnos-ENS project. It is designed to provide open access to project data, documentation, and updates for anyone interested in our work.

Hypnos-ENS: AI-based Anesthetic Depth Prediction
Hypnos-ENS is a deep learning project developed to predict the Patient State Index (PSI) during Total Intravenous Anesthesia (TIVA) using Propofol and Remifentanil. The model is designed to assist anesthesiologists in monitoring hypnotic depth without the continuous need for processed EEG (neuromonitoring) devices in resource-limited settings.

📌 Project Overview
The model utilizes a Multitask Gated Recurrent Unit (GRU) architecture to solve two simultaneous tasks:

Regression: Continuous estimation of the current PSI value.

Classification: Prediction of the 30-second hypnotic trend (Stable, Descending, or Ascending).

Key Findings 
+1

Performance: Achieved a Global Mean Absolute Error (MAE) of 7.96 and an R² of 0.34 on an independent hold-out set.

Clinical Accuracy: High precision during the Maintenance Phase (MAE 7.26).

Bias Awareness: Minimal global bias (-0.89), with a tendency to underestimate awareness (PSI > 50) and overestimate deep anesthesia (PSI < 25).

🛠 Model Architecture
The pipeline implements several state-of-the-art deep learning techniques for medical time-series:

GRU Cells: To capture the temporal dependencies of pharmacokinetic and hemodynamic variables.

Monte Carlo Dropout: Used for uncertainty estimation, providing confidence intervals for each prediction.

Feature Engineering: 24 input variables including demographic, hemodynamic, and derived pharmacokinetic metrics (Effect-site concentrations, drug ratios, and trend derivatives).

📊 Dataset
The model was trained on a retrospective cohort from Los Cobos Medical Center (Bogotá, Colombia):

Population: 332 adult patients.
+2

Resolution: ~2.85 million temporal records at 5-second intervals.
+1

Data Split: Patient-grouped cross-validation (GroupKFold, k=5) to ensure no data leakage between training and testing sets.
+1

🚀 Getting Started
Prerequisites

Python 3.9+

NVIDIA GPU (Recommended for training)

Requirements: pip install -r requirements.txt


📜 Ethical Considerations
This study was approved by the Institutional Ethics Committee of Universidad El Bosque (Act No. CIE 2026-029) and classified as risk-free research as it involved retrospective analysis of clinical records.

✉️ Contact & Citation
Lead Researchers:

Juan Camilo Chavarro Abril

Camilo Alberto Sabogal Camargo (Corresponding author: csabogalc@unbosque.edu.co)

If you use this code in your research, please cite our manuscript:

Sabogal-Camargo CA, et al. Artificial intelligence model to predict anesthetic depth during total intravenous anesthesia: development and validation. (2026).

In case you want the original data base used in this study please contact the corresponding author
