# Capstone
# Pedestrian-Footfall-Melbourne-Australia
Location data analysis of footfall patterns in the city of Melbourne, Australia. This was my Final Capstone project from the three month Data Science Immersive I completed at General Assembly London. 

Taking data sets provided by Melbourne's data website, I analyzed sidewalk sensor count data in relation to location features of the city. 

Prediction: Nearby buildings and city infrastructure impact the amount of footfall an area receives. 
Goals: Discover which features have the greatest impact on footfall, and make prediction about future trends.

Data sources:
-Hourly sidewalk sensor counts from 2009 to present
-Hourly Weather
-Yearly Building Data (census information with building use, number of floors & location)
-Bike Dock Locations & capacities
-Landmarks and Points of Interest in the city
-Street lighting owned by the city

*PROCESS*

First looking just at the Hourly Sensor Count Data ...
<img src = "visuals/sensor map.png">
This data set had location coordinates for each sensor, a sensor ID number, datetime of hourly records, and hourly count values. During this stage I also performed data cleaning on the data set. Many sensors would have faulty records, and the counts would drop out for weeks or months at a time. Other sensors would be added halfway through the year. For consistancy, I created a function to create a list of sensors that had full records for at least 12 months at a time. Since the records were not very stable for the first two years, the scope of the sensors was altered to be 2011-2018. This resulted in a list of different valid sensors for each year that looked like this:

sensors_2011 = [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18]
sensors_2012 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18]
sensors_2013 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 13, 14, 16, 17, 18]
sensors_2014 = [2,3,4,5,6,8,9,10,11,12,13,14,15,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32]
sensors_2015 = [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 18, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 36, 38, 39, 40]
sensors_2016 = [1, 2, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 17, 18, 19, 20, 21, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 36, 37, 38, 39, 40, 42, 43, 44, 53]
sensors_2017 = [1, 2, 3, 6, 7, 8, 9, 10, 11, 12, 15, 17, 18, 19, 20, 21, 23, 24, 25, 26, 27, 28, 29, 31, 33, 34, 35, 37, 39, 40, 42, 43, 44, 53]
sensors_2018 = [1, 2, 4, 5, 6, 7, 8, 9, 10, 11, 12, 15, 18, 19, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 33, 34, 35, 36, 37, 40, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53]
sensors_2019 = [1, 2, 3, 4, 5, 6, 8, 9, 10, 11, 12, 14, 15, 17, 18, 19, 20, 21, 23, 24, 26, 27, 28, 30, 31, 34, 35, 36, 37, 39, 40, 42, 43, 44, 46, 47, 48, 49, 50, 51, 52, 53, 54, 56, 57, 58]

My first step was to perform a time series analysis for each sensor, and see how accurately I could forecast future footfall based on past counts and trends. 

Here is two sensors that had valid records for the entire period 2011-2019:
*map*

To begin understanding the trends and patterns for an individual sensor, I created heatmaps for each sensor. 
*heatmap*
From these two different sensors we can already notice that there are dramatically different trends. Sensor 9 appears to be in a business district since it is almost exclusively busy on Monday-Friday, while sensor 2 is busiest on Fridays and in December. 
