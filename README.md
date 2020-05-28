# Predicting Pedestrian Footfall: <br /> Location Data Analysis of Melbourne, Australia

Utilizing datasets provided by the city of Melbourne, I analyzed sidewalk sensor count data in relation to location features of the city. 

## Table of Contents
* Project Goals
* Time Series Analysis
* Mapping Location Features
* Regression to Predict Daily Footfall Based on Location Features
* Forecasting Future Footfall
* Future Ideas


## Project Goals
After studying city planning and design in university, I have been very interested in how people move around a city and the trends that develop in pedestrian traffic. To explore this interest from a data perspective, I chose to analyze a dataset from Melbourne, Australia that has hourly counts from sidewalk sensors around the city. In order to better understand the flow of people through the city, I also integrated several other datasets with features of the city such as landmarks and bike share docks. By combining the pedestrian sensor data with nearby features of the city, I hoped to gain a stronger understanding of the location features that influence when and where people walk in various areas of the city. The findings of this project would be influential to prospective business owners who are deciding where to open a physical store so that they know which areas are the busiest at certain times. City planners could also find this analysis useful for predicting how much a new development or city feature would impact the nearby pedestrian footfall.

**Prediction:** Nearby buildings and city infrastructure impact the amount of footfall an area receives. <br />
**Goals:** Discover which features have the greatest impact on footfall, and make prediction about future trends. <br />

**Data sources:**
* Hourly sidewalk sensor counts from 2009 to present
* Hourly Weather (scraped)
* Yearly Building Data (census information with building use, number of floors & location)
* Bike Dock Locations & capacities
* Landmarks and Points of Interest in the city
* Street lighting owned by the city

## Time Series Analysis

The first step was to closely analyze the Hourly Sensor Count Data. Here is Tableau map visualisation of all the sensor's locations across the city.

<img src = "visuals/maps/sensor map.png">
This data set had location coordinates for each sensor, a sensor ID number, datetime of hourly records, and hourly count values. During this stage I also performed data cleaning on the data set. Many sensors would have faulty records, and the counts would drop out for weeks or months at a time. Other sensors would be added halfway through the year. For consistancy, I created a function to create a list of sensors that had full records for at least 12 months at a time. Since the records were not very stable for the first two years, the scope of the sensors was altered to be 2011-2018. This resulted in a list of different valid sensors for each year that looked like this:



My first step was to perform a time series analysis for each sensor, and see how accurately I could forecast future footfall based on past counts and trends. 

Here is two sensors that had valid records for the entire period 2011-2019:
*map*

To begin understanding the trends and patterns for an individual sensor, I created heatmaps for each sensor. 
*heatmap*
From these two different sensors we can already notice that there are dramatically different trends. Sensor 9 appears to be in a business district since it is almost exclusively busy on Monday-Friday, while sensor 2 is busiest on Fridays and in December. 
