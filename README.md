# python-api-challenge
The purpose of this project was to use APIs to support claims that it gets warmer as one approaches the equator.  The project consisted of two parts, one where the weather of various cities was analyzed and the other where ideal weather conditions were applied as a filter to 1) locate cities that fit these subjective ideal weather conditions and 2) the closest accommodations within 10000m of the cities. After splitting the world into two hemispheres and applying linear regression to scatter plots based on latitude and other weather conditions, it became a bit clear that there may be some relationship between temperature increasing as one approaches the equator from the south and decreasing as one heads further north from the equator.

The two key APIs used in this project were the OpenWeather API found at https://openweathermap.org/current and the Geoapify API found at https://apidocs.geoapify.com/. 

In the first part of the project, WeatherPy, random longitudes and latitudes were generated to be matched with cities found in the citipy Python module. The weather information was then collected using the OpenWeather API which then allowed for data analysis. Key weather conditions, such as cloudiness, humidity, and max temperatures were datapoints that were gathered from the API.

Relationships between a city's latitude and the weather conditions collected from the OpenWeather API were then visualized using the matplotlib module. Scatter plots showing a city's latitude against a city's humidity,  cloudiness, windspeed, and highest temperature on the day the API call was made were then analyzed to see if indeed there was some truth to the weather getting warmer as one approachs the equator.

The r-values obtained from each individual scatter plot did not show any strong relationship between a city's latitude and any of the conditions. However, it was observed that because its r-value was negative, the linear regression of temperature and latitude for the northern hemisphere seems to indicate that as one heads further north, temperatures tend to decrease. On the other hand, because its r-value was negative, the positive r-value of the southern hemisphere's linear regression of temperature versus latitude  seems to indicate that as one heads toward the equator from the bottom of the sphere that is the world, temperatures tend to increase.

In the second part of the assignment, VacationPy, the cities that were generated in WeatherPy were further filtered to cities with temperatures between about 70 and 82 degrees F (21-28 degrees C), a humidity percentage between 25% and 65%, a wind speed of less than 7mph (3 m/s) and cloudiness less than 50%. This brought the list down to 10 cities throughout the world and using the Geoapify API, it was necessary to locate a hotel within 7 miles (10000m). The data obtained for this assignment returned zero hotels, so in order to make the work worth it, the decision to remove the search radius of 10000m and to search for ANY accommodation was made. This resulted in about eight accommodations being located starting at least 37 miles away from the city's obtained latitude and longitude under these conditions.
