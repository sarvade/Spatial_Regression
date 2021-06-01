# Spatial_Regression


## Spatial Analysis for Crime Rates for San Francisco city


In this post, I walk through the steps required to build, evaluate, and interpret spatial regression models in Python.

The goal here is to develop a model that examines the relationship between rate of drunkenness incidents and bar density within block groups, while controlling for underlying spatial structure as well as for other block group characteristics that tend to be related to crime (Freisthler et al, 2016).  The explanatory variables I use in these models (in addition to bar density) are % poverty, % male, % vacant housing units, and retail density. The inclusion of retail density as a control is important in that it helps separate the effect of bars from the overall effect of retail, which tends to have a positive relationship with crime.

I'm going to start from the point of already having built the dataset. However, if you are interested, the code I used to build this dataset along with documentation of this process can be found on my [github](). The [first notebook]() wrangles with the raw California Alcohol Beverage Control licensing data to extract and geocode bars within San Francisco. The [second notebook]() extracts demographic data from the American Community Survey; cleans and maps the crime data; creates a measure of retail density using parcel land use data; and then aggregates all this data to the block group level for the final dataset. And lastly, the notebook containing the code used in this analysis can be downloaded [here]().
