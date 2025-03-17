# Master Thesis - Rainfall-Runoff and Reservoir Modeling

This repository contains the Python scripts and data analysis workflows developed for my master thesis project. The main focus is the modeling and analysis of rainfall-runoff processes, reservoir management, and the impact of different tank volumes on water flow and memory effects using Hurst exponent analysis.

---

## Repository Structure

- `Main_Yacine`: Main script for data processing and modeling. This includes data integration, runoff simulations, calibration, and model performance evaluation.
- `Rain`: Precipitation data processing, cleaning, and modeling for runoff and flow analysis.
- `Reservoir`: Long-term simulation with different reservoir configurations, including Hurst exponent calculations to analyze memory effects.

---

## Prerequisites

- Python 3.8+
- Libraries:
  - numpy
  - pandas
  - matplotlib
  - scipy
  - bokeh

You can install the required libraries using:

pip install numpy pandas matplotlib scipy bokeh


---

## Data Requirements

The scripts load `.pkl` files containing time series data for:
- Precipitation (MeteoSwiss, Pluviometer data)
- River level and flow rate (Triades data)
- Hydrique model simulation results
- Wind data (optional, for advanced analysis)

Data files should be placed in the same directory as the scripts unless otherwise specified.

---

## Description of Scripts

### 1. `Main_Yacine`
- **Purpose**: Integrates multiple datasets, processes precipitation and discharge data, and runs the hydrological model for Swisstech subcatchment.This file contain all the different analysis (failure rate, runoff etc...)
- **Functions**:
  - Precipitation and discharge data visualization
  - Hydrological modeling with soil and tank reservoirs
  - Model calibration against observed data
  - Evaluation of tank performance and failure rates
- **Outputs**:
  - Time series plots (matplotlib & bokeh)
  - Failure rate vs. tank volume analysis
  - Hurst exponent evaluation on runoff

### 2. `Rain`
- **Purpose**: Prepares and processes precipitation and river level data for calibration and validation of the runoff model.
- **Steps**:
  - Conversion from `.csv` to `.pkl`
  - Cleaning and renaming columns
  - Visualization of precipitation and water level
  - Flow rate conversion from water levels (Triades outlet)
  - Volume calculation under flow rate curves

### 3. `Reservoir`
- **Purpose**: Analyzes the impact of reservoir (tank) size on runoff stability and memory effect.
- **Key analyses**:
  - Hurst exponent estimation on precipitation and runoff data
  - Different tank sizes (100 to 2500 m³) and their effect on flow stability
  - Visualization of R/S analysis and regression for Hurst estimation
  - Comparison between different scenarios (with and without tanks)

---

## How to Run

1. Place all data files in the correct paths.
2. Run each script in order:
   - `Rain` to process input data
   - `Main_Yacine` to integrate datasets and run the model
   - `Reservoir` to analyze Hurst exponents and tank effects
3. Plots and outputs will be generated in the `plot/` directory or shown directly.

---

## Key Results

- Runoff simulations calibrated with Triades flow data
- Tank management reduces peak flow and increases system memory (Hurst exponent increases with tank volume)
- Data-driven recommendations for optimal tank size to achieve a balance between storage capacity and failure rates

---

## File Outputs

- `.pkl` files: Processed datasets and model outputs
- `.png` images: Plots of flow rates, failure rates, Hurst exponent analysis
- `combined_Qout.pkl`: Combined runoff scenarios for Hurst analysis

---

## Author

Yacine M'Hamdi - Master Thesis Project 2025
