# Brazilian Houses Rent Analysis

This repository contains the analysis and clustering of rental properties in Brazil, focusing on identifying the driving factors behind rent price variations and clustering houses based on their characteristics.

## Overview
The project utilizes the Brazilian Houses dataset, comprising 10,692 observations and 12 variables. The variables include categorical and numerical features representing house characteristics and rent-related information.

The primary objectives of the project are:
- Analyze factors influencing rent prices in Brazil.
- Cluster houses based on their characteristics for better market segmentation.

## Repository Structure
- main.R: R script for data cleaning, exploratory data analysis, and predictive modeling.
- markdown.Rmd: R Markdown file detailing the entire analysis workflow.
- report.pdf: Comprehensive PDF report summarizing the findings, including visualizations and insights.

## Key Features of the Analysis
### Data Pre-Processing
- Duplicates Handling: Removed 363 duplicate rows.
- Missing Values: Addressed the floor feature with 2,369 missing values, inferring that missing values represent properties with zero floors (e.g., houses).
- Encoding: Converted categorical variables (city, animal, furniture) into factors while keeping other variables numeric.

### Exploratory Data Analysis
- Outlier Detection and Removal: Identified and removed outliers (values four standard deviations away from the mean), reducing the dataset by 1.81%.
- Correlation Analysis: Identified significant correlations between rent amount and:
  - Area of the house (strong correlation).
  - Fire insurance costs (very strong correlation, ~0.99).
  - Property tax (moderate correlation).

### Key Findings
- City-wise Rent Distribution:
  - São Paulo has the highest average rent (~R$ 4,640), attributed to its economic significance.
  - Other cities like Rio de Janeiro (~R$ 3,288) and Belo Horizonte (~R$ 3,429) show relatively high rents.
- Effect of Categorical Variables:
  - Animal Acceptance: Houses allowing pets command higher rents (~R$ 3,965) than those that do not (~R$ 3,487).
  - Furniture: Furnished houses have significantly higher rents (~R$ 4,905) than unfurnished ones (~R$ 3,521).

## Predictive Modeling
### Models Implemented
Linear Models:
- Multiple Linear Regression.
- Stepwise Regression (AIC/BIC-based).
Penalized Regression:
- Lasso Regression (Lambda tuning).
Non-linear Models:
- k-Nearest Neighbors (KNN).
- Splines.
- XGBoost.

### Best Performing Model
XGBoost achieved the highest performance:
- R-squared: 0.9955
- RMSE: 215.37

### Feature Importance
Fire insurance cost was the most influential predictor, followed by house area and the number of rooms.

## Clustering Analysis
### Objective
Cluster houses into groups based on shared characteristics to understand rental market segmentation.

### Process
Dimensionality Reduction: Principal Component Analysis (PCA) was applied, selecting the top 3 components for clustering.
Clustering Models:
- K-Means (Optimal k = 2).
- Hierarchical Clustering (Optimal k = 2).

### Results
- Cluster 1: Low-value houses (smaller area, lower rent, mostly unfurnished).
- Cluster 2: High-value houses (larger area, higher rent, mostly furnished).
- Distribution:
  - Cluster 1 has broader geographical spread.
  - Cluster 2 is concentrated in São Paulo (~72%).
