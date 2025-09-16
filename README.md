# GeoPredictive Analysis of Global Meteorite Impacts: A Machine Learning Approach to Classification and Spatiotemporal Pattern Recognition
# Meteorite Landings Analysis

A comprehensive data science project analyzing global meteorite landing patterns using Python, with a focus on geographical distribution, temporal trends, and predictive modeling.

## Authors
- Dan Beecher (beecher.d@northeastern.edu)
- Rayd Hussain (hussain.r@northeastern.edu)

## Project Overview

This project analyzes NASA's Meteorite Landings dataset to investigate the distribution patterns of meteorite impacts across Earth's surface. We explore geographical features, temporal trends, and attempt to predict meteorite classifications using machine learning techniques.

### Key Questions Addressed
- Where do meteorites most frequently land on Earth?
- Are there geographical biases in meteorite recovery?
- Can we predict meteorite class based on mass and location?
- How have meteorite landing patterns changed over time?

## Dataset

**Source**: [Meteorite Landings from Data.gov](https://catalog.data.gov/dataset/meteorite-landings)
- **Records**: 45,716 meteorite landings
- **Time Period**: 9th century to April 2025
- **Maintained by**: NASA and The Meteoritical Society

### Data Fields
- `name`: Meteorite name
- `id`: Unique identifier
- `nametype`: Name type classification
- `recclass`: Meteorite classification
- `mass (g)`: Mass in grams
- `fall`: Fall or find designation
- `year`: Year of landing/discovery
- `reclat`: Latitude of landing
- `reclong`: Longitude of landing
- `GeoLocation`: Geographic location string

## Installation

### Prerequisites
- Python 3.7+
- pip package manager

### Required Libraries
```bash
pip install numpy matplotlib pandas geopandas shapely basemap scikit-learn
```

### Basemap Installation Note
Basemap can be tricky to install. If you encounter issues:
```bash
# For conda users:
conda install -c conda-forge basemap

# For pip users (may require additional dependencies):
pip install basemap-matplotlib
```

## Project Structure

```
meteorite-landings-analysis/
│
├── geopanduse.py          # Main analysis script
├── project.py             # Initial exploration script
├── meteorite_land.csv     # Dataset
├── README.md              # This file
│
├── outputs/               # Generated visualizations
│   ├── all_meteors.png
│   ├── us_meteors.png
│   ├── knn_accuracy.png
│   └── us_meteors_by_century.png
│
└── DS2500_Final_Project_Report.pdf  # Full analysis report
```

## Usage

### Running the Analysis
```bash
python geopanduse.py
```

This will generate four visualizations:
1. **Global meteorite landings map** - Shows all recorded meteorite impacts worldwide
2. **US-focused meteorite map** - Detailed view of landings in and around the continental US
3. **KNN accuracy plot** - Model performance across different k values
4. **Time-based US map** - Meteorite landings by century with color coding

### Running Initial Exploration
```bash
python project.py
```

This provides a basic visualization of the global meteorite data.

## Key Features

### 1. Data Processing
- Mass normalization for consistent visualization scaling
- Geospatial data conversion using GeoPandas
- Temporal filtering by century

### 2. Visualizations
- **Global Distribution**: World map with meteorite locations sized by mass
- **Regional Analysis**: Focused view of US meteorite landings
- **Temporal Patterns**: Century-based color coding to show historical trends
- **Model Performance**: KNN accuracy visualization across k values

### 3. Machine Learning
- K-Nearest Neighbors (KNN) classification
- Features: mass, latitude, longitude
- Target: meteorite class (recclass)
- Model evaluation across k values (1-50)

## Key Findings

1. **Geographic Bias**: Disproportionate number of meteorites recorded in the United States, likely due to data collection bias
2. **Regional Concentrations**: High density of landings in the US Midwest (100-110°W longitude)
3. **Classification Challenge**: Low prediction accuracy (10-18%) due to:
   - Over 100 different meteorite classes
   - Limited feature set (only mass and location)
4. **Temporal Patterns**: 
   - Pre-1800s: Very few recorded (Northern Mexico)
   - 1800s: Concentrated east of Mississippi River
   - 1900s: Midwest concentration
   - 2000s: Southwest US (Nevada, California, Arizona)

## Limitations & Considerations

### Data Biases
- **Collection Bias**: More meteorites recorded in populated areas
- **Preservation Bias**: Better preservation in dry climates
- **Reporting Bias**: US-centric data due to source (data.gov)

### Model Limitations
- Limited features available for classification
- High number of classes (100+) with imbalanced distribution
- Geographic coordinates may not be predictive of meteorite type

## Future Work

1. **Enhanced Features**:
   - Integrate velocity data
   - Include atmospheric entry angle
   - Add compositional analysis

2. **Advanced Modeling**:
   - Deep learning approaches
   - Ensemble methods
   - Feature engineering

3. **Extended Analysis**:
   - Satellite imagery integration
   - Climate correlation studies
   - Real-time monitoring system development

## Dependencies

- `numpy`: Numerical computing
- `matplotlib`: Plotting and visualization
- `pandas`: Data manipulation
- `geopandas`: Geospatial data handling
- `shapely`: Geometric operations
- `basemap`: Map projections
- `scikit-learn`: Machine learning algorithms

## License

This project uses publicly available data from NASA and The Meteoritical Society. Please refer to the original data source for licensing information.

## Acknowledgments

- NASA for maintaining the meteorite database
- The Meteoritical Society for data collection and curation
- Data.gov for providing public access to the dataset

## Contact

For questions or collaboration opportunities, please contact the authors at the provided email addresses.
