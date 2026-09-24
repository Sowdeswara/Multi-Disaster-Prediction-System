"# Multi-Disaster Prediction System

## SIH 2026 — Problem Statement 26178

*“A resilient, AI‑powered environmental monitoring network that provides early detection, localized intelligence, and actionable alerts for floods, forest fires, pollution events, and other environmental hazards common in India, enabling authorities and communities to shift from reactive disaster response to proactive risk prevention.”*

## Current Status

> **Current proof‑of‑work stage:** Indian flood dataset collection and preliminary review completed. Preprocessing, feature engineering and model development are the next stages.

## What Has Been Completed

- SIH 26178 problem research
- India‑focused dataset identification
- Flood dataset collection
- Local dataset organization
- Preliminary dataset review
- Multi‑timescale temporal‑memory architecture concept
- Resource‑efficient edge‑processing strategy
- Multi‑hazard expansion plan (draft architecture)

## Current Focus: Flood

The flood model head is the first target. Datasets covering river discharge, water‑level telemetry, rainfall, and soil‑moisture have been gathered and inspected. Model development has not yet started.

## Dataset Sources

| Dataset | File | Source |
|---------|------|--------|
| River Discharge (manual daily) | `riverdischarge_manual_daily_cwc_tn_1950_2000.csv` | Central Water Commission (CWC) |
| River Water Level Telemetry (2021‑2025) | `rwl_tel_hr_cwc_003_2021_2025.csv` | CWC |
| River Water Level Telemetry (2021‑2025) set 006 | `rwl_tel_hr_cwc_006_2021_2025.csv` | CWC |
| Historical Water Level (1961‑1990) | `rwl_tele_hr_cwc_003_1961_1990.csv` | CWC |
| North‑East India Rainfall (1901‑2016) | `ne-India_rainfall_act_dep_1901_2016.csv` | India Meteorological Department (IMD) |
| Sub‑division Rainfall (1901‑2015) | `sub-division_rainfall_act_dep_1901-2015.csv` | IMD |
| IMD Sub‑division (2017) | `Sub_Division_IMD_2017.csv` | IMD |
| Soil Moisture Tamil Nadu 2018 | `sm_Tamilnadu_2018.csv` | Tamil Nadu State Agency |
| Soil Moisture Tamil Nadu 2020 | `sm_Tamilnadu_2020.csv` | Tamil Nadu State Agency |
| Flood Forecasting Stations Summary | `RS_Session_259_AU_420_4.csv` | CWC |
| Forest Fire Season Summary | `RS_Session_267_AU_3077_B.csv` | FMCC |
| Multi‑Hour Fire Forecast (hypothetical) | `RS_Session_270_AU_682_A_i_a.csv` | FMCC |
| Cyclone Historical Data (1891‑2016) | `cyclones-1891-2016.csv` | IMD Cyclone Archive |

All files are located under `e:\\projects\\Sih\\datasets\\raw_data`.

## Proposed Data Handling

raw environmental data → short‑term memory → medium‑term rolling features → long‑term compact summaries → compact inference representation. This hierarchy reduces the amount of historical data presented to the inference pipeline; the actual reduction percentage will be measured after preprocessing.

## Proposed Architecture

See the detailed architecture diagram in `docs/architecture/system_architecture.md`.

## Resource‑Efficient Design

- Hierarchical temporal memory
- Rolling/moving statistics
- Historical aggregation
- Event‑triggered inference where appropriate
- Shared representation for future hazard heads
- Planned model quantization for edge deployment

These design choices are intended to **reduce** memory usage, **lower** inference workload, and improve suitability for older, resource‑constrained smartphones. Quantitative benefits will be measured once the pipeline is implemented.

## Development Roadmap

**Completed**: Dataset collection and preliminary review.

**In Progress**: Flood dataset preprocessing, quality analysis, temporal alignment, feature engineering, target construction.

**Planned**: Flood model training, evaluation, edge optimisation.

**Future**: Additional hazard models and edge deployment.

## Proof‑of‑Work Status

### Completed
- Dataset collection and preliminary review.

### In Progress
- Flood preprocessing and feature engineering.

### Planned
- Flood model training and evaluation.

### Future
- Additional hazard models and edge deployment.

## Research / Reference Review

A review of publicly available SIH submissions and open‑source flood/edge‑AI repositories was performed to identify best‑practice documentation structures, dataset documentation patterns, and edge‑AI presentation styles. No code has been directly copied.
" 
