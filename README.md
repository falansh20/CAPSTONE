#     Dynamic Parking Price Optimization System

Welcome to a smart-city-inspired project that reimagines how parking fees are managed. Using real-world-inspired data, streaming analytics, and demand-driven rules, this system calculates dynamic parking prices based on occupancy, traffic conditions, vehicle type, and more—all in real time.

---

##    Tech Stack

| Category         | Tools & Libraries                           |
|------------------|---------------------------------------------|
| Programming Lang | Python 3.x                                  |
| Data Engine      | [Pathway](https://pathway.com/)             |
| Data Handling    | Pandas and Other imp library of python      |
| Visualization    | Bokeh (interactive time series dashboard)   |
| Notebook/IDE     | Jupyter / Google Colab                      |
| Dataset Format   | CSV (timestamped occupancy + metadata)      |

---

## 🧠 Project Overview

This project simulates a **real-time smart parking system**. By analyzing occupancy trends, queue lengths, traffic flow, and contextual factors like holidays or special days, the system adjusts daily parking prices using demand-aware rules.

You’ll see how pricing surges on busy days, tapers on holidays, and varies based on the type of vehicle parked (bike, EV, car).

---

## 🗺️ Architecture Flow

```text
                         ┌──────────────────────┐
                         │    Parking Dataset    │
                         └─────────┬────────────┘
                                   │
                ┌──────────────────▼────────────────────┐
                │ Pathway Streaming Engine (replay_csv) │
                └─────────┬───────────┬──────────────────┘
                          │           │
                 Schema + Day Aggreg. │
                          ▼           ▼
     ┌──────────────┐   Feature    Occupancy   ┌──────────────────┐
     │ Pricing Logic│◀───────────── Reduction ◀│ Occupancy + Time │
     └─────┬────────┘   (volatility, traffic)  └──────────────────┘
           │
           ▼
  📈 Final Price Output Table
           │
           ▼
  📊 Bokeh Dashboard Visualization
