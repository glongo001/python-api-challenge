# python-api-challenge

# Part 1: WeatherPy
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

