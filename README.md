# NYC Hydrant Density Map

A web-based interactive map visualizing fire hydrant density by neighborhood in NYC, powered by MapLibre GL JS and PMTiles.

## Overview
This project displays neighborhood-level fire hydrant density data using vector tiles stored in a single PMTiles archive. It uses MapLibre GL JS for rendering and is designed for efficient, serverless deployment.

## Why PMTiles? (Scalability)
This project uses **PMTiles**, a cloud-native format for vector tiles, offering superior scalability over traditional GeoJSON:

- **Serverless & Cost-effective:** No dynamic tile server required. The map is served entirely as a static file, which can be hosted on any standard CDN or static hosting service with zero compute costs.
- **Efficient Data Streaming:** Using HTTP Range Requests, the browser only fetches the specific data required for the current view. This ensures the map stays performant even with large datasets.
- **No Memory Bottlenecks:** Unlike standard GeoJSON which loads everything into browser memory, PMTiles tiles data, preventing performance degradation even as the dataset grows.

## Project Structure
- `index.html`: The main web application.
- `neighborhood_density.pmtiles`: The vector tile data archive.
- `serve_with_range.py`: A simple Python server to run the map locally with HTTP Range Request support.

## Getting Started

### Local Development
To view the map locally, run the provided Python script:

```bash
python3 serve_with_range.py 8080
```
You can specify a different port if needed:
```bash
python3 serve_with_range.py <port_number>
```
Then, open your browser and navigate to `http://localhost:<port_number>`.

### Deployment
This folder is ready to be deployed to any static web hosting service (e.g., GitHub Pages, Vercel, Netlify). 
- No additional server configuration is required as these platforms support HTTP Range Requests by default.
- Simply upload `index.html` and `neighborhood_density.pmtiles` to your host's root directory.

## Data Source
- Fire hydrant density data is processed from NYC city records.
