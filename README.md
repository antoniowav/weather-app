# Weather App

This Weather App is a simple web application that displays current weather information for a user's current location or any searched city. It uses the OpenWeatherMap API to fetch weather data and provides functionality to toggle between Celsius and Fahrenheit units.

## Features

- Display current weather for user's geolocation
- Search for weather information by city name
- Toggle between metric (Celsius) and imperial (Fahrenheit) units
- Display detailed weather information including temperature, weather condition, real feel, humidity, wind speed, and pressure

## Installation

1. Clone the repository or download the code.
2. Ensure you have a modern web browser installed.

## Usage

1. Open `index.html` in a web browser.
2. Allow the browser to access your geolocation to get the current weather for your location.
3. Use the search form to look up weather information for a specific city.
4. Click the Celsius or Fahrenheit buttons to switch between units.

## Code Overview

### State Variables

- `currCity`: Stores the current city being displayed.
- `units`: Stores the unit system, either "metric" (default) or "imperial".
- `backupCity` and `backupCountry`: Store the last successful city and country, used as a fallback.

### Selectors

DOM elements are selected and assigned to variables for easy manipulation:
- `city`, `datetime`, `weather__forecast`, `weather__temperature`, `weather__icon`, `weather__minmax`, `weather__realfeel`, `weather__humidity`, `weather__wind`, `weather__pressure`.

### Event Listeners

- **Search Form**: On form submission, prevents the default action, updates `currCity`, and calls `changeWeather()` to fetch and display the new weather information.
- **Unit Buttons**: On button click, updates the `units` variable and calls `getWeather()` to refresh the weather information in the selected unit system.

### Functions

- `convertTimeStamp(timestamp, timezone)`: Converts a Unix timestamp and timezone offset to a human-readable string.
- `convertCountryCode(country)`: Converts a country code to its full name using the `Intl.DisplayNames` API.
- `getWeather()`: Fetches the weather for the user's current geolocation and updates the DOM with the fetched data.
- `changeWeather()`: Fetches the weather for the `currCity` and updates the DOM. If the city is not found, it displays an error message and reverts to the last known good city.

### API Usage

The app uses the OpenWeatherMap API to fetch weather data. Ensure you replace the `API_KEY` with your own API key from OpenWeatherMap.

### Error Handling

- If geolocation is not supported or fails, an error message is displayed.
- If a city is not found, a temporary error message is shown, and the display reverts to the last known good city.


## Notes

- Ensure the OpenWeatherMap API key is valid and replace the placeholder API key in the script.
- Style the application using CSS to make it visually appealing.

This README provides an overview and usage instructions for the Weather App. For any further questions or issues, feel free to reach out.