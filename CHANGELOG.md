# Changelog

All notable changes to this project will be documented in this file.

The format is based on Keep a Changelog, and this project aims to follow
Semantic Versioning once releases begin.

## [1.0.0] - 2025-11-28

### Added
- Search toggle button in dock: click magnifying glass icon to show/hide search sidebar
- Search sidebar now slides in as overlay from right side with backdrop
- Close button in search sidebar for easy dismissal
- Dock styling updated to Apple liquid glass aesthetic with translucent background and blur effect

### Changed
- Font changed from "Splash" (brush script) to "Inter" (minimal sans-serif) for logo and country names
- Dock appearance: semi-transparent grey gradient background with reduced blur (25px)
- Dock buttons reduced to 36px for more compact design
- Country labels now perfectly centered at country centroids (removed vertical offset)
- Search sidebar: changed from fixed panel to slide-in overlay for better space efficiency

### Fixed
- Search sidebar positioning and toggle functionality
- Icon sizing and dock proportions for better visual balance

## [0.4.0] - 2025-11-20

### Added
- City selection dropdown: choose from major cities within each country to view specific weather and time data
- Search sidebar: searchable list of all countries and major cities with instant filtering
- Major cities database for 12+ countries including USA, China, India, UK, France, Germany, Japan, Brazil, Australia, Canada, Russia, and Mexico
- Dynamic city data fetching: real-time weather and local time for any selected city
- Search functionality with debounced input and result limiting
- Click-to-select from search results to view country/city information

### Changed
- Info panel now displays "City" instead of "Capital" label
- City dropdown automatically updates all info (weather, time) when changed
- Default view shows capital city (first city in list) for countries with major cities data
- Search sidebar positioned on right side of screen for better balance
- Layout: info panel (left), map (center), search sidebar (right)
- Map container now flexible width between panels

## [0.3.0] - 2025-11-20

### Added
- Terrain-based country coloring: countries now display realistic colors based on their dominant landscape (deserts in sandy tans, rainforests in deep greens, temperate regions in light greens, Antarctica in white, etc.)
- Real-time weather information for each country's capital city (condition, temperature, humidity, wind speed)
- Current local time display for each country's capital city
- Extended map rendering from 3 to 5 copies for seamless infinite scrolling
- Timezone and latitude lines now render across all 5 map copies
- Animated splash screen with paint splash effect and brush script "Splash" font by Robert Leuschke
- Country name labels displayed on the map at each country's centroid
- Permanently visible info panel on left side for country information (replaces slide-in panel)
- Project rebranded to "Clickmap" with new logo styling
- Apple Weather-style widget for displaying weather conditions with gradient background, large temperature display, and icons
- Weather condition icons (sun, moon, clouds, rain, snow, thunder, fog) based on current weather
- Auto-detection of user's country on page load using geolocation API (ipapi.co)
- Black-to-transparent gradient overlay at top of page for modern Flightradar24-style header

### Changed
- Viewport: set initial page zoom to 100% (normal size)
- SVG viewport dimensions: reduced width to 465.6px (half original width), height 612px
- Map projection: reduced scale to 100 and adjusted vertical positioning for optimal Antarctica visibility
- Map interaction: enabled vertical panning when zoomed in with bounds constraints to prevent panning beyond map edges
- SVG aspect ratio: changed from "slice" to "meet" to fit height instead of width
- Ocean background: extended 5x width to cover all wrapped map copies
- UTC timezone labels: reduced font size from 9px to 7px for better visual balance
- Timezone handling: improved to support both IANA timezone identifiers and UTC offset calculations
- UI Layout: info panel now permanently visible on left side, map and panel side-by-side
- Zoom controls: moved to macOS-style dock at bottom center with translucent background and blur effect
- Background: changed from purple gradient to dark (#1a1a1a) for modern look
- Header: replaced solid header bar with fixed gradient overlay at top with centered logo
- Top gradient: reduced height to 60px (half original size) with smaller logo
- Country labels: positioned 15px lower to avoid overlap with top gradient, all names now centered at country centroids
- Info panel header: increased top padding to 4rem to prevent flag/country name from clashing with top gradient
- Weather display: redesigned as tall widget (400px min-height) with large icon, temperature, and grid layout for details
- Weather icons: now dynamically update based on actual weather conditions and time of day (day/night detection)
- Terrain colors: enriched green colors for tropical rainforests (deeper, richer greens) and temperate regions
- Israel renamed to Palestine throughout the application
- Logo font: applied "Splash" brush script font to all "Clickmap" branding

### Fixed
- Vertical scrolling: locked page height to 100vh with overflow hidden to prevent all scrolling
- Vertical panning: now locked at zoom level 1, enabled only when zoomed in
- Map positioning: adjusted center latitude and translation for better continent placement and Antarctica visibility
- Map wrapping: increased coverage to eliminate gaps when scrolling horizontally
- Geographic lines continuity: timezone and latitude lines now extend across all map copies
- Country name visibility: moved labels down to prevent overlap with top gradient overlay
- Weather emoji icons: fixed encoding issues and added proper day/night detection
- Country label positioning: all labels now properly centered, removed logic that hid labels for small countries

### Removed
- Footer removed to maximize map viewing area
- Slide-in animation for info panel (now always visible)
- Close button for info panel
- Traditional header bar with subtitle
- Rounded corners and margins on map/panel (full edge-to-edge design)
- Label hiding logic: all country names now visible regardless of size

## 0.2.0 - 2025-11-20

### Added
- Geographic reference lines: Equator, Tropics of Cancer and Capricorn, Arctic and Antarctic Circles (grey, on top of countries)
- Timezone meridian lines with UTC offset labels (blue, subtle)
- Infinite horizontal scrolling with seamless wrapping (3 map copies with auto-repositioning)
- Mobile viewport optimizations with dynamic viewport height support

### Changed
- Map styling: countries now have white fill by default, purple on hover/click
- Ocean background: blue fill added
- Interaction: changed from hover to click-only for better card usability
- Layout: compact header, footer, and margins; zoomed out projection to eliminate vertical scrolling
- Timezone lines: made more subtle with reduced opacity and lighter colors

### Fixed
- Pointer events on ocean to allow clicking through to countries
- Map loading issue with latitude lines rendering
- Infinite scroll wrapping using proper projection width calculations
- Mobile viewport: map now fills entire designated area

### Removed
- National anthem audio player feature (completely removed)

## 0.1.0 - 2025-11-15

### Added
- Initial interactive single-page app (`index.html`) with D3.js world map, hover/click interactions, info card, and zoom controls. ([f2acd1d])
- README with live demo link and project overview. ([9991f65])
- CHANGELOG.md file with initial version tracking

<!-- Commit references -->
[f2acd1d]: https://github.com/TaynazDev/GeoMapLink/commit/f2acd1d
[9991f65]: https://github.com/TaynazDev/GeoMapLink/commit/9991f65
