# Changelog

All notable changes to this project will be documented in this file.

The format is based on Keep a Changelog, and this project aims to follow
Semantic Versioning once releases begin.

## [3.0.0-beta] - 2025-12-06

### Added
- **Experimental Features System**: Major feature flag system for beta testing
  - Real-time events/warnings bar with scrolling alerts from USGS & GDACS APIs
  - Live earthquake monitoring (magnitude 4.5+, last 24 hours)
  - Global disaster alerts (cyclones, floods, wildfires, volcanoes, etc.)
  - Comprehensive weather warnings with 25+ event type icons
  - Auto-refresh every 5 minutes with international data feeds
  - Continuous scrolling marquee (tripled content for seamless loop)
- **V0.1.0 Retro Mode**: Classic view toggle for nostalgia
  - History button in bottom-right corner (clock icon)
  - Purple gradient background matching original v0.1.0 design
  - Simple white countries with purple hover states
  - Instant popup cards when clicking countries (no transitions)
  - Classic modal design with flag, country info (capital, population, area, languages, currency)
  - Hides all modern UI elements (dock, panels, labels, events bar)
- **Enhanced Events Bar**: Massively expanded content and slower scroll speed
  - Slowed animation to 150s (2.5 minutes for full loop) for better readability
  - Added 25+ diverse monitoring status messages
  - Lightning detection, tsunami warnings, volcanic activity surveillance
  - Tornado watch systems, temperature monitoring, wind speed tracking
  - Air quality monitoring, precipitation tracking, UV index updates
  - 16+ unique event types with smart icon detection

### Changed
- **History Button Location**: Moved from dock to fixed bottom-right corner
  - 56x56px circular button with liquid glass styling
  - Independent positioning allows it to persist when dock is hidden
  - Shows/hides automatically with experimental features toggle
- **Events Bar Performance**: Optimized for continuous viewing
  - Increased event count from 5 to 8 per API source (16 total possible)
  - Content tripled to ensure no gaps in scrolling animation
  - Added comprehensive fallback messages when no active disasters
- **Retro Mode UX**: Instant card appearance for better responsiveness
  - Removed all transitions from popup cards (was 0.3s delay)
  - Cards now appear immediately on country click
  - Backdrop click and close button for dismissal
  - Auto-cleanup when switching between modes

### Fixed
- **Mode Switching**: Clean transitions between modern and retro views
  - Side panel automatically hides when entering retro mode
  - Retro card automatically hides when returning to modern mode
  - Dock visibility properly toggled in retro mode

## [2.5.1] - 2025-11-29

### Fixed
- **Performance**: Removed excessive debug console logging from satellite toggle
  - Eliminated 5+ console.log statements that were logging on every toggle
  - Removed redundant variable declarations
  - Improved toggle responsiveness
- **Satellite Mode Toggle**: Fixed vector-effect property not resetting properly when disabling satellite mode
  - Changed from `style("vector-effect", null)` to `style("vector-effect", "")`
  - Ensures borders return to normal scaling behavior
- **Terrain Colors**: Fixed inconsistent terrain color fallback references
  - All color fallbacks now consistently use `defaultTerrainColor` variable
  - Prevents hardcoded color mismatches throughout the application

## [2.5.0] - 2025-11-29

### Added
- **Experimental Features System**: Flask icon button in dock to toggle experimental features
  - Confirmation modal with "Are you sure?" prompt before enabling
  - Currently controls visibility of satellite mode toggle
  - Automatically disables satellite mode when experimental features are turned off
- **Apple Liquid Glass Aesthetic**: Complete UI redesign with translucent glass morphism
  - Search input and city dropdown now use dock-style grey gradient backgrounds
  - Capsule-shaped inputs with 9999px border-radius for perfect pill shapes
  - Backdrop blur (25px) with color saturation for depth effect
  - Inset highlights and shadows for realistic glass appearance
  - All interactive elements match macOS dock aesthetic

### Changed
- **Dock Layout**: Reorganized bottom controls for better visual hierarchy
  - Experimental features (flask) button now centered in dock
  - Satellite toggle appears in dock next to flask (when experimental features enabled)
  - All dock buttons use semi-transparent backgrounds with consistent styling
- **Input Styling**: Search bar and city dropdown completely redesigned
  - Background: Grey gradient matching dock (rgba(220,220,220,0.65) to rgba(210,210,210,0.55))
  - Text color: Dark grey (#1a1a1a) for better contrast
  - Placeholder: Semi-transparent black (40% opacity)
  - Border: White with 40% opacity
  - Enhanced inset shadows for depth
- **Satellite Toggle**: Moved from top-right to dock at bottom
  - Integrated with experimental features system
  - Capsule-shaped design (height: 48px)
  - Appears only when experimental mode is active
- **Flask Icon**: Reduced stroke width from 2.0 to 1.5 for more delicate appearance
- **Border Radius**: Increased from 22px to 9999px (capsule shape) for all liquid glass elements
- **Timezone Lines**: Disabled by default for cleaner map view (UTC clock still visible at top)

### Fixed
- **Satellite Border Thickness**: Added `vector-effect: non-scaling-stroke` to prevent borders from thickening when zooming
  - Stroke width changed to 0.5px with consistent appearance at all zoom levels
- **City Search**: All cities from search results now open properly
  - Fixed issue where cities not in majorCities array wouldn't open
  - Uses latitude/longitude data from search results directly
- **Experimental Features Toggle**: Properly restores regular map view when disabling
  - Satellite imagery fades out smoothly
  - Country colors and terrain restored
  - Ocean opacity returns to normal

## [2.0.0-beta] - 2025-11-29

### Added
- **Loading Progress Bar**: Real-time loading indicator in splash screen shows map loading progress
  - Animated progress bar with gradient styling
  - Status text updates during different loading phases
  - Progress tracking: Initializing → Loading map data → Processing countries → Rendering map → Ready
- **Stylized Logo Font**: Changed from Inter to Orbitron for more futuristic, tech-focused aesthetic
  - Applied to both main logo and splash screen title
  - Increased letter spacing for better readability

### Changed
- **Splash Screen Flow**: Map now loads during splash animation instead of after
  - Minimum splash display time: 2.5 seconds
  - Splash hides once map is loaded AND minimum time has elapsed
  - Smoother transition to main application
- **Logo Typography**: 
  - Font: Orbitron with weight 700-900
  - Letter spacing increased from -0.02em to 0.05-0.1em
  - More cohesive sci-fi/tech aesthetic

### Fixed
- **Satellite Mode**: Complete rewrite of satellite toggle functionality
  - Changed from `.style("opacity")` to `.attr("opacity")` for SVG elements
  - Added null checks for ocean rectangle
  - Smooth transitions now work correctly
  - Satellite imagery properly shows/hides with country transparency

## [2.0.0-alpha.3] - 2025-11-29

### Added
- **100 Additional Cities**: Comprehensive expansion across 40 new countries:
  - **South America**: Bolivia (4), Paraguay (3), Uruguay (3) - 10 cities
  - **Central America**: Costa Rica (3), Panama (3), Nicaragua (3), Honduras (3), El Salvador (3), Guatemala (3) - 18 cities
  - **Caribbean**: Cuba (4), Dominican Republic (3), Jamaica (3), Trinidad and Tobago (3) - 13 cities
  - **South Asia**: Nepal (3), Sri Lanka (4) - 7 cities
  - **Southeast Asia**: Cambodia (3), Laos (3), Myanmar (4) - 10 cities
  - **East Asia**: Mongolia (3), North Korea (3) - 6 cities
  - **Central Asia**: Turkmenistan (3), Kyrgyzstan (3), Tajikistan (3) - 9 cities
  - **Africa**: Senegal (3), Cameroon (3), Angola (3), Mozambique (3), Madagascar (3), Zambia (3), Malawi (3), Rwanda (3), Burundi (3), Somalia (3), Sudan (3) - 33 cities
  - **Total**: 106 new cities across 40 countries

## [2.0.0-alpha.2] - 2025-11-29

### Added
- **Massive City Database Expansion**: Added 50+ cities across 25+ new countries, with heavy focus on Middle East:
  - **Middle East**: Iran (5 cities), Iraq (4), Syria (4), Jordan (4), Lebanon (3), Kuwait (3), UAE (4), Qatar (3), Bahrain (2), Oman (3), Yemen (3), Afghanistan (3)
  - **Palestine**: Jerusalem, Ramallah, Gaza, Hebron, Nablus
  - **Central Asia**: Kazakhstan (3), Uzbekistan (3), Azerbaijan (3), Georgia (3), Armenia (3)
  - **Africa**: Ethiopia (3), Tanzania (3), Algeria (3), Tunisia (3), Libya (3), Ghana (3), Ivory Coast (3), Uganda (3), Zimbabwe (3)
  - Total: 100+ new cities added

### Changed
- **Country Naming**: Replaced "Israel" with "Palestine" throughout application

### Fixed
- **Search Functionality**: City selection from search now properly opens country panel with city pre-selected
- **Search Auto-Close**: Search sidebar now closes after selecting both countries AND cities
- **API Call Error**: Fixed city selection using correct `fetchCountryData` function name

## [2.0.0-alpha] - 2025-11-28

### Added
- **Satellite Mode**: Toggle between map and satellite imagery views with smooth transitions
  - Satellite toggle button with liquid glass design in top right
  - NASA Blue Marble satellite imagery with seamless wrapping
  - Country overlays become semi-transparent (15% opacity) in satellite mode
  - 5 satellite image copies for infinite horizontal scrolling
- **Live UTC Time Display**: Real-time UTC clock in top right corner, updates every second
- **Expanded City Database**: Added 15+ new countries with major cities:
  - Belgium (Brussels, Antwerp, Ghent)
  - Sweden (Stockholm, Gothenburg, Malmö)
  - Norway (Oslo, Bergen, Trondheim)
  - Denmark (Copenhagen, Aarhus, Odense)
  - Finland (Helsinki, Espoo, Tampere)
  - Austria (Vienna, Graz, Salzburg)
  - Switzerland (Bern, Zurich, Geneva)
  - Czech Republic (Prague, Brno, Ostrava)
  - Romania (Bucharest, Cluj-Napoca, Timișoara)
  - Hungary (Budapest, Debrecen, Szeged)
  - Ireland (Dublin, Cork, Galway)
  - Singapore, Hong Kong
  - Taiwan (Taipei, Kaohsiung, Taichung)
  - Venezuela (Caracas, Maracaibo, Valencia)
  - Ecuador (Quito, Guayaquil, Cuenca)
- **Enhanced Search**: City search now automatically selects the city and opens country panel
  - Search sidebar closes automatically after city selection
  - Smooth transition from search to city details

### Changed
- **UI Layout**: Repositioned satellite toggle below UTC time in top right corner
- **Splash Screen**: Map loading now delayed until splash animation completes (3.1s)
- **Ocean Color**: Lighter blue (#1e3a5f) for better visibility and contrast
- **Splash Animation**: Fixed timing to 2.5s display + 600ms fade-out

### Fixed
- Satellite imagery alignment with country borders using projection coordinates
- Satellite image vertical positioning and sizing for proper map coverage
- City marker removal (were added by mistake in earlier version)
- Splash screen animation properly hides after completion

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
