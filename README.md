# PMESA — Phytomelioration Multi-Environmental Suitability Assessment

A Google Earth Engine implementation of the **Phytomelioration Multi-Environmental Suitability Assessment (PMESA)** framework for spatial screening and prioritization of phytomelioration areas on the exposed Aral Sea seabed.

This repository accompanies the research article:

**A Multi-Environmental Suitability Assessment Framework for Phytomelioration Planning in the Aral Sea Dry Bed**

Submitted to **Remote Sensing (MDPI)**.

---

## 1. Overview

The desiccation of the Aral Sea has exposed extensive areas of degraded and saline seabed. Environmental conditions across the exposed surface are spatially heterogeneous, with differences in vegetation, surface moisture, salinity-related spectral response, terrain, land surface temperature, wind exposure, and precipitation.

The PMESA framework integrates these heterogeneous environmental observations into a common spatial decision framework to estimate **relative environmental suitability for phytomelioration planning**.

The framework combines:

- multi-source environmental data;
- spatial harmonization;
- Benefit/Cost normalization;
- Entropy Weight Method (EWM);
- weighted spatial aggregation; and
- suitability classification.

The resulting PMESA index is intended for **spatial screening and prioritization** and should not be interpreted as a direct prediction of plant survival or establishment.

---

## 2. Study Area

The study area is located in **Muynak District, Karakalpakstan, Uzbekistan**, within the exposed bed of the Aral Sea.

The study domain covers approximately:

**41,343 km²**

The study boundary was obtained from the:

**FAO Global Administrative Unit Layers (GAUL) Level-2 dataset**

and processed in Google Earth Engine.

### Study period

The environmental analysis covers:

**1 May 2025 – 30 September 2025**

This seasonal period was selected to provide a consistent observation window for vegetation activity and environmental conditions relevant to the assessment.

---

## 3. Environmental Criteria

PMESA integrates eight environmental criteria.

| Criterion | Data Source | Environmental Representation | Suitability Relationship |
|---|---|---|---|
| NDVI | Sentinel-2 SR Harmonized | Vegetation condition | Benefit |
| NDWI | Sentinel-2 SR Harmonized | Surface moisture condition | Benefit |
| SI2 | Sentinel-2 SR Harmonized | Salinity-related spectral response | Cost |
| Elevation | SRTM DEM | Topographic position | Cost |
| Slope | SRTM-derived | Surface relief | Cost |
| LST | MODIS MOD11A2 | Land surface thermal condition | Cost |
| Wind Speed | ERA5-Land | Atmospheric exposure | Cost |
| Precipitation | CHIRPS Daily | Cumulative seasonal water input | Benefit |

### SI2 interpretation

SI2 is used as a **salinity-related spectral proxy**. It is not treated as a direct measurement of soil electrical conductivity or salt concentration.

---

## 4. Data Sources

All spatial environmental datasets used in the implementation are accessed through the Google Earth Engine data catalog.

### Sentinel-2

```text
COPERNICUS/S2_SR_HARMONIZED
COPERNICUS/S2_CLOUD_PROBABILITY
