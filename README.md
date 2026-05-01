# NDVI-Data-Cube-Reconstruction-using-Temporal-and-Spatial-Interpolation.

## 📌 Overview

This project presents a workflow for **NDVI Data Cube Reconstruction using Temporal and Spatial Interpolation** from satellite imagery. The analysis focuses on generating a consistent, gap-free NDVI data cube over a **custom-defined Region of Interest (ROI) within the Western Province of Sri Lanka**.

Using multi-temporal satellite observations, the study addresses common challenges such as cloud contamination, missing pixels, and irregular temporal coverage. NDVI is first derived from surface reflectance data, followed by the construction of a spatio-temporal data cube. To improve data continuity and usability, missing values are systematically handled through **temporal interpolation (across time)** and **spatial interpolation (across image dimensions)**.

The reconstructed NDVI data cube enables clearer visualization of vegetation dynamics and supports more reliable time series analysis. This approach provides a scalable and reproducible framework for environmental monitoring, particularly in regions with frequent cloud cover and data gaps.

---

## 🎯 Objectives

* Extract NDVI from satellite imagery over a selected ROI
* Remove cloud and shadow contamination using QA bands
* Convert Earth Engine imagery into an analysis-ready data cube
* Perform **gap filling** using temporal and spatial interpolation
* Apply smoothing to reduce noise in NDVI time series
* Visualize original vs processed NDVI datasets

---

## 🧰 Tools and Libraries

* **Python**
* Google Earth Engine (GEE)
* geemap
* xarray
* xee
* **Matplotlib**

---

## 🛰️ Dataset

* Satellite Data: Landsat 8 Collection 2 Level-2
* Bands used:

  * Surface Reflectance bands (`SR_B5`, `SR_B4`)
  * Quality Assessment band (`QA_PIXEL`)
* Temporal Range: **2023 – 2024**
* Spatial Extent: User-defined ROI (drawn interactively)

---



## 📊 Outputs

### Multi-temporal NDVI maps
<img width="1808" height="2690" alt="1" src="https://github.com/user-attachments/assets/7ff3f720-f4f4-45d4-8c91-0e3140e1bb69" />

### Gap-filled NDVI dataset
 <img width="1808" height="2690" alt="3" src="https://github.com/user-attachments/assets/fab3334a-9885-4c5a-ad23-13d531746e63" />
 
### Smoothed NDVI time series
<img width="1808" height="2690" alt="2" src="https://github.com/user-attachments/assets/003d6838-4272-4b62-83fd-231e31912495" />

---

## ⚠️ Notes

* Dimension names may vary (`X/Y` vs `x/y`) depending on projection
* Always verify dataset structure using:

  ```python
  print(ds.dims)
  ```
* Interpolation must match the correct dimension names

---

## 🚧 Limitations

* **Cloud contamination** may still influence NDVI quality
* Linear interpolation may not fully capture complex vegetation dynamics
* Spatial interpolation can introduce artificial smoothing in heterogeneous landscapes
* Temporal resolution depends on satellite revisit frequency (~16 days for Landsat)

---

## 🔍 Potential Improvements

* Use higher temporal resolution data such as Sentinel-2
* Apply advanced smoothing techniques (e.g., Savitzky–Golay filter)
* Integrate multi-sensor data fusion (Landsat + Sentinel)
* Perform seasonal or phenological analysis

---

## 🌍 Applications

* Vegetation monitoring
* Drought assessment
* Agricultural analysis
* Land cover change detection
* Ecosystem health evaluation

---

## 📎 Conclusion

This workflow provides a robust and scalable approach to generating **gap-free NDVI time series** from satellite imagery. By combining cloud-based processing with local analytical tools, it enables efficient handling of large geospatial datasets and supports advanced environmental analysis.

---

