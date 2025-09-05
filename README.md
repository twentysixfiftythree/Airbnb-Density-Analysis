# Airbnb Density Analysis: NYC vs Toronto

A comprehensive data analysis project comparing Airbnb listing densities, pricing patterns, and seasonal trends between New York City and Toronto using machine learning and geospatial analysis techniques.

##  Research Questions

This project addresses three key research questions:

1. **Density Analysis**: How do Airbnb listing densities differ between New York City and Toronto?
2. **Pricing & Predictive Modeling**: What are the average Airbnb listing prices in NYC versus Toronto, and how do predictive models perform to predict revenue potential?
3. **Seasonality**: How do seasonal patterns affect Airbnb availability and pricing in both cities?

## 🏗️ Project Structure

```
Airbnb-Density-Analysis/
├── Notebooks/
│   ├── Density Analysis.ipynb      # Geospatial density analysis and heatmaps
│   ├── Predictive Models.ipynb     # Machine learning models for price prediction
│   └── Seasonality.ipynb          # Seasonal trend analysis
├── README.md
└── writeup.pdf                    # Detailed project report
```

## 🚀 Getting Started

### Prerequisites

- Python 3.7+
- Jupyter Notebook
- Required Python packages (see Installation section)

### Installation

1. Clone this repository:
```bash
git clone <repository-url>
cd Airbnb-Density-Analysis
```

2. Install required packages:
```bash
pip install pandas numpy matplotlib seaborn folium geopandas shapely mapclassify scikit-learn xgboost category_encoders
```

3. Launch Jupyter Notebook:
```bash
jupyter notebook
```

## 📁 Data Sources

The analysis uses Airbnb listing data from [Inside Airbnb](https://insideairbnb.com/get-the-data):

- **NYC Dataset**: New York City Airbnb listings
- **Toronto Dataset**: Toronto Airbnb listings
- **Geographic Data**: 
  - NYC neighborhoods GeoJSON
  - Toronto neighborhoods GeoJSON

### Data Features

Each dataset contains 18 key features including:
- Geographic coordinates (latitude, longitude)
- Neighborhood information
- Room type and pricing
- Host details and listing metrics
- Availability data (30, 60, 90, 365 days)

## 🔬 Methodology

### 1. Density Analysis (`Density Analysis.ipynb`)

- **Grid-based Analysis**: Divided cities into 1km² grid cells
- **Density Calculation**: Computed listings per square kilometer
- **Geospatial Visualization**: Created interactive heatmaps using Folium
- **Neighborhood Comparison**: Analyzed density patterns by neighborhood

**Key Findings:**
- NYC average density: 28.46 listings/km²
- Toronto average density: 20.59 listings/km²
- Highest density areas: Hell's Kitchen (NYC), Waterfront Communities (Toronto)

### 2. Predictive Modeling (`Predictive Models.ipynb`)

- **Price Analysis**: Compared average listing prices between cities
- **Feature Engineering**: Encoded categorical variables
- **Model Comparison**: 
  - Random Forest Regression
  - XGBoost Regression
- **Performance Metrics**: R² score, RMSE, MAE

**Model Performance:**
- **NYC XGBoost**: R² = 0.495, RMSE = 61.28
- **Toronto XGBoost**: R² = 0.384, RMSE = 59.82
- **NYC Random Forest**: R² = 0.327, MAE = 51.06
- **Toronto Random Forest**: R² = 0.314, MAE = 51.18


While these may seem relatively low, pricing has so many factors that cannot simply be seen with tabular data. There's a certain level of finish that we don't have the access to, which I believe is the lurking variable.

### 3. Seasonality Analysis (`Seasonality.ipynb`)

- **Availability Patterns**: Analyzed booking patterns across different time periods
- **Seasonal Correlation**: Examined relationship between price and availability
- **Visualization**: Created scatter plots and correlation matrices

**Key Insights:**
- Both cities show similar seasonal patterns
- Winter months: ~60% availability
- Christmas period: ~40-50% availability
- Price variations correlate with seasonal demand

## 📈 Key Results

### Pricing Comparison
- **NYC Average Price**: $206.50
- **Toronto Average Price**: $177.04
- **Price Difference**: NYC is ~17% more expensive than Toronto

### Density Insights
- NYC has higher overall density but more concentrated hotspots
- Toronto shows more distributed density patterns
- Both cities have clear high-density tourist areas

### Seasonal Trends
- Minimal seasonal variation in availability patterns
- Christmas period shows slight price increases
- Summer months show counterintuitive availability patterns

## 🛠️ Technical Implementation

### Libraries Used
- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn, folium
- **Geospatial**: geopandas, shapely, mapclassify
- **Machine Learning**: scikit-learn, xgboost, category_encoders

### Data Processing Pipeline
1. Data cleaning and preprocessing
2. Feature engineering and encoding
3. Outlier removal using IQR method
4. Train-test split (80/20)
5. Model training and evaluation

##  Visualizations

The notebooks generate several key visualizations:
- Interactive heatmaps showing listing density
- Bar charts comparing neighborhood densities
- Scatter plots for price vs. availability analysis
- Correlation matrices for feature relationships
- Model performance visualizations

## 🔍 Usage

1. **Run Density Analysis**: Execute `Density Analysis.ipynb` to generate heatmaps and density comparisons
2. **Build Predictive Models**: Run `Predictive Models.ipynb` to train and evaluate ML models
3. **Analyze Seasonality**: Use `Seasonality.ipynb` to explore temporal patterns

## 📝 Notes

- Data was sampled to 10,000 listings per city for computational efficiency
- Outliers were removed using the IQR method
- Geographic projections used EPSG:4326 (WGS84) coordinate system
- All analysis performed in Google Colab environment

## 🤝 Contributing

This is an academic research project. For questions or suggestions, please refer to the detailed writeup in `writeup.pdf`.

## 📄 License

This project uses data from Inside Airbnb, which is available under their terms of use.

---

**Data Source**: [Inside Airbnb](https://insideairbnb.com/get-the-data)
