# ⚡ Smart Building HVAC Energy Optimizer & Peak Load Forecaster

> **Short-Term Electricity Usage Forecasting & Dynamic Thermal Comfort Control Engine**

---

## 📌 Context & Problem
Commercial buildings, university campuses, and educational complexes frequently struggle with unpredictable electricity demand spikes and high utility bills. 

### Key Challenges:
1. **Unthrottled Baseline Demand:** Central HVAC systems often run continuously at 100% capacity during operating hours, wasting massive amounts of energy on empty classrooms, conference halls, and lab wings.
2. **Penalizing Peak Demand Charges:** Utility providers charge severe financial penalties based on the highest peak load ($\text{kW}$) recorded in a billing cycle.
3. **Over-Cooling & Student Discomfort:** Fixed AC temperature setpoints ignore outdoor weather transitions, causing indoor spaces to become uncomfortably cold and leading to student fatigue and body thermal shock.

---

## 💡 Solution Overview
This project delivers an intelligent, short-term load forecasting engine that integrates **scheduled facility occupancy profiles** with **historical meteorological datasets** to optimize central HVAC damper controls and temperature setpoints.

### Core Features:
- **Occupancy-Driven Demand Modeling:** Converts structured timetable schedules into hourly student counts and sensible human heat loads ($100\,\text{W/person}$).
- **Zone-Level Airflow Control:** Dynamically commands motorized duct dampers to throttle airflow down to 20% maintenance capacity during vacant time slots.
- **Climate-Adaptive Setpoints:** Integrates 5-year historical weather averages and regional guidelines (such as BEE $24^\circ\text{C}$ baseline standards) to adjust target temperatures based on outdoor conditions, fan wind-chill effects, and thermal shock prevention ($\le 12^\circ\text{C}$ delta).
- **Error Measurement Suite:** Calculates real-time forecast validation metrics including **MAE** ($\text{kW}$), **RMSE** ($\text{kW}$), and **MAPE** ($\%$) to measure predictive accuracy against unoptimized baselines.

---

## 📊 Performance Metrics (Summer Baseline Simulation)

| Metric | Unoptimized Baseline | Timetable & Climate Optimized | Impact / Reduction |
| :--- | :--- | :--- | :--- |
| **Peak Electrical Demand** | $168.0\,\text{kW}$ | $161.6\,\text{kW}$ | **$6.4\,\text{kW}$ Peak Demand Shaved** |
| **Daily HVAC Consumption** | $1,680.0\,\text{kWh}$ | $1,247.8\,\text{kWh}$ | **$432.2\,\text{kWh}$ Daily Saved (~25.7%)** |

### Forecast Evaluation Metrics:
- **Mean Absolute Error (MAE):** $43.22\,\text{kW}$
- **Root Mean Squared Error (RMSE):** $53.52\,\text{kW}$
- **Mean Absolute Percentage Error (MAPE):** $29.75\%$

---

## 🛠️ Architecture & Technology Stack
- **Core Engine & Data Pipeline:** Python, Pandas, NumPy
- **Thermal Physics Model:** Sensible Heat Equations, Cooling Degree Factor, BEE Comfort Guidelines
- **Predictive Data Contract:** Structured JSON timeline output (`forecast_data.json`)
- **UI & Visualization Layer:** React / Streamlit Dashboard with real-time KPI cards and time-series demand charts
- **AI Operations Agent:** Gemini API via Google AI Studio for automated facility operator instructions

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Required libraries: `pandas`, `numpy`

### Installation & Execution
```bash
# Clone the repository
git clone [https://github.com/YOUR_USERNAME/smart-hvac-energy-optimizer.git](https://github.com/YOUR_USERNAME/smart-hvac-energy-optimizer.git)

# Navigate to the workspace folder
cd smart-hvac-energy-optimizer

# Execute the forecasting & thermal engine
python hvac_simulation.py
