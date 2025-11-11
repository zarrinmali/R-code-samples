# R-code-samples
This repository contains selected R Markdown files demonstrating data cleaning, transformation, visualization, and analysis skills.  
Data files used in these scripts are not included due to confidentiality.  

## Files
- `Data Task-Barley production.Rmd`
  This script analyzes data on barley production and prices in the US from 1990-2017. It uses a dataset on barley production in bushels by agricultural district, as well as a dataset on mean prices received by farmers per bushel of barley by state. The script includes some data visualizations as well as regressions to explore patterns and relationships in the data.

- `IMR-AFO Data Wrangling (for regressions).Rmd`
  This code was written by me when I was working as an RA for Professor Eyal Frank at Harris School of Public Policy at UChicago.
  This script processes Animal Feeding Operations (AFO) and infant mortality rate (IMR) data for five U.S. states (NC, MI, WI, IA, MN) to create spatially and temporally harmonized datasets for regression analysis. It performs the following:
  1. Cleans and consolidates facility-level AFO data, converting start and end dates into a monthly panel of AFO activity from roughly 1989–2018 (year range varies by state).
  2. Spatially links AFOs to counties using shapefiles and constructs county-by-year-by-month counts of active AFOs.
  3. Computes AFO counts within distance gradations (0–100 km) around both population-weighted and geographic centroids for each county and time period.
  4. Generates separate state-level and combined datasets for both centroid types so that the resulting datasets contain the number of AFOs by distance gradation around the population and geographic-weighted centroids at the county-by-year-by-month level for each of the states mentioned.
  5. Cleans and aggregates two types of IMR data (from detailed mortality files and linked birth–death records), merges with county-level populations, and calculates monthly IMR values.

- `IMR-AFO Data Analysis (Regressions).Rmd`
  This code was written by me when I was working as an RA for Professor Eyal Frank at Harris School of Public Policy in UChicago.
  This script analyzes the relationship between infant mortality rates (IMR) and the number of animal feeding operations (AFOs) across counties in five U.S. states (NC, MI, WI, IA, MN). It uses datasets for IMR and AFOs by distance gradation around population-weighted and geographic centroids at the county-by-year-by-month level for each of the states mentioned. (These datasets are created in the script called IMR-AFO Data Wranging (for regressions)).The script constructs merged datasets at the county-year-month level, applies state-specific temporal truncations, and estimates fixed-effects regressions to quantify associations between AFO activity and IMR under varying model specifications. In total, 36 regression models are produced—covering both IMR measures, centroid types, and fixed-effects combinations whose results are saved as text tables for further interpretation.

- `IL DOA-EPA matching_Zarrin_final.Rmd`
  This code was written by me when I was working as an RA for Professor Eyal Frank at Harris School of Public Policy in UChicago.
  This script cleans, deduplicates, and merges Animal Feeding Operation (AFO) records in Illinois from two state agencies, the Department of Agriculture (DOA) and the Environmental Protection Agency (EPA), to create a unified, geocoded facility-level dataset. The main steps are outlined below:
  1. DOA internal matching: 
      - Splits the raw DOA dataset into records with and without facility IDs.
      - Uses fuzzy string matching on facility names to identify potential duplicates.
      - Filters matches by county and animal type, applies a similarity threshold, and reviews results manually in Excel as needed.
      - Creates a cleaned, unique facility-level dataset with consolidated coordinates and ownership information.
  2. DOA–EPA cross-agency matching: 
      - Fuzzy-joins DOA and EPA datasets by facility name, filters by same county, and groups matches by string similarity.
      - Calculates geographic distances between matched facility coordinates to confirm validity.
      - Conducts manual verification in Excel for ambiguous cases.
      - Merges confirmed matches and appends unmatched DOA and EPA facilities to preserve full coverage.
  3. Final dataset 
      - Collapses the merged dataset so that each facility corresponds to one row, consolidating similar facility and owner names using string distance metrics.
      - Ensures each unique facility has one consistent ID, name, address, and set of coordinates.
