# Measles Incidence & Vaccination Coverage (2015–2024)

## Project Description
This project analyzes global measles incidence trends from **2015–2024** and integrates them with **MCV1 and MCV2 vaccination coverage** from WUENIC (WHO/UNICEF). The analysis visualizes incidence patterns across WHO regions and countries, identifies high-burden locations, evaluates MCV1–MCV2 dropout, and examines how vaccination coverage relates to measles incidence. All figures and analysis were produced in **R** using tidyverse-based workflows.

---

## Data Sources

### **Measles Case Data (2015–2024)**  
Obtained from TidyTuesday (WHO-sourced):  
🔗 https://github.com/rfordatascience/tidytuesday/tree/main/data/2025/2025-06-24  

The file used in this project:  
- `cases_year.csv`  

### **Vaccination Coverage Data (WUENIC)**  
Queried from WHO Immunization Data (downloaded **11/11/2025**):  
🔗 https://immunizationdata.who.int/global/wiise-detail-page/measles-vaccination-coverage?GROUP=WHO_REGIONS+Countries&ANTIGEN=&YEAR=&CODE=

Query settings used:
- **WHO Regions:** All  
- **Countries:** All  
- **Antigen:** Measles-containing vaccine, 1st dose;  Measles-containing vaccine, 1st dose
- **Years:** 2015–2024  

The exact Excel file used in this analysis (`measles_vaccination_coverage_2015_24.xlsx`) is included in this repository.

---

## Installation / Build Instructions

### Requirements
- R and RStudio  
- `DV_Measles_Final.Rmd`  
- `measles_vaccination_coverage_2015_24.xlsx`  

### Install Required R Packages
```r
install.packages(c(
  "tidyverse", "readr", "readxl", "janitor",
  "countrycode", "scales", "broom", "glue", "stringr"
))


