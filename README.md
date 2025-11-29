# Clickmap

An interactive, single-page world map application with real-time weather, local time, and comprehensive city/country search. Features a modern Flightradar24-inspired design with Apple Weather-style widgets and seamless navigation.

## Live Demo

Open the hosted demo here:

https://taynazdev.github.io/GeoMapLink/

## Features

### Core Functionality
- **Interactive country selection** with click interactions and visual feedback
- **City selector dropdown** to view weather and time for major cities within each country
- **Real-time search** for countries and cities with instant filtering and click-to-select
- **Auto-detection** of user's country on page load using geolocation
- **Infinite horizontal scrolling** with seamless wrapping (5 map copies)
- **Vertical panning** when zoomed in with bounds constraints
- **macOS-style dock** at bottom center for zoom controls

### Data & Information
- **Apple Weather-style widget** with dynamic icons (sun, moon, clouds, rain, snow, thunder, fog)
- **Real-time weather data**: temperature, humidity, wind speed, and conditions for any city
- **Local time display** with timezone support for each selected city
- **Country information**: flag, population, and Wikipedia link
- **Major cities database** for 12+ countries (USA, China, India, UK, France, Germany, Japan, Brazil, Australia, Canada, Russia, Mexico)

### Design & UI
- **Flightradar24-inspired interface** with gradient overlay header
- **Terrain-based country coloring**: realistic colors matching dominant landscapes (deserts in sandy tans, rainforests in deep greens, etc.)
- **Country name labels** displayed on map at centroids, zoom-responsive sizing
- **Side-by-side layout**: info panel (left), map (center), search sidebar (right)
- **Smooth transitions** and modern, professional UI throughout
- **Responsive design** optimized for all screen sizes

### Geographic Features
- **Satellite mode toggle**: Switch between map view and satellite imagery
  - 5 seamless satellite image copies for infinite scrolling
  - Local image file support (`satellite.jpg` or `satellite.png`)
  - Automatic fallback to remote sources if local file not found
- **Geographic reference lines**: Equator, Tropics, Arctic/Antarctic Circles
- **Timezone meridian lines** with UTC offset labels
- **Animated splash screen** with paint splash effect and loading progress bar
- **Palestine mapping** (replaces Israel throughout application)

## Quick Start

You only need a browser and an internet connection (CDNs are used).

1. Clone or download this repo
2. **For satellite mode**: Add a `satellite.jpg` or `satellite.png` file to the root directory
   - Use an equirectangular projection image (like Blue Marble)
   - Recommended: 5400x2700 resolution or higher
3. Open `index.html` in your browser

That's it. No build step required.

## Project Structure

- `index.html` — Single-file app with embedded CSS and JavaScript
- `README.md` — This documentation

## Tech Stack

- **D3.js v7** for SVG rendering, zoom/pan, and infinite scrolling
- **TopoJSON v3** world map data (world-atlas)
- **REST Countries API v3.1** for country information and timezone data
- **Open-Meteo API** for real-time weather data (no API key required)
- **ipapi.co** for user geolocation detection
- **Google Fonts** "Splash" by Robert Leuschke for branding

## Usage

### Search
- Type in the search bar on the right to find countries or cities
- Click any result to view detailed information
- Search works instantly with debounced input (300ms)

### City Selection
- Click any country to view its information
- Use the city dropdown to switch between major cities
- Weather, time, and icons update automatically for selected city

### Map Navigation
- Click and drag to pan horizontally (infinite scrolling)
- Zoom in/out using the dock controls at bottom center
- Vertical panning enabled when zoomed in
- Reset button returns to default view

## Notes

- Automatically detects and displays your country on page load
- Weather icons change based on conditions and time of day (day/night detection)
- All country names visible on map with intelligent sizing
- Some country names are normalized for better API matching
- Palestine replaces Israel throughout the application

## Changelog

See `CHANGELOG.md` for a history of notable changes.

## License

See `LICENSE` for details.

