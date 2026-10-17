# ClearSky — Real-Time Weather App

ClearSky is a responsive weather dashboard built with plain HTML, CSS and JavaScript. It shows the current weather, today's highlights, an hourly forecast and a 5-day forecast for any city in the world, using data from the [OpenWeather API](https://openweathermap.org/api).

Built as **Task 3** of the **Elevvo Internship Program**.

**Live demo:** https://bishoy-labib-ezzat.github.io/clear-sky-weather-app/

## Features

- **City search** with live suggestions as you type (debounced, powered by OpenWeather Geocoding).
- **Current location** using the browser's Geolocation API, with an automatic fallback to an approximate IP-based location if permission is denied.
- **Current weather**: temperature, conditions, date and location name.
- **Today's highlights**:
  - Air Quality Index (PM2.5, SO₂, NO₂, O₃) with a color-coded level badge
  - Sunrise and sunset times (in the city's local time)
  - Humidity, pressure, visibility and "feels like" temperature
- **Hourly forecast** for the next 24 hours (3-hour steps), with temperature and wind speed/direction.
- **5-day forecast** with daily icons and maximum temperatures.
- **Hash-based routing** so each city has its own shareable URL, plus a 404 page for unknown routes.
- Loading state and fade-in animation while data loads.

## Tech Stack

- HTML5
- CSS3 (custom properties, responsive layout)
- Vanilla JavaScript (ES modules, Fetch API)
- [OpenWeather API](https://openweathermap.org/api): Current Weather, 5 Day / 3 Hour Forecast, Air Pollution, Geocoding
- [ipify](https://www.ipify.org/) and [ipinfo](https://ipinfo.io/) for the approximate-location fallback
- Google Fonts (Nunito Sans) and Material Symbols Rounded icons

## Project Structure

```
.
├── index.html            # Page layout
├── ClearSky.svg          # Favicon
├── css/
│   └── style.css         # All styles
├── font/
│   └── material-symbol-rounded.woff2
├── images/
│   ├── clearsky_logo_light.png
│   └── weather_icons/    # Weather condition and wind direction icons
└── js/
    ├── api.js            # OpenWeather API key, fetch helper and endpoint URLs
    ├── app.js            # Search, rendering of all weather sections
    ├── module.js         # Date/time helpers, unit conversion, AQI labels
    └── service.js        # Hash router and location handling
```

## Getting Started

1. **Clone the repository**

   ```bash
   git clone https://github.com/Bishoy-Labib-Ezzat/clear-sky-weather-app.git
   cd clear-sky-weather-app
   ```

2. **Add your OpenWeather API key** (optional but recommended)

   Create a free key at [openweathermap.org](https://home.openweathermap.org/api_keys) and replace the value of `apiKey` in [`js/api.js`](js/api.js).

3. **Run it with a local server**

   The app uses ES modules, so opening `index.html` directly from the file system won't work. Serve the project folder with a local server instead, for example:

   ```bash
   npx serve .
   ```

   or use the **Live Server** extension in VS Code. Then open the URL it prints (e.g. `http://localhost:3000`).

## Routes

| Route | What it shows |
| --- | --- |
| `#/current-location` | Weather for your current position (default) |
| `#/approximatelocation` | Weather for your IP-based location (used when geolocation is blocked) |
| `#/weather?lat=<lat>&lon=<lon>` | Weather for the given coordinates (used by search results) |

Any other route shows the 404 page.

## Credits

- Weather data: [OpenWeather](https://openweathermap.org/)
- Icons: [Material Symbols](https://fonts.google.com/icons)

## Author

**Bishoy Labib** — [@Bishoy-Labib-Ezzat](https://github.com/Bishoy-Labib-Ezzat)
