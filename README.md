# DEEPTAL v1.0  
## DEtection and Evaluation of overdeepenings as Potential sites for future glacial TAL (Lake)
DEEPTAL is a geospatial analysis tool developed for the automated detection and evaluation of glacier bed overdeepenings that may evolve into future glacial lakes under changing climatic conditions.
You can download from the link, https://github.com/pjnavinkumar/DEEPTAL/releases/tag/v1.0

---

## Version Information
- **Version:** 1.0  
- **Release Date:** 27 May 2026  
### Authors
- **Prof. RAAJ Ramsankaran**
- **Dr. P J Navinkumar**, **Mrs. J S Gopika**, **Dr. Rahul Kumar**  
Department of Civil Engineering  
Indian Institute of Technology (IIT) Bombay  
---

# 1. Prerequisites
## A. SAGA GIS (Important)
DEEPTAL requires SAGA GIS for hydrological preprocessing and sink-filling operations.

### Automatic Detection
The software automatically detects SAGA GIS if the extracted `saga-*` folder is placed inside the main `DEEPTAL_R_APP` directory.

### Installation Steps
1. Download **SAGA GIS (Binary ZIP version)** from:  
   https://sourceforge.net/projects/saga-gis/
2. Extract the downloaded ZIP archive.
3. Copy the extracted `saga-*` folder into the main application directory:
```text
/DEEPTAL_R_APP
   └── saga-*
```
---

## B. R Language & Required Packages
The launcher script automatically installs missing dependencies during the first run.

### Automatic Setup
The file:
```text
launch_deeptal_v1.bat
```
will automatically:
- Check whether R is installed
- Download and install R (if missing)
- Install required R packages

### Internet Requirement
An internet connection is required during the first execution.

---

## Manual Installation (Optional)
If automatic installation is blocked by firewall or security settings:

### Install R manually
Download from:
https://cran.r-project.org/bin/windows/base/

### Install required packages manually
Open R or RStudio and run:
```r
install.packages(c(
  "shiny",
  "terra",
  "RSAGA",
  "ggplot2",
  "viridis",
  "patchwork",
  "bslib",
  "zip"
))
```
---

# 2. Folder Structure
Ensure the directory structure is organized as follows:
```text
/DEEPTAL_R_APP
│
├── app_deeptal_v1.R
├── launch_deeptal_v1.bat
├── saga**/
├── www/
└── Output/
```

### Description
| Folder/File | Description |
|---|---|
| `app_deeptal_v1.R` | Main DEEPTAL application |
| `launch_deeptal_v1.bat` | One-click launcher |
| `saga**/` | SAGA GIS installation folder |
| `www/` | Logos, manuals, help files |
| `Output/` | Automatically generated analysis outputs |

---

# 3. Launching the Application
## Method A — One-Click Launcher (Recommended)
1. Right-click:
```text
launch_deeptal_v1.bat
```
and select:
```text
Run as Administrator
```
2. During the first run, the launcher may:
   - Install R
   - Install required packages
   - Configure dependencies
3. Once initialization is complete, DEEPTAL opens automatically in standalone application mode.
---

## Method B — Run Using RStudio
1. Open:
```text
app_deeptal_v1.R
```
in RStudio.
2. Ensure SAGA GIS path is correctly configured.
3. Click:
```text
Run App
```
---

# 4. Workflow Overview
DEEPTAL performs the following operations:
- Surface DEM preprocessing
- Ice thickness alignment
- Glacier-wise clipping and masking
- Sink filling using SAGA GIS
- Slope-based overdeepening detection
- Area- and Volume-based filtering
- Freeboard scenario analysis
- Generation of raster, vector, tabular, and visual outputs
---

# 5. Outputs Generated
For each glacier, DEEPTAL generates:

## Raster Outputs
- Overdeepening depth maps (`.tif`)
- Bedrock DEM
- Hydrologically filled bedrock DEM

## Vector Outputs
- Overdeepening polygon layers (`.geojson`)

## Tabular Outputs
- Patch-wise statistics (`.csv`)

## Visual Outputs
- Comparison plots (`.png`)

Output filenames dynamically include the selected freeboard values.
Example:
```text
glacier_1_vol_5_m_fb_depth.tif
glacier_1_area_15_m_fb_polygon.geojson
```
---

# 6. Troubleshooting
## Issue: “SAGA Path not found”
### Solution
Ensure the `saga-*` folder is placed inside the DEEPTAL directory or manually provide the SAGA installation path in the application interface.

---
## Issue: Launcher closes immediately
### Solution
- Check internet connectivity
- Ensure firewall settings are not blocking downloads
- Install R manually if necessary
---
## Issue: Browser does not open automatically
### Solution
Open a browser manually and enter:
```text
http://127.0.0.1:3361
```
---

# 7. Citation
If you use DEEPTAL in your research, please cite:
```text
Ramsankaran, R., Navinkumar, P. J., Gopika, J. S., & Kumar, R. (2026). DEEPTAL v1.0: DEtection and Evaluation of overdeepenings as Potential sites for future glacial TAL (Lake) [Software]. Indian Institute of Technology Bombay, Mumbai, India.
```
---

# 8. Disclaimer
DEEPTAL is provided as free software for research and academic purposes only. The developers and contributing team shall not be held responsible for any results, interpretations, or consequences arising from the use, misuse, or modification of the source code or outputs generated by the software. Any alterations made to the original R source code are solely the responsibility of the user.

---

# 9. Developed By
### Hydro-Remote Sensing Applications (H-RSA) Group  
Department of Civil Engineering, Indian Institute of Technology (IIT) Bombay  

## Powered By
### Geospatial Information Science and Engineering (GISE) Hub  
Indian Institute of Technology (IIT) Bombay
