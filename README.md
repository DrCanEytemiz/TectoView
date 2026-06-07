# TectoView: An Open-Source Web Tool for Real-Time Seismotectonic Cross-Section Visualization

[![DOI](https://zenodo.org/badge/1121270051.svg)](https://doi.org/10.5281/zenodo.18022059)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**TectoView** is a platform-independent, browser-based single-page application designed for rapid, interactive seismotectonic data exploration and high-resolution visualization[cite: 1]. By performing all geodetic computations entirely on the client side, TectoView bridges the gap between raw catalog data and structural interpretation within seconds—requiring no local installation, server uploads, or licensing fees[cite: 1].

It is engineered to instantly produce publication-quality (Q1 journal standards) graphical outputs directly from your browser[cite: 1].

## 🚀 Live Demo

**[Click here to use TectoView](https://DrCanEytemiz.github.io/TectoView/)**  
*(No installation required. Runs entirely in your browser supporting the HTML5 Canvas API[cite: 1].)*

---

## ✨ Key Features

* **Multi-Format Ingestion:** Drag-and-drop support for comprehensive seismotectonic datasets including earthquake catalogs, fault traces, topographic data, and focal mechanisms[cite: 1].
* **Interactive Dynamic Profiling:** Select profile transects (A–A') either by dragging map markers or entering manual coordinates[cite: 1]. It automatically computes great-circle bearings, azimuths, and Reciprocal/Forward orientation labels mapped onto 16 intercardinal compass sectors[cite: 1].
* **Rigorous Geodetic Computations:** Uses the **Haversine Formula** for accurate profile length measurements on regional scales[cite: 1]. Utilizes **Heron's Formula** and the Law of Cosines for swath filtering and precise perpendicular projection of hypocenters onto the target cross-section[cite: 1].
* **Automated Topography Pipeline:** Integrated **OpenTopography API** module to automatically download 30 m resolution SRTM Global 1 Arc-Second (SRTMGL1) DEM data based on profile limits or spatial polygons[cite: 1].
* **Focal Mechanism Support:** Renders equal-area Schmidt projection beachballs[cite: 1]. Supports *In-situ* or *Sky* modes on cross-sections, and *Epicenter* or *Radial Offset* (with leader lines) layouts on the map view to avoid overlaps[cite: 1].
* **Advanced Visual Analytics:** 
  * **Dual-Variable Map Encoding:** Map and profile symbols concurrently visualize depth (via customizable linear gradients) and magnitude (via editable quadratic or custom JavaScript expressions)[cite: 1].
  * **Temporal Phase Split:** Automatically parses catalog metadata to isolate the mainshock (Cyan star) and secondary significant doublets (Yellow star), splitting sequences into color-coded phases (Grey/Red)[cite: 1]. Includes a manual time-override split panel[cite: 1].
* **Dynamic Fault Label Mapping:** Automatically parses attribute tables from uploaded Shapefiles, allowing users to dynamically select custom columns (e.g., fault names) to render as tick marks on the cross-section[cite: 1].
* **Publication Ready:** Single-click exports to high-resolution raster images (**PNG at 900 DPI**) or fully scalable, group-separated vector graphics (**SVG**), ensuring seamless post-processing in Adobe Illustrator or Inkscape[cite: 1].
* **Reproducibility & Privacy:** Full interface states (coordinates, visual preferences, ranges) can be exported/imported via JSON settings files[cite: 1]. All processing happens locally; your data never leaves your computer[cite: 1].

---

## 📂 Input Data Formats

All datasets are loaded via drag-and-drop boxes equipped with instant clear (✕) controls[cite: 1]. Coordinate inputs are expected in geographic coordinates (**WGS84**, decimal degrees)[cite: 1].

### 1. Earthquake Data
The parser automatically detects column headers or schemas for three formats[cite: 1]:
* **Plain Text (.txt) & CSV (.csv):** Must contain a header row followed by one event per line[cite: 1]. Mandatory fields (in any order): `latitude`, `longitude`, `depth` (km), `magnitude`, and `time` (ISO 8601 format, e.g., `2023-02-06T04:17:33`)[cite: 1].
* **QuakeML (.xml / .qml):** Fully compliant with the QuakeML 1.2 schema, reading preferred origin and magnitude elements with XML-namespace tolerance[cite: 1].

### 2. Topography Data
* **Local Import:** Supports ASCII `.xyz` point clouds (`Longitude Latitude Elevation` in meters) or GeoTIFF `.tif` files[cite: 1].
* **API Retrieval:** If no file is uploaded, entering a free OpenTopography API key allows instant client-side fetching and linear binning of SRTM data (up to a 2.5° bounding box span)[cite: 1].

### 3. Active Faults
* **Shapefile (.zip):** A zipped archive containing mandatory `.shp`, `.shx`, and `.dbf` files[cite: 1].
* **Text (.txt):** Custom segment format containing fault trace vertices[cite: 1].

### 4. Focal Mechanisms (.txt / .csv)
* Must follow a structured columnar format: `Latitude`, `Longitude`, `Depth`, `Magnitude`, `Strike`, `Dip`, `Rake`[cite: 1].

---

## 📖 How to Cite

If you use TectoView in your academic work, abstracts, or reports, please cite the core software and repository as follows:

> Eytemiz, C. (2026). TectoView: An Open-Source Web Tool for Real-Time Seismotectonic Cross-Section Visualization [Software]. Zenodo. https://doi.org/10.5281/zenodo.18022059

## 📄 License

This project is licensed under the permissive **MIT License** - see the [LICENSE](LICENSE) file for details. It permits free academic and commercial use, modification, and distribution[cite: 1].

---
**Developed by Dr. Can Eytemiz**[cite: 1]  
* Dokuz Eylül University, Institute of Marine Sciences and Technology, Marine Geology and Geophysics[cite: 1]
* Dokuz Eylül University, Earthquake Research and Application Center (DAUM)[cite: 1]  
* ✉️ can.eytemiz@deu.edu.tr | ORCID: 0000-0002-1474-695X[cite: 1]
