# AI-Enhanced Data Driven Hybrid Economic Model Predictive Control

Official Digital Twin Simulation and Control Code for the IEEE manuscript:

**"AI-Enhanced Data Driven Hybrid Economic Model Predictive Control with LSTM Forecasting and PID Supervision for Secure, Cost and Carbon Optimal Data Center Cooling."**

---

# 📖 Project Overview

Data center cooling consumes up to **40% of total facility energy**. Traditional reactive controllers (like PID) suffer from **operational myopia**: they cannot anticipate heat surges and ignore dynamic grid signals such as real-time electricity pricing and carbon intensity.

This repository contains the **complete multi-seed digital twin environment** used to empirically validate the **AI-Hybrid-EMPC architecture**.

The framework integrates:

### Deep Learning Forecasting
A **3-layer Bidirectional LSTM network** anticipating highly stochastic thermal workloads and grid carbon intensity over a **24-hour receding horizon**.

### Tri-Objective Optimization
An **Economic Model Predictive Control (EMPC)** algorithm minimizing:

- Utility cost
- Formalized **Scope 2 carbon emissions**
- **ASHRAE thermal safety violations**

### Min-Max Robust Security
A **mathematical security shield** defending the cooling infrastructure against **stealthy False Data Injection (FDI) attacks** targeting **OpenADR 3.0 grid APIs**.

### Edge PID Supervision
A deterministic **fallback PID controller** ensuring **operational stability** during **API failures or network outages**.

---

# 🏆 Key Performance Indicators

Evaluated across a **7-day (168-hour) multi-seed digital twin simulation** using real-world datasets.

The **AI-Hybrid-EMPC controller achieved:**

- **78.4% reduction** in total cooling power consumption vs PID baseline
- **78.6% reduction** in operational electricity expenditure
- **78.5% reduction** in formal **Scope 2 carbon emissions (kg CO₂)**
- **Rapid constraint recovery** during sustained **3-hour cyber-physical FDI attacks**  
  *(average recovery: 25 control steps)*

---

# 📂 Repository Structure

```
├── data/                                   # Directory for real-world telemetry CSVs
│   ├── data_center_cold_source_control.csv
│   ├── electricity_load_forecasting_cleaned.csv
│   └── energy_environment_data_cleaned.csv
│
├── Hybrid_EMPC_LSTM_Simulation_Code.ipynb  # Main Jupyter/Colab notebook
│                                           # Complete forecasting + control framework
│
├── README.md                               # Project documentation
└── LICENSE                                 # MIT License
```

---

# 🚀 Getting Started

## Prerequisites

To run the simulation locally or on **Google Colab**, install the following dependencies:

```
numpy >= 1.26
pandas
tensorflow >= 2.15
scipy
matplotlib
```

---

# ▶ How to Run

### 1. Clone the Repository

```
git clone https://github.com/YourUsername/AI-Hybrid-EMPC-DataCenter-Cooling.git
cd AI-Hybrid-EMPC-DataCenter-Cooling
```

### 2. Data Setup

Place the required datasets into the `/data/` directory.

Expected files:

```
data_center_cold_source_control.csv
electricity_load_forecasting_cleaned.csv
energy_environment_data_cleaned.csv
```

**Note**

If datasets are not detected, the notebook automatically **generates statistically equivalent synthetic telemetry** so that the **control algorithms and mathematical models still execute correctly**.

---

### 3. Run the Simulation

1. Open  
   `Hybrid_EMPC_LSTM_Simulation_Code.ipynb`

2. Run inside:
   - **Google Colab**, or
   - **Jupyter Notebook**

3. Execute **all cells sequentially**.

---

# 🔬 Reproducibility Guarantee

All random seeds are **strictly fixed to `42`** for:

- `numpy`
- `tensorflow`
- `random`

This guarantees **exact deterministic replication** of the **multi-seed KPI averages reported in Table II of the manuscript**.

---

# 📝 Citation

If you use this digital twin environment in research, please cite:

```
@inproceedings{doula2024aihybridempc,
  title={AI-Enhanced Data Driven Hybrid Economic Model Predictive Control with LSTM Forecasting and PID Supervision for Secure, Cost and Carbon Optimal Data Center Cooling},
  author={Doula, Imam Ud and Rahman, Adrita and Fatima, Samiha},
  booktitle={IEEE Conference (To Be Updated)},
  year={2026}
}
```

---

# 🛡️ License

This project is licensed under the **MIT License**.

See the `LICENSE` file for details.
