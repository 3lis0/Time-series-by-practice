# Rossmann Store Sales Forecasting

A comprehensive time series forecasting project predicting daily sales for Rossmann drugstore chain using multiple modeling approaches including statistical models, machine learning, and ensemble methods.

##  Project Overview

Rossmann operates over 3,000 drug stores across 7 European countries. This project tackles the challenge of predicting daily sales for 1,115 stores in Germany for up to 6 weeks in advance. Accurate sales forecasting enables better staff scheduling, inventory management, and strategic planning.

**Competition**: [Kaggle Rossmann Store Sales](https://www.kaggle.com/c/rossmann-store-sales)
**Evaluation Metric**: Root Mean Square Percentage Error (RMSPE)

##  Dataset Description

### Files
- `train.csv` - Historical sales data with target variable
- `test.csv` - Test data without sales (prediction target)
- `store.csv` - Store metadata and characteristics
- `sample_submission.csv` - Submission format template

### Key Features
- **Sales**: Daily turnover (target variable)
- **Store**: Unique store identifier
- **Date**: Date of sales record
- **Customers**: Number of customers per day
- **Open**: Store operational status (0=closed, 1=open)
- **Promo**: Daily promotion indicator
- **StateHoliday**: State holiday types (a=public, b=Easter, c=Christmas)
- **SchoolHoliday**: School closure indicator
- **StoreType**: Store model categories (a, b, c, d)
- **Assortment**: Product range levels (a=basic, b=extra, c=extended)
- **CompetitionDistance**: Distance to nearest competitor
- **Promo2**: Continuous promotion participation

##  Implementation Pipeline

### 1. Data Analysis & Exploratory Data Analysis (EDA)
- **Sales Trends**: Weekly and monthly seasonality patterns
- **Distribution Analysis**: Sales distribution across stores and time
- **Promotional Impact**: Effect of promotions on sales performance
- **Day-of-Week Patterns**: Weekly sales cycles
- **Store Type Comparison**: Performance variations by store categories
- **Correlation Analysis**: Feature relationship mapping

### 2. Data Preprocessing & Feature Engineering
- **Missing Value Handling**: Imputation strategies for competition and promotion data
- **Time-Based Features**: 
  - Cyclical encoding (sin/cos) for seasonality
  - Calendar features (year, month, day, quarter)
  - Weekend and holiday indicators
- **Lag Features**: Historical sales patterns (7, 14, 30-day lags)
- **Rolling Statistics**: Moving averages and volatility measures
- **Store-Level Statistics**: Aggregated performance metrics
- **Competition Features**: Logarithmic distance transformation
- **Categorical Encoding**: Label encoding for store attributes

### 3. Modeling Approaches

#### Simple Baseline Models
- **Mean Model**: Store-level average sales
- **Last Day Model**: Previous day's sales as prediction
- **Moving Average**: 7-day rolling average

#### Statistical Time Series Models
- **ETS (Error, Trend, Seasonality)**: Exponential smoothing with additive components
- **ARIMA**: Auto-ARIMA with seasonal components (weekly seasonality)
- **Prophet**: Facebook's forecasting tool with multiple seasonality

#### Machine Learning Models
- **XGBoost**: Gradient boosting with comprehensive feature engineering
- **Random Forest**: Ensemble of decision trees (implemented framework)

### 4. Model Evaluation & Selection
- **Validation Strategy**: Time series cross-validation
- **Metric**: Root Mean Square Percentage Error (RMSPE)
- **Performance Comparison**: Systematic evaluation across all models

## 📈 Results Summary

### Model Performance (RMSPE)
| Model | RMSPE Score | Description |
|-------|-------------|-------------|
| Simple Mean | 0.2133 | Store-level average baseline |
| Last Day Sales | 0.1253 | Previous day persistence |
| 7-Day Moving Average | 0.1933 | Short-term trend following |
| ETS | 0.1865 | Statistical seasonality modeling |
| ARIMA | 0.1698 | Autoregressive integrated approach |
| Prophet | 0.1720 | Multi-seasonal forecasting |
| **XGBoost** | **0.0555** | **🏆 Best performing model** |

### Key Insights
- **XGBoost achieved exceptional performance** with RMSPE of 0.0555, significantly outperforming all other models
- **55% improvement** over the best statistical model (Last Day Sales: 0.1253)
- **Classical time series models** (ETS, ARIMA, Prophet) performed similarly in the 0.16-0.17 range
- **Simple baselines** provided reasonable performance, with Last Day Sales being surprisingly effective (0.1253)
- **Feature engineering and ML approach** proved crucial for capturing complex sales patterns
- **Promotional effects** and **store characteristics** are key predictive factors

## 🚀 Usage Instructions

### Prerequisites
```python
# Required libraries
pandas, numpy, matplotlib, seaborn
scikit-learn, xgboost
statsmodels, pmdarima, prophet
```

### Running the Analysis
1. **Data Setup**: Download Rossmann dataset from Kaggle
2. **Environment**: Run in Google Colab or Jupyter notebook
3. **Execution**: Follow the notebook sections sequentially
4. **Kaggle Submission**: Generate predictions for test set

### Key Functions
- `create_time_features()`: Generate temporal features
- `create_lag_features()`: Build historical lookback features  
- `create_rolling_features()`: Calculate moving statistics
- `rmspe()`: Evaluation metric calculation
- `prepare_ml_features()`: Comprehensive feature engineering

## 📁 Project Structure
```
rossmann-store-sales/
├── Rossmann_Store_Sales.ipynb    # Main analysis 
└── README.md                     # This documentation
```

## 🏆 Business Impact

### Value Delivered
- **Improved Forecasting Accuracy**: XGBoost model significantly outperforms simple baselines
- **Staff Optimization**: Better sales predictions enable efficient scheduling
- **Inventory Management**: Accurate demand forecasting reduces waste and stockouts
- **Strategic Planning**: Long-term trend analysis supports business decisions

### Model Insights
- **Promotional Strategy**: Quantified impact of different promotion types
- **Seasonal Planning**: Identified key seasonal patterns for planning cycles  
- **Store Performance**: Highlighted factors driving store-level variations
- **Competition Analysis**: Measured competitive proximity effects

## 🔄 Future Enhancements

### Potential Improvements
- **Deep Learning**: LSTM/GRU for sequential pattern learning
- **External Data**: Weather, economic indicators, local events
- **Ensemble Methods**: Advanced model combination techniques
- **Hyperparameter Optimization**: Systematic parameter tuning
- **Real-time Updates**: Online learning for model adaptation

### Scalability Considerations
- **Multi-store Modeling**: Hierarchical forecasting approaches
- **Cloud Deployment**: Production-ready model serving
- **Monitoring**: Model performance tracking and alerts
- **A/B Testing**: Continuous model improvement validation

##  Technical References

### Libraries Used
- **Data Processing**: pandas, numpy
- **Visualization**: matplotlib, seaborn  
- **Machine Learning**: scikit-learn, xgboost
- **Time Series**: statsmodels, pmdarima, prophet
- **Evaluation**: Custom RMSPE implementation

### Methodological Approach
- Time series cross-validation for temporal data
- Feature engineering with domain knowledge
- Multiple model comparison and selection
- Production-ready prediction pipeline

---
## Contact

- GitHub: [3lis0](https://github.com/3lis0)
- LinkedIn: [ali-salama](https://www.linkedin.com/in/ali-salama/)
- kaggle: [alisalama0](https://www.kaggle.com/alisalama0)