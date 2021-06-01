## Spatial Analysis for Crime Rates for San Francisco city

In this post, I walk through the steps required to build, evaluate, and interpret spatial regression models in Python.

<div style="text-align: justify"> I start with some background on maximum likelihood spatial regression models and then use the Python library ```pysal``` to implement them. Based on the data I found available to public, I have decided to do an analysis of crime rates within block groups in San Francisco, CA. More specifically, I look to see if police incidents related to "drunkenness" (an official crime category in the SF Police data) occur at a higher rate in areas that have a higher density of bars. Although the models presented here are simpler, because they build directly off of the standard OLS regression. </div>
<br>

<div style="text-align: justify"> The goal here is to develop a model that examines the relationship between rate of drunkenness incidents and bar density within block groups, while controlling for underlying spatial structure as well as for other block group characteristics that tend to be related to crime (Freisthler et al, 2016).  The explanatory variables I use in these models (in addition to bar density) are % poverty, % male, % vacant housing units, and retail density. The inclusion of retail density as a control is important in that it helps separate the effect of bars from the overall effect of retail, which tends to have a positive relationship with crime. </div>
<br>

I'm going to start from the point of already having built the dataset. However, if you are interested, the code I used to build this dataset along with documentation of this process can be found on my [github](https://github.com/sarvade/Spatial_Regression). 

- The [first notebook](https://github.com/sarvade/Spatial_Regression/blob/master/1-California_Alcohol_License_Data_Clean_Geocode.ipynb) wrangles with the raw California Alcohol Beverage Control licensing data to extract and geocode bars within San Francisco. 

- The [second notebook](https://github.com/sarvade/Spatial_Regression/blob/master/2-Compile_Dataset_Crime_Demographics.ipynb) extracts demographic data from the American Community Survey; cleans and maps the crime data; creates a measure of retail density using parcel land use data; and then aggregates all this data to the block group level for the final dataset. 

- And lastly, the notebook containing the code used in this analysis can be downloaded [here](https://github.com/sarvade/Spatial_Regression/blob/master/3-Spatial_Econonometric_Modeling.ipynb). 

<div style="text-align: justify"> I'm primarily interested in showing the statistical processes rather than offer any practical evaluation of crime in San Francisco. Nonetheless, I think it'd be interesting to see if this relationship that makes somewhat intuitive sense will actually manifest itself in the police data. </div>
<br>


