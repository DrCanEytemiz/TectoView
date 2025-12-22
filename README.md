\# TectoView Pro: Advanced Seismotectonic Cross-Section Plotter



\[![DOI](https://zenodo.org/badge/1121270051.svg)](https://doi.org/10.5281/zenodo.18022059)


\*\*TectoView Pro\*\* is a web-based, interactive tool designed for seismologists and structural geologists to visualize earthquake hypocenters, fault lines, and topography in 2D map view and 3D projected cross-sections.



It is designed to produce publication-quality (Q1 journal standard) figures directly from the browser.



\## 🚀 Live Demo

\*\*\[Click here to use TectoView Pro](https://DrCanEytemiz.github.io/TectoView-Pro/)\*\*  

\*(No installation required. Runs entirely in your browser.)\*



\## ✨ Key Features

\*   \*\*Instant Visualization:\*\* Drag \& drop support for Earthquakes (`.txt`), Faults (`.zip` Shapefile or `.txt`), Topography (`.xyz`), and Polygons.

\*   \*\*Interactive Profiling:\*\* Drag A-A' markers on the map to instantly update the cross-section.

\*   \*\*Swath Profiling:\*\* Adjustable profile width (swath) using Heron's formula for precise distance calculations.

\*   \*\*Mainshock Analysis:\*\* Automatically identifies and highlights primary and secondary mainshocks (Cyan/Yellow stars).

\*   \*\*Temporal Phasing:\*\* "Color by Time" mode to distinguish foreshocks/aftershocks phases (Grey/Red).

\*   \*\*Publication Ready:\*\* Downloads high-resolution combined figures (Map + Profile) with academic formatting (Times New Roman fonts, inner ticks, coordinates).

\*   \*\*Privacy Focused:\*\* All data processing happens client-side. Your data never leaves your computer.



\## 📂 Input Data Formats



\### 1. Earthquake Data (.txt)

The tool supports a specific columnar format (whitespace separated).

\*   \*\*Format:\*\* `ID LAT LON DEPTH X Y Z EX EY EZ YR MO DY HR MI SC MAG`

\*   The tool uses `LAT` (Col 2), `LON` (Col 3), `DEPTH` (Col 4), `YR/MO/DY...` (Cols 11-16 for time), and `MAG` (Col 17).



\### 2. Topography (.xyz)

Standard XYZ format: `Longitude Latitude Elevation`



\### 3. Faults (.zip or .txt)

\*   \*\*Shapefile:\*\* A standard .zip containing .shp, .shx, .dbf.

\*   \*\*Text:\*\* Custom segment format supported by the parser.



\## 📖 How to Cite

If you use this tool in your research, please cite it as follows:



> Eytemiz, C. (2025). TectoView Pro: Advanced Seismotectonic Cross-Section Plotter \[Software]. Zenodo. https://doi.org/10.5281/zenodo.XXXXXX



\## 📄 License

This project is licensed under the MIT License - see the \[LICENSE](LICENSE) file for details.



---

\*\*Developed by Dr. Can Eytemiz\*\*  

\*Dokuz Eylul University\*

\*Earthquake Research and Application Center (DAUM)\*


