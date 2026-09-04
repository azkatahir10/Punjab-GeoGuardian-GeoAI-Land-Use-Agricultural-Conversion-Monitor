# 🛰️ Punjab GeoGuardian: GeoAI Land-Use & Agricultural Conversion Monitor

A geospatial AI pipeline built with Google Earth Engine (GEE), Python, and `geemap` to monitor urban sprawl and quantify agricultural land loss across the Raiwind Road expansion corridor in Lahore, Pakistan.

---

## 📌 Executive Summary

Rapid urban development along peri-urban corridors in Punjab threatens prime agricultural land and regional food security. **Punjab GeoGuardian** leverages cloud-free Sentinel-2 satellite imagery composites to map land-use and land-cover (LULC) transformations between **Spring 2019** and **Spring 2025**.

### Key Finding

* **Agricultural Conversion:** **3.20 sq km** of prime farmland was converted to urban built-up infrastructure along the Raiwind Road study corridor between 2019 and 2025.

---

## ⚙️ Tech Stack & Methodology

* **Platform:** Google Earth Engine (GEE), Google Colab, `geemap`
* **Data Source:** Copernicus Sentinel-2 Level-2A (`COPERNICUS/S2_SR_HARMONIZED`, 10m spatial resolution)
* **Study Area:** Raiwind Road Corridor, Lahore (`[74.15, 31.30, 74.35, 31.45]`)
* **Spectral Indices:**

  * Normalized Difference Vegetation Index (NDVI)
  * Normalized Difference Built-up Index (NDBI)
* **Classification Logic:** Calibrated rule-based thresholding for surface reflectance:

  * **Vegetation:** `NDVI >= 0.30`
  * **Built-up:** `NDBI > 0.12 AND NDVI < 0.25`

---

## 📊 Analytics Summary Output

```text
=============================================
PUNJAB GEOGUARDIAN ANALYTICS SUMMARY
=============================================
Study Area: Raiwind Road Corridor, Lahore
Timeframe: 2019 vs 2025
Agricultural Area Converted to Urban: 3.20 sq km
=============================================
```

---

## 🎯 Ground Truth Validation & Error Analysis

The pipeline performance was validated against **50 high-resolution ground truth sample locations** across the Raiwind Road corridor, accompanied by an edge-case error matrix.

### Validation Table — 50 Points

Evaluates classification accuracy across:

* Vegetation
* Built-up
* Bare Soil
* Agricultural-to-Urban Conversion

### Error Analysis — 15 Cases

Identifies potential spectral overlap and classification issues, including:

* Fallow/dry agricultural soil being confused with built-up areas
* Turbid water being confused with built-up surfaces
* Narrow asphalt road networks being omitted
* Construction sites being confused with bare agricultural land
* Cloud-shadow misclassification
* Greenhouse structures being confused with water
* Dense vegetation masking urban infrastructure
* Mixed pixels along peri-urban boundaries

The analysis also proposes architectural improvements such as multi-temporal composites, NDWI masking, Sentinel-1 SAR integration, temporal change analysis, and advanced classification techniques.

> Refer to the project documentation and notebook for the complete validation matrices and detailed error analysis.

---

## 🚀 Quickstart & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/punjab-geoguardian.git
cd punjab-geoguardian
```

### 2. Install Dependencies

```bash
pip install earthengine-api geemap
```

### 3. Run the Notebook

Open:

```text
End-to-End GeoAI and Satellite Intelligence Project.ipynb
```

in **Google Colab**.

Authenticate your Google Earth Engine account and run the notebook cells sequentially.

---

## 📂 Repository Structure

```text
punjab-geoguardian/
│
├── End-to-End GeoAI and Satellite Intelligence Project.ipynb
│   # Main Google Colab Notebook
│
├── README.md
│   # Project Summary & Documentation
│
└── requirements.txt
    # Python Dependencies
```

---

## 🔬 Methodology Overview

The project follows an end-to-end satellite intelligence workflow:

```text
Sentinel-2 Satellite Imagery
            ↓
     Data Preprocessing
            ↓
    Cloud Filtering / Masking
            ↓
    Surface Reflectance Scaling
            ↓
     Spectral Index Calculation
        ↙             ↘
      NDVI            NDBI
        ↘             ↙
      LULC Classification
            ↓
      2019 vs. 2025 Comparison
            ↓
   Agricultural → Urban Detection
            ↓
      Area Quantification
            ↓
 Ground Truth Validation & Analysis
```

---

## 📈 Results

The analysis identified significant agricultural-to-urban land conversion within the Raiwind Road study corridor.

### Primary Result

**3.20 sq km of agricultural land was identified as converted to urban built-up infrastructure between Spring 2019 and Spring 2025.**

This demonstrates the potential of satellite-based GeoAI workflows for monitoring peri-urban expansion and agricultural land-use change.

---

## 🧠 Future Improvements

Potential improvements to the Punjab GeoGuardian pipeline include:

1. Replace rule-based thresholding with supervised machine-learning classification.
2. Incorporate Sentinel-1 SAR data for improved urban and vegetation discrimination.
3. Add NDWI for improved water-body detection.
4. Implement multi-temporal imagery instead of relying solely on seasonal composites.
5. Introduce automated ground-truth data collection.
6. Compare results against higher-resolution satellite imagery where available.
7. Develop an interactive monitoring dashboard.
8. Automate periodic agricultural-to-urban change detection.
9. Incorporate spatial texture and object-based features.
10. Explore deep-learning-based semantic segmentation for high-resolution land-cover mapping.

---

## 🛠️ Technologies Used

* **Google Earth Engine**
* **Sentinel-2**
* **Python**
* **Google Colab**
* **geemap**
* **Earth Engine API**
* **Remote Sensing**
* **GIS**
* **NDVI**
* **NDBI**
* **Land Use / Land Cover Classification**
* **Change Detection**
* **GeoAI**
* **Satellite Image Analysis**

---

## 📚 Project Documentation

For the complete methodology, ground-truth validation table, analytics summary, and 15-case error analysis, refer to the project notebook and accompanying documentation.

