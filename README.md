# Utsira-pv-sizing
Utsira PV and battery sizing

Work in progress (UiS project TNU100, Aug–Dec 2026, supervisors: Mohammad Mansouri, UiS; Aleksi Mankonen, LUT).

Goal: size a PV plant with battery storage to cover the annual electricity demand of Utsira, a Norwegian island municipality (about 220 inhabitants, 3.29 GWh in 2025).

Data: 8,760 hourly demand values for 2025 (UtsiraHC2025_1.xlsx); hourly solar and temperature data from Open-Meteo.

Method: hourly PV output with temperature and system losses for several panel tilts; row-spacing and land-use estimates; hourly battery simulation with state-of-charge limits and efficiencies. pvlib is used for solar position.

Status: preliminary. Known issue being fixed: irradiance for different tilts must come from the same location. Results will be added when verified.
