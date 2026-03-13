AI-Enhanced Data Driven Hybrid Economic Model Predictive Control

Official Digital Twin Simulation and Control Code for the IEEE manuscript:

"AI-Enhanced Data Driven Hybrid Economic Model Predictive Control with LSTM Forecasting and PID Supervision for Secure, Cost and Carbon Optimal Data Center Cooling."

📖 Project Overview

Data center cooling consumes up to 40% of total facility energy. Traditional reactive controllers (like PID) suffer from "operational myopia"—they cannot anticipate heat surges and ignore dynamic grid signals like real-time electricity pricing and carbon intensity.

This repository contains the complete, multi-seed digital twin environment used to empirically validate the AI-Hybrid-EMPC architecture. The framework integrates:

Deep Learning Forecasting: A 3-layer Bidirectional LSTM network anticipating highly stochastic thermal workloads and grid carbon intensity over a 24-hour receding horizon.

Tri-Objective Optimization: An Economic Model Predictive Control (EMPC) algorithm minimizing utility costs, formalized Scope 2 carbon emissions, and strict ASHRAE thermal safety violations.

Min-Max Robust Security: A mathematical shield defending the cooling infrastructure against stealthy False Data Injection (FDI) attacks targeting OpenADR 3.0 grid APIs.

Edge PID Supervision: A deterministic fallback algorithm ensuring absolute operational stability during API or network failures.

🏆 Key Performance Indicators

Evaluated across a 7-day, 168-hour multi-seed simulation using real-world datasets, the AI-Hybrid-EMPC achieved:

78.4% absolute reduction in total cooling power consumption vs. the PID baseline.

78.6% absolute reduction in operational utility expenditure.

78.5% absolute reduction in formal Scope 2 Carbon Emissions (kg CO₂).

Rapid constraint recovery (average 25 steps) during sustained 3-hour cyber-physical FDI attacks.

📂 Repository Structure

.
├── data/                               # Directory for real-world telemetry CSVs
│   ├── data_center_cold_source_control.csv
│   ├── electricity_load_forecasting_cleaned.csv
│   └── energy_environment_data_cleaned.csv
├── Paper1point5_Simulation.ipynb       # Main Jupyter/Colab Notebook with the complete framework
├── README.md                           # Project documentation
└── LICENSE                             # MIT License


🚀 Getting Started and Reproducibility

Prerequisites

To run the simulation locally or on Google Colab, ensure you have the following dependencies installed:

numpy >= 1.26

pandas

tensorflow >= 2.15

scipy

matplotlib

How to Run

Clone this repository:

git clone [https://github.com/YourUsername/AI-Hybrid-EMPC-DataCenter-Cooling.git](https://github.com/YourUsername/AI-Hybrid-EMPC-DataCenter-Cooling.git)
cd AI-Hybrid-EMPC-DataCenter-Cooling


Data Setup: Place the required datasets (listed above) into the /data/ directory. (Note: If the datasets are not found, the notebook is programmed to gracefully fall back to generating statistically equivalent synthetic telemetry to ensure the mathematical models still execute).

Open Paper1point5_Simulation.ipynb in Google Colab or Jupyter Notebook.

Execute all cells sequentially.

Reproducibility Note: All random seeds (numpy, tensorflow, random) are strictly hard-coded to 42 at the top of the notebook to guarantee exact deterministic replication of the multi-seed averages reported in Table II of the manuscript.

📝 Citation

If you use this code or digital twin environment in your research, please cite our paper:

@inproceedings{doula2024aihybridempc,
  title={AI-Enhanced Data Driven Hybrid Economic Model Predictive Control with LSTM Forecasting and PID Supervision for Secure, Cost and Carbon Optimal Data Center Cooling},
  author={Doula, Imam Ud and Rahman, Adrita and Fatima, Samiha},
  booktitle={IEEE Conference (To Be Updated)},
  year={2026}
}


🛡️ License

This project is licensed under the MIT License - see the LICENSE file for details.
