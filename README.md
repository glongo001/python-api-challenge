# python-api-challenge
I used my knowledge of Python requests, APIs, and JSON traversals to analyze weather data (Part 1) and create a heatmap with the cities with my preferred weather conditions (Part 2).

## Part 1: WeatherPy
I created a Python script to visualize weather data of over 500 cities at different distances from the equator. 

1. In order to create the list of cities I created a set of random latitude and longitude combinations, used the `citipy` library to find the nearest city, and stored the name of the city and the latitude and longitude in a list. I used `len()` to confirm the list of cities was longer than 500, it was `606`.

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

## Part 2: VacationPy
- Used the list of cities stored in the csv file from Part 1 to create a heatmap using the latitudes and longitudes as locations and humidity as the weight. 
- Created new dataframe to store only cities with my ideal weather conditions.
- Used the dataframe to search for nearby hotels in each city and stored the hotel name in the new dataframe.
- Added a marker layer to show pins where the hotels are, and created a display box showing the city name, hotel name, and country.

