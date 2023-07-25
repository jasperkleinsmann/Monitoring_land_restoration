# Monitoring_land_restoration

This repository contains all the scripts developed for the article: **A Remote Sensing Assessment of Farmer-Managed Land Restoration in Seven African Countries using Dense NDVI Time Series Forecasting**. The scripts are numbered (A1, A2, etc) based on the order in which they should be executed.

The restoration polygon data is not made available for privacy and property reasons. Still, parts of the analysis can be reproduced as some intermediate Landsat 8 time series have been made available here. The data in the folders `datasets/output/time_series` and `datasets/output/plot_data` can be used to run the greening time series analysis in scripts A6, A7 and parts of A10. 

Overview of the scripts:
- A1: Script to (geometrically) clean and combine the raw restoration plot data
- A2: Script to extract Landsat 8 and GPM precipitation time series for all restoration plots using GEE
- A3: Script to 1) merge all the country-specific reflectance data extracted from GEE and 2) convert these raw DN values into surface reflectance
- A4: Script to 1) extract all site-specific GPM data, 2) do some basic pre-processing on it and 3) merge the precipitation data to the plot reflectance time series
- A5: Script 1) assign administrative boundary information (country, district, region) to the plots based on geometry and 2) combine the satellite time series from all countries into one dataframe.
- A6: Script to 1) train the SARMAX models and 2) predict the NDVI per plot
- A7: Script to perform the greening analysis. It merged the actual NDVI and predicted SARMAX NDVI and compared the two time series by computing the MAEp
- A8a: Script that performs the entire greening time series analysis (A2, A3, A4, A5, A6, A7) for the validation points
- A8b: Script to create annual median composites of Landsat 8 data for validation of the model
- A9: Script to perform the greening analysis (A2, A3, A4, A5, A6, A7) for 100 sub-areas of large plots (>120 ha) to check the robustness of the method for large plots
- A10: Script to make the figures 
