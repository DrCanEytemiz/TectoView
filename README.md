# TectoView: An Open-Source Web Tool for Real-Time Seismotectonic Cross-Section Visualization

[![DOI](https://zenodo.org/badge/1121270051.svg)](https://doi.org/10.5281/zenodo.18022059)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**TectoView** is a platform-independent, browser-based single-page application designed for rapid, interactive seismotectonic data exploration and high-resolution visualization. By performing all geodetic computations entirely on the client side, TectoView bridges the gap between raw catalog data and structural interpretation within seconds—requiring no local installation, server uploads, or licensing fees.

It is engineered to instantly produce publication-quality graphical outputs directly from your browser.

---

## 🚀 Live Demo

**[Click here to use TectoView](https://DrCanEytemiz.github.io/TectoView/)**
*(No installation required. Runs entirely in your browser supporting the HTML5 Canvas API.)*

---

## ✨ Key Features

- **Multi-Format Ingestion:** Drag-and-drop support for comprehensive seismotectonic datasets including earthquake catalogs, fault traces, topographic data, and focal mechanisms.

- **Interactive Dynamic Profiling:** Define profile transects (A–A') by dragging interactive map markers or by entering coordinates manually in either decimal degrees (DD) or degree–minute–second (DMS) format, switchable via a toggle. DMS fields enforce a valid [0, 60) range. The tool automatically computes great-circle bearings, azimuths, and Reciprocal/Forward orientation labels mapped onto 16 compass sectors.

- **Rigorous Geodetic Computations:** Uses the **Haversine Formula** for accurate profile length measurements on regional scales. Applies the **Law of Cosines** and **Heron's Formula** for swath filtering and precise perpendicular projection of hypocenters onto the target cross-section.

- **Automated Topography Pipeline:** Integrated **OpenTopography API** module to automatically download 30 m resolution SRTM Global 1 Arc-Second (SRTMGL1) DEM data based on profile limits or spatial polygons.

- **Focal Mechanism Support:** Renders equal-area (Schmidt) projection beachballs with a physically correct hemisphere-boundary algorithm, ensuring accurate compressional/dilatational quadrant detection across all mechanism types (strike-slip, normal, reverse, oblique). On cross-sections, each beachball is plotted above the topographic envelope in plan view, with the corresponding hypocenter marked at its true depth and linked by a vertical dashed guide line. On the map, supports *Epicenter* or *Radial Offset* (with leader lines) layouts to avoid overlaps.

- **Advanced Visual Analytics:**
  - **Dual-Variable Map Encoding:** Map and profile symbols concurrently visualize depth (via customizable linear gradients) and magnitude (via editable quadratic or custom JavaScript expressions).
  - **Three Coloring Modes:** *By Depth* (color = depth), *By Time — Phase Split* (automatic mainshock/doublet detection with color-coded temporal phases and a manual time-override panel), and *By Time — Continuous Gradient* (smooth single-gradient coloring across the full catalog time span).
  - **Time Filter:** A tmin/tmax date-range panel in Graph Parameters instantly filters both the map and cross-section, letting you isolate any temporal subset of the catalog.

- **Legend Position Control:** Place the legend at any of the four corners of the chart area, or as a horizontal strip entirely below the plot axis, ensuring it never obscures data.

- **Dynamic Fault Label Mapping:** Automatically parses attribute tables from uploaded Shapefiles, allowing users to dynamically select custom columns (e.g., fault names) to render as tick marks on the cross-section.

- **Publication Ready:** Single-click exports to high-resolution raster images (**PNG at 900 DPI**) or fully scalable, group-separated vector graphics (**SVG**), ensuring seamless post-processing in Adobe Illustrator or Inkscape.

- **Reproducibility & Privacy:** Full interface states (coordinates, visual preferences, ranges) can be exported/imported via JSON settings files. All processing happens locally; your data never leaves your computer.

---

## 📂 Input Data Formats

All datasets are loaded via drag-and-drop boxes equipped with instant clear (✕) controls. Coordinate inputs are expected in geographic coordinates (**WGS84**, decimal degrees).

### 1. Earthquake Data
The parser automatically detects column headers or schemas for three formats:
- **Plain Text (.txt) & CSV (.csv):** Must contain a header row followed by one event per line. Mandatory fields (in any order): `latitude`, `longitude`, `depth` (km), `magnitude`, and `time` (ISO 8601 format, e.g., `2023-02-06T04:17:33`).
- **QuakeML (.xml / .qml):** Fully compliant with the QuakeML 1.2 schema, reading preferred origin and magnitude elements with XML-namespace tolerance.

### 2. Topography Data
- **Local Import:** Supports ASCII `.xyz` point clouds (`Longitude Latitude Elevation` in meters) or GeoTIFF `.tif` files.
- **API Retrieval:** If no file is uploaded, entering a free OpenTopography API key allows instant client-side fetching and linear binning of SRTM data (up to a 2.5° bounding box span).

### 3. Active Faults
- **Shapefile (.zip):** A zipped archive containing mandatory `.shp`, `.shx`, and `.dbf` files.
- **Text (.txt):** Custom segment format containing fault trace vertices.

### 4. Focal Mechanisms (.txt / .csv)
- Must follow a structured columnar format: `Latitude`, `Longitude`, `Depth`, `Magnitude`, `Strike`, `Dip`, `Rake`.

---

## 📖 How to Cite

If you use TectoView in your work, abstracts, or reports, please cite the core software and repository as follows:

> Eytemiz, C. (2026). TectoView: An Open-Source Web Tool for Real-Time Seismotectonic Cross-Section Visualization [Software]. Zenodo. https://doi.org/10.5281/zenodo.18022059

## 📄 License

This project is licensed under the permissive **MIT License** — see the [LICENSE](LICENSE) file for details. It permits free academic and commercial use, modification, and distribution.

---

**Developed by Dr. Can Eytemiz**
- Dokuz Eylül University, Institute of Marine Sciences and Technology, Marine Geology and Geophysics
- Dokuz Eylül University, Earthquake Research and Application Center (DAUM)
- ✉️ can.eytemiz[at]deu.edu.tr | ORCID: 0000-0002-1474-695X
