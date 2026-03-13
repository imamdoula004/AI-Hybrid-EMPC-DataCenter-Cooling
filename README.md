# AI-Enhanced Data Driven Hybrid Economic Model Predictive Control

Official Digital Twin Simulation and Control Code for the IEEE research manuscript:

**"AI-Enhanced Data Driven Hybrid Economic Model Predictive Control with LSTM Forecasting and PID Supervision for Secure, Cost and Carbon Optimal Data Center Cooling."**

---

# 📖 Project Overview

Modern data centers consume enormous amounts of energy, with **cooling systems responsible for up to 40% of total facility power consumption**. Traditional reactive controllers such as PID operate using short-term feedback and suffer from **operational myopia**: they cannot anticipate future thermal workloads or incorporate dynamic grid signals such as electricity pricing and carbon intensity.

This repository contains the **complete digital twin simulation environment** used to validate the **AI-Hybrid-EMPC architecture** for intelligent data center cooling optimization.

The framework combines **machine learning forecasting, predictive optimization, cybersecurity resilience, and classical control stability** to create a robust cooling management strategy.

---

# ⚙️ Core Architecture

The proposed framework integrates four main components:

### 1. Deep Learning Forecasting
A **3-layer Bidirectional LSTM network** predicts:

- future thermal workload
- electricity demand
- grid carbon intensity

over a **24-hour receding horizon**.

These forecasts allow the controller to proactively adjust cooling strategies before thermal stress occurs.

---

### 2. Economic Model Predictive Control (EMPC)

A **tri-objective EMPC optimization algorithm** determines optimal cooling actions by minimizing:

- electricity cost
- Scope 2 carbon emissions
- thermal constraint violations based on ASHRAE standards

This predictive optimization operates continuously across the simulation horizon.

---

### 3. Cyber-Physical Security Layer

The control system includes a **min-max robust defense mechanism** designed to mitigate **False Data Injection (FDI) attacks** targeting grid communication interfaces such as **OpenADR-based energy signals**.

The framework detects abnormal signals and maintains safe cooling operation under adversarial conditions.

---

### 4. Edge PID Supervision

To ensure deterministic safety, a **fallback PID controller** supervises the optimization layer.

If communication or forecasting fails, the PID controller maintains **stable cooling operation and thermal constraint satisfaction**.

---

# 🏆 Key Performance Indicators

Performance was evaluated using a **7-day (168-hour) multi-seed digital twin simulation**.

Results demonstrate substantial improvements compared with a traditional PID baseline:

| Metric | Improvement |
|------|------|
| Cooling Power Consumption | **78.4% reduction** |
| Operational Electricity Cost | **78.6% reduction** |
| Scope 2 Carbon Emissions | **78.5% reduction** |
| Cyber-Attack Recovery | **~25 control steps average recovery** |

The system maintains **thermal stability even during sustained 3-hour cyber-physical attacks**.

---

# 📂 Repository Structure

```
├── data/                                   # Real-world telemetry datasets
│   ├── data_center_cold_source_control.csv
│   ├── electricity_load_forecasting_cleaned.csv
│   └── energy_environment_data_cleaned.csv
│
├── Hybrid_EMPC_LSTM_Simulation_Code.ipynb  # Main simulation notebook
│
├── README.md                               # Documentation
└── LICENSE                                 # MIT License
```

---

# 🚀 Getting Started

## Prerequisites

Install the following Python libraries:

```
numpy >= 1.26
pandas
tensorflow >= 2.15
scipy
matplotlib
```

---

# ▶ Running the Simulation

### Step 1 — Clone the Repository

```
git clone https://github.com/YourUsername/AI-Hybrid-EMPC-DataCenter-Cooling.git
cd AI-Hybrid-EMPC-DataCenter-Cooling
```

---

### Step 2 — Prepare the Dataset Directory

Place the required CSV datasets into:

```
/data/
```

Expected files:

```
data_center_cold_source_control.csv
electricity_load_forecasting_cleaned.csv
energy_environment_data_cleaned.csv
```

If the datasets are not detected, the notebook automatically **generates statistically equivalent synthetic telemetry** so that the mathematical models and controller remain executable.

---

### Step 3 — Run the Simulation Notebook

Open the notebook:

```
Hybrid_EMPC_LSTM_Simulation_Code.ipynb
```

Run it using:

- **Google Colab**
- **Jupyter Notebook**
- **JupyterLab**

Execute all cells sequentially.

---

# 🔬 Reproducibility

To ensure deterministic reproducibility, all experiments use **fixed random seeds (42)** for:

- NumPy
- TensorFlow
- Python random

This guarantees exact replication of the **multi-seed KPI results reported in the manuscript**.

---

# 📊 Datasets

The digital twin environment integrates multiple real-world datasets for electricity demand, environmental signals, and cooling control telemetry.

Primary datasets used in this project:

**Energy and Environmental Data**

https://www.kaggle.com/datasets/mertkont/energy-and-environment-data

**Electricity Consumption Dataset**

https://www.kaggle.com/datasets/littlebaldturtle/electricity-consumption

**Electricity Load Forecasting Dataset**

https://www.kaggle.com/datasets/saurabhshahane/electricity-load-forecasting

**Data Center Cold Source Control Dataset**

https://www.kaggle.com/datasets/programmer3/data-center-cold-source-control-dataset

These datasets provide realistic signals for:

- electricity load forecasting
- grid behavior
- thermal dynamics
- cooling system telemetry

---

# 🙏 Acknowledgements

We gratefully acknowledge the dataset contributors and the Kaggle community for providing publicly available datasets that enable research in **energy systems, machine learning forecasting, and sustainable data center operations**.

Their work enables reproducible experimentation and benchmarking in emerging **AI-driven energy optimization research**.

---

# 📝 Citation

If you use this code or digital twin environment in academic work, please cite:

```
@inproceedings{doula2024aihybridempc,
  title={AI-Enhanced Data Driven Hybrid Economic Model Predictive Control with LSTM Forecasting and PID Supervision for Secure, Cost and Carbon Optimal Data Center Cooling},
  author={Doula, Imam Ud and Rahman, Adrita and Fatima, Samiha},
  booktitle={IEEE Conference (To Be Updated)},
  year={2026}
}
```

---

# 🛡 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for details.
