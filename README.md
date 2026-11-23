# 📈 Monte Carlo Simulation in Supply Chain Management

<p align="center">
  <img src="https://img.shields.io/badge/C%2B%2B-17-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white" alt="C++" />
  <img src="https://img.shields.io/badge/MPI-OpenMPI-003B57?style=for-the-badge" alt="MPI" />
  <img src="https://img.shields.io/badge/OpenMP-Multi--Threading-blue?style=for-the-badge" alt="OpenMP" />
  <img src="https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Terraform-Azure-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="Terraform" />
</p>

A high-performance, distributed **Monte Carlo Simulation Engine** for supply chain risk analysis and stochastic inventory optimization. Built with a **hybrid MPI + OpenMP C++ core** for parallel trial generation, an **integrated Python Random Forest analytics engine** for parameter sensitivity forecasting, and **automated Azure Terraform infrastructure** for cloud execution.

---

## 📌 Architecture & Features

1. **Hybrid Parallel Simulation Engine (`src/`)**:
   - Built with **MPI (Message Passing Interface)** for distributed inter-node execution and **OpenMP** for multi-threaded intra-node SIMD parallelization.
   - Models stochastic demand variations, lead-time uncertainty, multi-echelon holding costs, and backorder stockout risks.
2. **Predictive Analytics & Sensitivity Engine (`python/`)**:
   - Random Forest Regressor fits simulation outcome distributions to evaluate key cost drivers.
   - Generates empirical cumulative distributions, Value-at-Risk (VaR 95%), service level metrics, and feature importance rankings.
3. **Cloud Infrastructure as Code (`terraform-azure/`)**:
   - Automates provisioning of Azure compute clusters and virtual networks for scalable multi-node batch simulation jobs.

---

## 🗂️ Project Structure

```
├── src/
│   ├── mc_hybrid_openmp.cpp         # Hybrid MPI + OpenMP Monte Carlo simulation engine
│   └── mc_mpi_cpu.cpp               # Multi-process distributed MPI implementation
├── python/
│   ├── analytics_engine.py          # Random Forest ML model, summary statistics & plotting
│   ├── requirements.txt             # Python analytical library dependencies
│   └── run_complete_analysis.sh     # End-to-end execution script
├── terraform-azure/                 # Automated Azure compute infrastructure provisioning
│   ├── main.tf
│   ├── variables.tf
│   └── deploy.sh
├── requirements.txt                 # Root Python requirements
└── README.md
```

---

## ⚡ Quickstart & Usage

### 1. Python Analytics Setup

```bash
git clone https://github.com/Karthickruban/Monte-Carlo-Simulation-in-supply-chain-management.git
cd Monte-Carlo-Simulation-in-supply-chain-management
pip install -r requirements.txt
```

### 2. Compile and Run the Parallel C++ Engine

```bash
# Compile hybrid MPI + OpenMP binary
mpicxx -O3 -fopenmp src/mc_hybrid_openmp.cpp -o mc_hybrid

# Run across 4 MPI processes with multi-threading
mpirun -np 4 ./mc_hybrid
```

### 3. Run Machine Learning Sensitivity Analysis

```bash
python python/analytics_engine.py --results simulation_results.csv --params simulation_parameters.csv --all
```

---

## 👥 Contributors & Research Team

- **Vignesh V S** ([@VigneshVS2005](https://github.com/VigneshVS2005)) — Cloud orchestration, infrastructure & parallelization
- **Karthick Ruban** ([@Karthickruban](https://github.com/Karthickruban)) — Stochastic modeling, Monte Carlo algorithms & ML predictive analytics

---

## 📄 License
MIT License