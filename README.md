# Weather App

A responsive weather application that fetches real-time weather data for any city using the OpenWeatherMap API. Built with plain HTML, CSS, and JavaScript — no frameworks, no build tools.

## Features

- **City search** — look up current weather for any city worldwide
- **Live weather data** — temperature, humidity, wind speed, and current conditions
- **Sunrise & sunset times** — calculated correctly using the city's own timezone offset (not the visitor's local time)
- **Local time display** — shows the current local time in the searched city
- **Weather icon** — pulls the matching condition icon from OpenWeatherMap
- **Error handling** — clear messages for invalid city names, empty input, and network failures
- **Responsive layout** — adapts cleanly from desktop down to mobile screens

## Tech Stack

- **HTML5** — semantic structure and accessibility (ARIA live region for screen readers)
- **CSS3** — custom properties (CSS variables), flexbox, CSS grid, and media queries for responsiveness
- **JavaScript (ES6+)** — `async/await`, the Fetch API, and DOM manipulation
- **OpenWeatherMap API** — REST API for live weather data

## How It Works

`script.js` builds a request URL from the city name and an API key, fetches the current weather as JSON from OpenWeatherMap, and updates the DOM with the response. Key implementation details:

- Uses `async/await` with `try/catch` for clean error handling
- Distinguishes between a "city not found" (404) response and other network errors, showing a relevant message for each
- Converts UTC timestamps (sunrise, sunset, local time) into the searched city's local time using the `timezone` offset returned by the API, rather than relying on the browser's own timezone
- Builds the weather icon URL dynamically based on the icon code returned by the API

## Project Structure

```
weather-app/
├── index.html       # Page structure and markup
├── styles.css        # Styling and responsive layout
└── script.js         # API calls, DOM updates, and error handling
```

## Setup & Usage

1. Clone this repository
   ```bash
   git clone https://github.com/your-username/weather-app.git
   ```
2. Get a free API key from [OpenWeatherMap](https://openweathermap.org/api)
3. Open `script.js` and replace the placeholder with your API key:
   ```javascript
   const API_KEY = 'YOUR_OPENWEATHERMAP_API_KEY';
   ```
4. Open `index.html` in your browser — no server or build step required

## What I Learned

This project was a hands-on introduction to working with a real third-party API: handling asynchronous requests, managing different error states, and the importance of timezone-aware time formatting (an easy bug to introduce when displaying data for a different location than your own). It also reinforced fundamentals like responsive layout and accessible markup without relying on a framework.

## Live Demo

*(Add a link here once deployed — e.g. via Netlify, Vercel, or GitHub Pages)*

## License

This project is open source and available for learning purposes.
