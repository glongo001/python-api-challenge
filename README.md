# python-api-challenge
I used my knowledge of Python requests, APIs, and JSON traversals to analyze weather data (Part 1) and create a heatmap with the cities with my preferred weather conditions (Part 2).

# Part 1: WeatherPy
I created a Python script to visualize weather data of over 500 cities at different distances from the equator. 

1. In order to create the list of cities I created a set of random latitude and longitude combinations, used the `citipy` library to find the nearest city, and stored the name of the city and the latitude and longitude in a list. I used `len()` to confirm the list of cities was longer than 500, it was `606`.

2. I used the `OpenWeatherMap API`to obtain the `city`, `cloudiness`, `country`, `date`, `humidity`, `latitude`, `longitude`, `maximum temperature`, and `wind speed` for each city in my list.

3. I used the `pandas` library to create a dataframe with the columns `City`, `Lat`, `Lng`, `Max Temp`, `Humidity`, `Cloudiness`, `Wind Speed`, `Country`, and `Date`. Then, I exported the dataframe to a csv named `cities.csv`



To get started, the code required to generate random geographic coordinates and the nearest city to each latitude and longitude combination is provided.
- Generated a list of 500+ cities and obtained weather information such as cloudiness, humidity, maximum temperature, and wind speed. Exported the list to a csv file.
- Obtained the count of rows, the mean value for each variable, the standard deviation, the minimum, the 25%, 50% and 75% quantiles, and the maximum of each variable.
- Created scatterplots showing Temperature(F) vs. Latitude, Humidity (%) vs. Latitude, Cloudiness (%) vs. Latitude, Wind Speed (mph) vs. Latitude.
- Created scatterplots comparing the same conditions but divided them into the Northern hemisphere (latitude >= 0) and the Southern hemisphere (latitude <= 0).
- Generated regression lines for the scatterplots and analyzed the trends in each.

# Part 2: VacationPy
- Used the list of cities stored in the csv file from Part 1 to create a heatmap using the latitudes and longitudes as locations and humidity as the weight. 
- Created new dataframe to store only cities with my ideal weather conditions.
- Used the dataframe to search for nearby hotels in each city and stored the hotel name in the new dataframe.
- Added a marker layer to show pins where the hotels are, and created a display box showing the city name, hotel name, and country.

