# NYC Hydrant Density Map

A web-based interactive map visualizing fire hydrant density by neighborhood in NYC, powered by MapLibre GL JS and PMTiles.

## Overview
This project displays neighborhood-level fire hydrant density data using vector tiles stored in a single PMTiles archive. It uses MapLibre GL JS for rendering and is designed for efficient, serverless deployment.

## Project Structure
- `index.html`: The main web application.
- `neighborhood_density.pmtiles`: The vector tile data archive.
- `create_pmtiles.sh`: Script to regenerate the PMTiles file from source data.
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
