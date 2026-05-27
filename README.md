=================================================================================================
                       		      DEEPTAL v1.0
DEtection and Evaluation of overdeepenings as Potential sites for future glacial TAL (Lake)
=================================================================================================

Version: 1.0
Date:    27 May 2026
Authors:  Dr. PJ Navinkumar; Mrs. J.S. Gopika, Dr. Rahul Kumar, and Prof. RAAJ Ramsankaran

1. PREREQUISITES
------------------------------------------------------------------------------
A. SAGA GIS (CRITICAL STEP)
   This tool requires SAGA GIS to perform hydrological analysis.
   The tool will automatically detect "saga" if it is placed inside the "DEEPTAL" folder. 
   If it is not present, then follow the steps given below.
   1. Download SAGA GIS (Binary Zip) from: https://sourceforge.net/projects/saga-gis/
   2. Extract the downloaded zip file.
   3. Copy this "saga**" folder and paste it inside the "DEEPTAL_R_APP" folder.
      

B. R Language & Packages (Automated)
   - The "launch_deeptal_v1.bat" file will automatically:
     1. Check if R is installed. If not, it will download and install the latest version.
     2. Check for required packages (shiny) and install them.
   - Requirement: You must have an internet connection for the first run.

   *Manual Option (If the auto-installer is blocked):*
   - Install R manually: https://cran.r-project.org/bin/windows/base/
   - Open R and run: 
     install.packages(c("shiny", "terra", "RSAGA", "ggplot2", "viridis", "patchwork", "bslib", "zip"))


2. FOLDER STRUCTURE
------------------------------------------------------------------------------
Ensure your folder looks like this for the Auto-Detect features to work:

/DEEPTAL_R_APP
   |-- app_deeptal_v1.R          (The main application code)
   |-- launch_deeptal_v1.bat     (Double-click this to run)
   |-- saga**/                   (Place your SAGA GIS folder here!)
   |-- www/                      (Logos and Help PDF)
   |-- Output/                   (Results will be saved here automatically)


3. HOW TO LAUNCH
------------------------------------------------------------------------------
Method A: The "One-Click" Launcher (Recommended)
   1. Right-click the "launch_deeptal_v1.bat" file and select "Run as Administrator".
      (Note: Administrator rights are required so the tool can automatically 
      install R and the necessary packages during its first run).
   2. Wait! The first time you run it, it may take a few minutes to:
      - Download R (if missing).
      - Install necessary libraries.
   3. Once ready, the tool will open in a clean, standalone window (App Mode).

Method B: Run via RStudio (Advanced)
   1. Open "app_deeptal_v1.R" in RStudio.
   2. Ensure you have set the SAGA path in the UI or code.
   3. Click "Run App".


4. TROUBLESHOOTING
------------------------------------------------------------------------------
* Issue: "SAGA Path not found" error in the tool.
  Solution: Ensure you pasted the "saga**" folder inside the tool directory. 
  Alternatively, paste the full path to your SAGA folder (e.g., C:/SAGA-9.11) 
  into the text box in the tool.

* Issue: The black window closes immediately or shows "Download failed".
  Solution: Check your internet connection. Your university/office firewall might 
  be blocking the auto-download. If so, install R manually (Section 1B).

* Issue: "The system cannot find the path specified" for Chrome/Edge.
  Solution: The tool tries to open Chrome or Edge automatically. If you use a 
  non-standard browser, just open your browser and type: http://127.0.0.1:3361

==============================================================================
Developed by 
Hydro-Remote Sensing Applications (H-RSA) Group, 
Department of Civil Engineering,
Indian Institute of Technology (IIT) Bombay

Powered by 
Geospatial Information Science and Engineering (GISE) Hub, IIT Bombay
==============================================================================
