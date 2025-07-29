# Amazon Region Educational Accessibility Analysis

This repository contains a comprehensive geospatial analysis of educational accessibility across the Amazon region, focusing on Brazil, Ecuador, Colombia, Peru, and Bolivia. This project was developed as part of deliverable operation RG-T4435 for the Inter-American Development Bank (BID/IDB).

## Project Overview

This analysis provides critical insights into educational accessibility gaps across the Amazon basin, with particular focus on:

- **Geospatial data processing** for population grids and school locations
- **Accessibility gap analysis** using walking distance calculations
- **Special focus on schools without terrestrial access** (riverside/isolated schools)
- **Comparative insights** across Amazonian countries
- **Population-based analysis** by educational level (primary, middle, secondary)

## Key Components

### 1. Geospatial Data Processing Scripts
- Population grid cell processing and standardization across countries
- School location data harmonization from multiple national sources
- Geographic coordinate system alignment (EPSG:4326)
- Administrative boundary integration

### 2. Accessibility Analysis
- **Walking distance calculations** using OpenStreetMap road networks via OSRM routing
- **Travel time computations** for primary, middle, and secondary education levels
- **Accessibility thresholds** and categorization (e.g., "No access", time-based categories)
- **Multi-country analysis** covering the Amazon basin

### 3. Riverside Schools Analysis
- Identification of schools accessible only by waterways
- River proximity analysis using HydroRIVERS dataset
- Population without terrestrial access to educational facilities
- Special attention to indigenous and remote communities

### 4. Key Outputs

#### Data Products
- `gdf_celdas_final_2025_07_29.parquet`: Final analysis results with 35,433 grid cells
- Country-specific accessibility datasets for Brazil, Peru, Colombia, Ecuador, and Bolivia
- Population by school age demographic breakdowns
- Riverside population accessibility summaries (`riverside_pop_school_access_2025_07_29.xlsx`)

#### Analytical Results
- **Population metrics**: School-age population (5-9, 10-14, 15-19 years) by accessibility categories
- **Distance analysis**: Travel times and distances to nearest educational facilities
- **Coverage gaps**: Areas with no terrestrial access to schools
- **Country comparisons**: Cross-national analysis of educational accessibility

## Methodology

### Data Sources
- **Population Data**: WorldPop constrained demographic datasets
- **School Data**: National educational facility databases from each country
- **Geographic Data**: OpenStreetMap for routing, HydroRIVERS for waterways
- **Administrative Boundaries**: Country and sub-national administrative divisions

### Analysis Framework
1. **Grid-based approach**: Standardized 1km x 1km population grid cells
2. **Accessibility calculation**: Walking distance/time using road networks
3. **Multi-level education**: Separate analysis for primary, middle, and secondary schools
4. **Waterway accessibility**: Special consideration for river-dependent access

## Technical Implementation

### Key Technologies
- **Python ecosystem**: GeoPandas, Pandas, UrbanPy for geospatial analysis
- **Routing engine**: OSRM (Open Source Routing Machine) for travel time calculations
- **Visualization**: Matplotlib, Contextily, Folium for mapping
- **Data processing**: Dask for distributed computing, Parquet for efficient storage

### Notebooks Structure
- `00_initial_exploration.ipynb`: Data exploration and preprocessing
- `01_01-03_distance_calculation_*.ipynb`: Travel time/distance calculations by country
- `02-03_population_calculation_*.ipynb`: Demographic analysis and aggregation
- `04_population_*_analysis.ipynb`: Results analysis and visualization
- `05_01_new_schools.ipynb`: School data processing
- `06_01_riverside_schools.ipynb`: Waterway accessibility analysis

## Key Findings

The analysis provides crucial insights for educational policy and infrastructure planning in the Amazon region, identifying:

- Areas with limited or no terrestrial access to educational facilities
- Population concentrations requiring new educational infrastructure
- Disparities in educational accessibility between countries and regions
- Communities dependent on waterway transportation for school access

## Deliverable Compliance

This repository fulfills the requirements for the Amazon Region Analysis Report (16% weight) under operation RG-T4435, providing:

✅ **Geospatial data processing scripts** for educational accessibility analysis  
✅ **Accessibility gap analysis** with quantitative metrics  
✅ **Report on schools without terrestrial access** with population impact  
✅ **Comparative insights** across Brazil, Ecuador, Colombia, Peru, and Bolivia  
✅ **Standalone component** for Amazon region educational accessibility

## Usage

The analysis can be reproduced by running the Jupyter notebooks in sequence. The main dependencies are managed through `pyproject.toml` and can be installed using UV package manager.

```bash
# Install dependencies
uv sync

# Run analysis notebooks in order
# See individual notebooks for specific country/region analysis
```

## Data Outputs

Final results are available in the `outputs/` directory, including:
- Processed geographic datasets (Parquet format)
- Summary statistics (Excel format)
- Visualization outputs (PNG maps and charts)
- Detailed accessibility metrics by geographic cell
