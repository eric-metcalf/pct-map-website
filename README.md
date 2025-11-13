# Dori's PCT Adventure

An interactive map visualizing Dori's Pacific Crest Trail (PCT) journey from Mexico to Canada.

🗺️ **[View Live Map](https://YOUR_USERNAME.github.io/pct-map-website/)**

## About

This website displays:
- 🥾 The complete Pacific Crest Trail route (2,650 miles)
- 📍 Daily camping locations with GPS coordinates
- 🏔️ Major landmarks along the trail
- 📅 Day-by-day progress with messages

## Features

- **Interactive Map**: Pan, zoom, and explore the entire PCT
- **Daily Markers**: Click on green markers to see camping locations and daily updates
- **Trail Route**: Full GPX-based trail data with 112,946+ track points
- **Topographic View**: Terrain-focused map style perfect for hiking visualization

## Technology

- **Leaflet.js** - Interactive mapping library
- **Stadia Maps** - Outdoor-focused map tiles
- **GPX Data** - Accurate PCT trail coordinates
- **Garmin inReach** - Daily location data from satellite messages

## Local Development

To run locally:

```bash
# Option 1: Simple file open
open index.html

# Option 2: Local web server (recommended)
python3 -m http.server 8000
# Then visit: http://localhost:8000
```

## Data Updates

The map data is generated from Garmin inReach satellite messages. To update:

1. Process new message data using the companion Scala project
2. Copy the generated files to this repository:
   - `daily_locations.json` - Daily camping locations
   - `pct_trail.json` - PCT trail route (only needs updating if trail data changes)
3. Commit and push to update the live site

## Files

- `index.html` - Main web application
- `pct_trail.json` - Complete PCT trail coordinates (112,946 points)
- `daily_locations.json` - Daily camping locations with messages

## Credits

- Trail data from [dcarr.com PCT GPX files](https://www.dcarr.com/2025-pct-gpx)
- Map tiles from [Stadia Maps](https://stadiamaps.com/)
- Built with ❤️ to track an amazing PCT adventure

## License

This project is for personal use. Map data and tiles are subject to their respective licenses.

