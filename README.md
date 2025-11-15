# Measles Incidence & Vaccination Coverage (2015–2024)

## Project Description
This project analyzes global measles incidence trends from **2015–2024** and integrates them with **MCV1 and MCV2 vaccination coverage** from WUENIC (WHO/UNICEF). The analysis visualizes incidence patterns across WHO regions and countries, identifies high-burden locations, evaluates MCV1–MCV2 dropout, and examines how vaccination coverage relates to measles incidence. All figures and analysis were produced in **R** using tidyverse-based workflows.

---

## Data Sources

### **Measles Case Data (2015–2024)**  
Obtained from TidyTuesday (WHO-sourced):  
🔗 https://github.com/rfordatascience/tidytuesday/tree/main/data/2025/2025-06-24  

The file used in this project: `cases_year.csv`. Follow the above link to see the data dictionary.

### **Vaccination Coverage Data (WUENIC)**  
Queried from WHO Immunization Data (downloaded **11/11/2025**):  
🔗 https://immunizationdata.who.int/global/wiise-detail-page/measles-vaccination-coverage?GROUP=WHO_REGIONS+Countries&ANTIGEN=&YEAR=&CODE=

Query settings used:
- **WHO Regions:** All  
- **Countries:** All  
- **Antigen:** Measles-containing vaccine, 1st dose;  Measles-containing vaccine, 1st dose
- **Years:** 2015–2024  

The exact Excel file used in this analysis (`measles_vaccination_coverage_2015_24.xlsx`) is included in this repository.
Data dictionary and other information about the data can be found in the sheets of the Excel file.

## Data Cleaning
- **Measles incidence data (TidyTuesday/WHO):**
  - Converted year values to numeric and restricted the dataset to 2015–2024.
  - Mapped WHO region codes (AFRO, AMRO, etc.) to full region names.

- **Vaccination coverage data (WUENIC):**
  - Standardized country names, including resolving encoding inconsistencies  
    (e.g., *Côte d’Ivoire* → *Cote d'Ivoire*).
  - Merged WHO region information into the vaccination dataset.
  - Reshaped coverage data to wide format to compute **MCV1–MCV2 dropout**.

- **Merged dataset:**
  - Combined incidence, vaccination, and dropout datasets by matching on `country` and `year`.
  - Created additional derived fields (e.g., MCV2 coverage groups, incidence caps) used for visualization clarity.
---

## Installation and Build Instructions

### 1. Software Requirements
- **R** (version 4.0 or later)
- **RStudio** (recommended for knitting the R Markdown file)
- The following project files:
  - `DV_Measles_Final.Rmd`
  - `measles_vaccination_coverage_2015_24.xlsx`

---

### 2. Install Required R Packages
Before running the analysis, install all necessary packages:

```r
install.packages(c(
  "tidyverse", "readr", "readxl", "janitor",
  "countrycode", "scales", "broom", "glue", "stringr"
))
```
### 3. Run the Project

1. Download or clone this repository to your local machine.  
2. Ensure that all project files are stored in the same working directory.  
3. Open `DV_Measles_Final.Rmd` in **RStudio**.  
4. Confirm that the vaccination file  
   `measles_vaccination_coverage_2015_24.xlsx`  
   is present in the directory, as the script reads it directly.  
5. When running the code, all visualizations will automatically display in the RStudio Plots pane. If you wish to save the figures as standalone PNG files, the code includes optional `ggsave()` lines (currently commented out). 


