# Land Restoration Anomaly Detection 

This repository contains the scripts developed for the article: **Continuous Anomaly Detection after Farmer-Managed Land Restoration in Sub-Saharan Drylands**.

### How to use:
The scripts are numbered (A1, A2, etc) based on the order in which they were executed. The greening time series analysis can be reproduced by executing scripts A6 and A7 in combination with the intermediate satellite (Landsat 8 and GPM) datasets (available here: https://doi.org/10.5281/zenodo.8181836). The data required are stored in the folders `datasets/output/time_series` and `datasets/output/plot_data`. The resulting datasets from A6 and A7 can be used to reproduce the figures in A10. 

_Note:_ The restoration polygon data are not made available for privacy and property reasons. 

### Overview of the scripts:
- A1: Script to (geometrically) clean and combine the raw restoration plot data
- A2: Script to extract Landsat 8 and GPM precipitation time series for all restoration plots using GEE
- A3: Script to 1) merge all the country-specific reflectance data extracted from GEE and 2) convert these raw DN values into surface reflectance
- A4: Script to 1) extract all plot-specific GPM data, 2) do some basic pre-processing on it and 3) merge the precipitation data to the plot reflectance time series
- A5: Script 1) assign administrative boundary information (country, district, region) to the plots based on geometry and 2) combine the satellite time series from all countries into one dataframe.
- A6: Script to 1) train the SARMAX models and 2) forecast the NDVI per plot
- A7: Script to perform the Countinuous Anomaly Detection after Intervention (CADI) analysis. It merges the actual NDVI and forecasted SARMAX NDVI and compares the two time series by computing the MAEp
- A8a: Script that performs the entire CADI time series analysis (A2, A3, A4, A5, A6, A7) and RESTREND analysis for the validation points.
- A8b: Script to create annual median composites of Landsat 8 data for validation of the model
- A9: Script to perform the greening analysis (A2, A3, A4, A5, A6, A7) for 100 sub-areas of large plots (>120 ha) to check the robustness of the method for large plots
- A10: Script to make the figures

The analysis is available an online tool here: https://dashboards.cifor-icraf.org/app/restoration_app
