# Utsira PV and battery sizing



Work in progress (UiS project TNU100, Aug–Dec 2026; supervisors: Mohammad Mansouri, UiS; Aleksi Mankonen, LUT).



## Goal

Size a PV plant with battery storage to cover the annual electricity demand of Utsira, a Norwegian island municipality (about 220 inhabitants, 3.29 GWh in 2025).



## Data

- **Demand:** 8,760 hourly values for 2025 in `UtsiraHC2025_1.xlsx`.

- **Weather and sunlight:** hourly irradiance on tilted planes and air temperature from Open-Meteo (reanalysis data) for 59.297 N, 4.898 E, 19 m, year 2025. There are 26 CSV files: tilts 0° to 60° in 5° steps, facing south (`open-meteo-59.30N4.90E19m{tilt}tilt.csv`) and north (`open-meteo-59.30N4.90E19m-{tilt}tilt.csv`).



## Method (`Scaling_first.ipynb`)

Each step has a note in the notebook that explains why, the formulas and the assumptions.

1. Hourly PV power per m² for each tilt (efficiency with a temperature coefficient).

2. Single-diode module model (De Soto, through pvlib) with Faiman cell temperature, and DC cable loss for one string.

3. Row spacing against shading at the winter solstice, panel area for the yearly demand, whole modules and strings, and a land-use index to compare tilts.

4. Battery sizing from the cumulative energy balance, with a loss iteration.

5. Battery temperature model: thermal inertia, temperature-dependent efficiency and self-discharge, and a charging limit at low temperature.

6. Plots of the four most critical weeks.



## Status

Preliminary. The design tilt is 0° (flat), chosen for the smallest land-use index. The battery temperature parameters are assumptions until manufacturer data is available. Final results will be added after verification.



## Run

1. Install the packages: `pip install -r requirements.txt`

2. Open `Scaling_first.ipynb` in Jupyter from this folder (the data files must be in the same folder).

3. Run **Kernel → Restart & Run All**. It takes about 1 to 2 minutes.



## Author

Enkhbayar Enkh-Orgil, LUT University (exchange studies at the University of Stavanger).

