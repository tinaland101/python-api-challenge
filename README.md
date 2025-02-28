# python-api-challenge
Overview

This project leverages Python, APIs, and data visualization libraries to analyze weather data from various cities worldwide and visualize ideal vacation locations. The project is split into two key sections:

WeatherPy: Uses the OpenWeatherMap API to retrieve and analyze weather data, showcasing the relationship between latitude and various weather conditions.

VacationPy: Uses the Geoapify API to find ideal vacation spots based on specific weather criteria and locates nearby hotels.

Project Structure

python-api-challenge/
│-- WeatherPy/
│   │-- WeatherPy.ipynb
│   │-- output_data/
│   │   ├── cities.csv
│   │   ├── Fig1.png (Latitude vs Temperature)
│   │   ├── Fig2.png (Latitude vs Humidity)
│   │   ├── Fig3.png (Latitude vs Cloudiness)
│   │   ├── Fig4.png (Latitude vs Wind Speed)
│   │-- api_keys.py (Excluded in .gitignore)
│   └── README.md
│
│-- VacationPy/
│   │-- VacationPy.ipynb
│   │-- output_data/
│   │   ├── city_humidity_map.png
│   │   ├── hotel_map.png
│   │   ├── city_humidity_map.html
│   │   ├── hotel_map.html
│   └── README.md
└── .gitignore

WeatherPy

Objective:

To analyze weather conditions across cities worldwide and evaluate how they relate to latitude.

Steps:

Generate Cities:

Uses the citipy library to generate 500+ random cities worldwide.

Retrieves weather data using the OpenWeatherMap API.

Analyze Weather Data:

Creates scatter plots for:

Latitude vs. Temperature

Latitude vs. Humidity

Latitude vs. Cloudiness

Latitude vs. Wind Speed

Computes linear regression for each relationship in the Northern and Southern Hemispheres.

Store and Export Data:

Saves the retrieved data into cities.csv.

Exports visualizations as PNG files.

Key Findings:

Temperature decreases as latitude increases, particularly in the Northern Hemisphere.

No strong correlation was found between humidity, cloudiness, wind speed, and latitude.

VacationPy

Objective:

To visualize ideal vacation locations based on weather conditions and locate nearby hotels.

Steps:

Create a City Humidity Map:

Uses hvPlot to plot city locations with point sizes representing humidity levels.

Saves the map as city_humidity_map.png.

Filter Ideal Vacation Locations:

Selects cities with temperatures between 21°C and 27°C, wind speeds below 4.5 m/s, and no cloud cover.

Saves the filtered locations in a new DataFrame.

Find Nearby Hotels:

Uses the Geoapify API to find hotels within 10 km of each ideal location.

Stores hotel names in hotel_df.

Create a Hotel Map:

Uses hvPlot to visualize vacation spots with hotel details.

Saves the map as hotel_map.png.

Key Findings:

Most ideal vacation spots were found near coastal regions.

Many locations did not have a hotel within 10 km, highlighting potential tourism opportunities.

Installation and Dependencies

Required Libraries:

pandas

numpy

matplotlib

requests

time

scipy.stats

hvplot.pandas

selenium (for saving maps as PNG)

Setup Instructions:

Clone this repository:

git clone https://github.com/your-username/python-api-challenge.git

Navigate to the project directory:

cd python-api-challenge

Install dependencies:

pip install -r requirements.txt

Add your API keys in api_keys.py:

weather_api_key = "your_openweather_api_key"
geoapify_key = "your_geoapify_api_key"

Run the Jupyter notebooks in order (WeatherPy.ipynb first, then VacationPy.ipynb).

Results

WeatherPy Output:

Generated scatter plots stored in output_data/

Fig1.png - Latitude vs. Temperature

Fig2.png - Latitude vs. Humidity

Fig3.png - Latitude vs. Cloudiness

Fig4.png - Latitude vs. Wind Speed

VacationPy Output:

 Generated maps stored in output_data/

city_humidity_map.png - City humidity distribution

hotel_map.png - Hotels in ideal vacation spots

Conclusion

This project demonstrates how to use APIs, data analysis, and visualization techniques to understand global weather patterns and identify travel destinations based on weather preferences.

 Next Steps:

Improve hotel search by broadening the search radius or including multiple results.

Enhance data accuracy by using real-time weather updates.
