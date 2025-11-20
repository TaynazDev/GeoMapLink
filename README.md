# Clickmap

An interactive, single-page world map that highlights countries on click and shows a rich info card with real-time data (flag, capital, local time, weather, population, and a Wikipedia link). Built with a clean, minimal UI and smooth transitions.

## Live Demo

Open the hosted demo here:

https://taynazdev.github.io/GeoMapLink/

## Features

- Interactive country selection with click interactions
- Info card with flag, capital, local time, real-time weather (temperature, humidity, wind speed), population, and Wikipedia link
- Infinite horizontal scrolling with seamless wrapping
- Geographic reference lines (Equator, Tropics, Arctic/Antarctic Circles)
- Timezone meridian lines with UTC labels
- Vertical panning enabled when zoomed in with bounds constraints
- Zoom in/out and reset controls for detailed exploration
- Responsive layout optimized for all screen sizes
- Smooth transitions and modern UI
- Real-time data from REST Countries API and Open-Meteo Weather API
- Rendering via D3.js + TopoJSON

## Quick Start

You only need a browser and an internet connection (CDNs are used).

1. Clone or download this repo
2. Open `index.html` in your browser

That’s it. No build step required.

## Project Structure

- `index.html` — Single-file app with embedded CSS and JavaScript
- `README.md` — This documentation

## Tech Stack

- D3.js v7 for SVG rendering, zoom/pan, and infinite scrolling
- TopoJSON v3 world map data (world-atlas)
- REST Countries API v3.1 for country information and timezone data
- Open-Meteo API for real-time weather data

## Notes

- The info card is positioned to avoid going off-screen when possible
- Zoom controls help access small countries and islands
- Some country names are normalized for better API matching

## Changelog

See `CHANGELOG.md` for a history of notable changes.

## License

See `LICENSE` for details.

