# Country Data Clustering Analysis

![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-v1.3.0-orange.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📊 Project Overview

This project performs unsupervised learning analysis on country data to classify countries into different development clusters based on various socio-economic indicators. Using K-Means clustering with PCA dimensionality reduction, we identify three distinct country groups that represent different levels of economic development and health outcomes.

## 🎯 Key Findings

The analysis successfully identified **3 distinct country clusters**:

| Cluster | Description | Key Characteristics |
|---------|-------------|-------------------|
| **Class 0** | High Income & Low Child Mortality | Developed countries with strong economies, advanced healthcare, low child mortality (≈5.1/1000), high income (≈48,500), and low fertility rates (≈1.81) |
| **Class 1** | Low Income & High Child Mortality | Underdeveloped countries with poor health outcomes, high child mortality (≈78.2/1000), low income (≈5,332), and high fertility rates (≈4.42) |
| **Class 2** | Medium Income & Moderate Child Mortality | Developing countries in transition, moderate child mortality (≈20.3/1000), moderate income (≈13,670), and moderate fertility rates (≈2.25) |

## 📈 Model Performance

- **Silhouette Score**: 0.403 (Good cluster separation)
- **Optimal Clusters**: 3 (determined using Elbow Method)
- **Dimensionality Reduction**: PCA with 2 components
- **Scaling Method**: RobustScaler (robust to outliers)

## 🛠️ Technical Stack

- **Python 3.8+**
- **Data Processing**: pandas, numpy
- **Machine Learning**: scikit-learn
- **Visualization**: matplotlib, seaborn, plotly
- **Model Selection**: yellowbrick
- **Statistical Analysis**: scipy

## 📁 Project Structure

```
Country-Data-Clustering/
├── result.ipynb              # Main analysis notebook
├── Country-data.csv          # Dataset
├── data-dictionary.csv       # Data description
├── requirements.txt          # Dependencies
└── README.md                # This file
```

## 📊 Dataset Description

The dataset contains **167 countries** with the following features:

| Feature | Description | Type |
|---------|-------------|------|
| `country` | Country name | Categorical |
| `child_mort` | Child mortality rate (per 1000 live births) | Numerical |
| `exports` | Exports as % of GDP | Numerical |
| `health` | Health spending as % of GDP | Numerical |
| `imports` | Imports as % of GDP | Numerical |
| `income` | Net income per person | Numerical |
| `inflation` | Inflation rate | Numerical |
| `life_expec` | Life expectancy at birth | Numerical |
| `total_fer` | Total fertility rate | Numerical |
| `gdpp` | GDP per capita | Numerical |

## 🔍 Methodology

### 1. Data Preprocessing
- **Missing Values**: No missing values detected
- **Outlier Detection**: Z-score method (threshold = 3)
- **Encoding**: Label encoding for country names
- **Scaling**: RobustScaler for outlier robustness

### 2. Dimensionality Reduction
- **PCA**: Reduced to 2 components for visualization
- **Explained Variance**: Captures significant variance in the data

### 3. Clustering
- **Algorithm**: K-Means clustering
- **Optimal K**: Determined using Elbow Method
- **Validation**: Silhouette analysis for cluster quality

### 4. Visualization
- **PCA Scatter Plot**: 2D visualization of clusters
- **Feature Analysis**: Income vs Child Mortality scatter plot
- **Cluster Profiling**: Statistical summary of each cluster

## 📈 Results & Insights

### Cluster Analysis Summary

#### 🏆 Class 0: High-Income Developed Countries
- **Countries**: Australia, Austria, Belgium, Canada, Denmark, Finland, France, Germany, Japan, Netherlands, Norway, Singapore, Sweden, Switzerland, United States, etc.
- **Characteristics**:
  - Very low child mortality (≈5.1 per 1,000)
  - High income (≈48,500) and GDP per capita (≈45,900)
  - Highest health spending (≈8.78% of GDP)
  - Long life expectancy (≈80.4 years)
  - Low fertility rate (≈1.81 children per woman)

#### 🌍 Class 2: Medium-Income Developing Countries
- **Countries**: Brazil, China, Colombia, India, Indonesia, Malaysia, Mexico, Philippines, Russia, South Africa, Thailand, Turkey, etc.
- **Characteristics**:
  - Moderate child mortality (≈20.3 per 1,000)
  - Moderate income (≈13,670) and GDP per capita (≈7,872)
  - Moderate health spending (≈6.88%)
  - Life expectancy ≈72.8 years
  - Moderate fertility rate (≈2.25 children per woman)

#### 🌱 Class 1: Low-Income Underdeveloped Countries
- **Countries**: Afghanistan, Bangladesh, Ethiopia, Haiti, Kenya, Nigeria, Pakistan, Sudan, Uganda, Yemen, etc.
- **Characteristics**:
  - Very high child mortality (≈78.2 per 1,000)
  - Low income (≈5,332) and GDP per capita (≈2,413)
  - Lowest health spending (≈5.71%)
  - Short life expectancy (≈62.7 years)
  - High fertility rate (≈4.42 children per woman)

## 🎯 Business Applications

This clustering analysis can be used for:

- **Policy Making**: Identify countries needing development assistance
- **Investment Decisions**: Target markets based on development stage
- **Resource Allocation**: Prioritize aid and development programs
- **Economic Research**: Study development patterns and transitions
- **Healthcare Planning**: Focus on countries with high child mortality

## 🔧 Customization

### Modifying Clustering Parameters

You can adjust the clustering parameters in the notebook:

```python
# Change number of clusters
MODEL = KMeans(n_clusters=4, max_iter=500, random_state=10)

# Use different scaling method
from sklearn.preprocessing import StandardScaler
SCALER = StandardScaler()

# Adjust PCA components
PCA_MODEL = PCA(n_components=3)
```

### Adding New Features

To include additional country indicators:

1. Add new columns to your dataset
2. Update the feature selection in the preprocessing step
3. Re-run the clustering analysis

## 📊 Visualization Examples

The analysis includes several visualizations:

- **PCA Scatter Plot**: Shows cluster separation in 2D space
- **Income vs Child Mortality**: Reveals the strong negative correlation
- **Cluster Profiling**: Statistical summaries for each group

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Reynaldi**
- GitHub: [@GregReynaldi](https://github.com/GregReynaldi)

## 🙏 Acknowledgments

- Dataset source: [Country Data](Country-data.csv)
- Scikit-learn documentation for clustering algorithms
- Yellowbrick for model selection visualization

## 📞 Contact

If you have any questions or suggestions, please feel free to reach out:

- Email: your.email@example.com
- GitHub Issues: [Create an issue](https://github.com/GregReynaldi/country-data-clustering-simple/issues)

---

⭐ **Star this repository if you found it helpful!**
