# python-api-challenge
I used my knowledge of Python requests, APIs, and JSON traversals to analyze weather data (Part 1) and create a heatmap with the cities with my preferred weather conditions (Part 2).

## Part 1: WeatherPy
I created a Python script to visualize weather data of over 500 cities at different distances from the equator. 

1. In order to create the list of cities I created a set of random latitude and longitude combinations, used the `citipy` library to find the nearest city, and stored the name of the city and the latitude and longitude in a list. I used `len()` to confirm the list of cities was longer than 500, it was `626`.

2. I used the `OpenWeatherMap API`to obtain the `city`, `cloudiness`, `country`, `date`, `humidity`, `latitude`, `longitude`, `maximum temperature`, and `wind speed` for each city in my list.

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/data_retrieval.png)

3. I used the `pandas` library to create a dataframe with the columns `City`, `Lat`, `Lng`, `Max Temp`, `Humidity`, `Cloudiness`, `Wind Speed`, `Country`, and `Date`. Then, I exported the dataframe to a csv named `cities.csv`

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/cities.png)

4. I created a dataframe with the columns `Lat`, `Lng`, `Max Temp`, `Humidity`, `Cloudiness`, `Wind Speed`, and `Date`. I used `count()` to obtain the count of each column, I used `mean()` to obtain the means, `std()` to obtain the standard deviation, `min()` to obtain each minimum, `quantile` to obtain the 25%, 50% and 75% quantile values, and `max()` to obtain the maxima.

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/weather_info.png)

5. I created a scatter plot with matplotlib that displayed the maximum temperature and latitude. I divided the northern hemisphere and southern hemisphere data and use `linregress()` from `scipy.stats` to create a linear regression line for each hemisphere.

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_temp.png)
![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_temp_north.png)
![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_temp_south.png)

6. I created a scatter plot that displayed the humidity and latitude. And plots for the northern and southern hemisphere with a linear regression line.

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_humidity.png)
![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_humidity_north.png)
![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_humidity_south.png)

7. I created a scatter plot that displayed the cloudiness and latitude. And divided the data for the northern and southern hemispheres with a linear regression line.

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_cloudiness.png)
![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_cloudiness_north.png)
![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_cloudiness_south.png)

8. I created a scatter plot that displayed the wind speed and latitude. And plotted the northern and southern hemispheres separately with a linear regression line.

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_windspeed.png)
![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_windspeed_north.png)
![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/lat_windspeed_south.png)

9. Based on the information from the tables and scatter plots I created, I concluded that:
    - As cities get closer to the equator (latitude of 0) the maximum temperature rises. When looking at cities in the Southern hemisphere there is a clear upwards trend in maximum temperature as latitude rises to 0 degrees (r-squared is 0.70). Meanwhile, when looking at cities in the Northern hemisphere there is a clear downwards trend in maximum temperature as latitude rises and moves further away from 0 degrees (r-squared is 0.34).
    - In both the Northern and the Southern hemispheres the r-squared value for the linear regression for cloudiness is very low, 0.0062 and 0.0013 respectively. This means that the level of correlation is low. Therefore, there are no clear trends showing any differences in cloudiness across latitudes.
    - In the Northern hemisphere humidity decreases as latitude increases, the r-squared value is 0.0058. In the Southern hemisphere humidity also decreases as latitude increases, the r-squared value is 0.013. The r-squared value in both hemispheres is low, therefore there is no strong correlation, humidity does not seem to change much as latitude changes.
    - In the Northern hemisphere wind speed increases slightly as latitude increases, r-squared is 0.042. In the Southern hemisphere wind speed decreases slightly as latitude increases, r-squared is 0.28. The r-squared value in both hemispheres is low, showing that there is no strong correlation, wind speed does not change much as latitude changes.

## Part 2: VacationPy
I used the `Geoapify API` and the `geoViews` Python library to plan future vacations based on my ideal weather conditions.

1. I imported the list of cities stored in the `cities.csv` file from Part 1 and stored the data in a dataframe.

2. I used the `gmaps` library to create a heatmap that displayed each city and the humidity of each city determined the size of the marker.

3. I created a new dataframe that included only cities where the maximum temperature was below 82F and above 69F, a humidity below 70%, no cloudiness, and wind speed below 5 mph.

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/cities_ideal.png)

4. I added a `Hotel Name` column and used `gmaps` to search hotels within 5000 meters from each city and stored the closest hotel to the latitude and longitude set for each city. 

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/cities_hotels.png)

5. Lastly, I created a heatmap with the locations with my ideal weather with hover messages that showed where the hotels are, and created a display box showing the city name, hotel name, and country.

![alt text](https://github.com/glongo001/python-api-challenge/blob/main/WeatherPy/Resources/hotels.png)
