# 2025_ia651_puthenveettil

Code for 2025 IA651 Final Project.
#### Created by : Prasannan Ashwin Puthenveettil

# Project Title: Predicting Electric Vehicle MSRP(Manufacturer's Suggested Retail Price) and Range Using Machine Learning

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Features](#features)
- [Data Preprocessing](#data-preprocessing)
- [EDA & Visualizations](#eda--visualizations)
- [Modeling](#modeling)
- [Results](#results)
- [Overfitting & Underfitting](#overfitting--underfitting)
- [Production Considerations](#production-considerations)
- [Future Improvements](#future-improvements)
- [Acknowledgment](#acknowledgment)


## Project Overview
This project explores electric vehicle adoption patterns using the Washington State Department of Licensing’s Electric Vehicle Population dataset. The goal is to develop two predictive models:

### 1: Predicting `BaseMSRP`
- Predict the **Base Manufacturer's Suggested Retail Price** of an electric vehicle.
- Useful for consumers, dealerships, and pricing analytics.

### 2: Predicting `Electric Range`
- Predict the **Electric Range** (in miles) of the vehicle on a full charge.
- Useful for consumers comparing EV performance and for manufacturers benchmarking efficiency.

##  Dataset

The project uses the [Washington State DOL Open Data](https://catalog.data.gov/dataset/electric-vehicle-population-data), containing real-world data on electric vehicles (EVs), including specifications like make, model, electric range, base MSRP, and classification attributes.
- **File**: `Electric_Vehicle_Population_Data.csv`

## Features

| Feature Name | Description |
|--------------|-------------|
| Model Year | Year of manufacture |
| Make | Manufacturer (e.g., TESLA) |
| Model | Specific vehicle model (e.g., MODEL S) |
| Electric Vehicle Type | BEV or PHEV |
| CAFV Eligibility | Clean fuel eligibility status |
| Electric Utility | Utility company serving EV |
| Base MSRP | Manufacturer Suggested Retail Price (target 1) |
| Electric Range | Range per charge (target 2) |

  
This dataset is useful for understanding factors affecting EV pricing and range, which has implications in sustainability, EV adoption strategies, and cost prediction models.

## Data Preprocessing
- Removed irrelevant columns (e.g., `VIN`, `DOL Vehicle ID`)
- Replaced 0s in `Base MSRP` and `Electric Range` with NaNs
- Handled missing values using `.dropna()`
- Applied **OneHotEncoding** for categorical variables
- Applied **StandardScaler** to numerical columns
- Created a **ColumnTransformer** for combined preprocessing

##  Exploratory Data Analysis (EDA)

### Prediction Task
- **Type**: Regression
- **X variables**: Multiple numerical and categorical fields like `Electric Range`, `Vehicle Class`, `Electric Utility`, etc.
- **Y variables**: Two separate targets:
  - `BaseMSRP`
  - `Electric Range`

###  Observations
- Dataset size: ~1300+ entries
- Several categorical fields needed encoding
- Feature-target relationships showed **moderate to strong correlation** for select features

###  Visualizations

#### Average MSRP by Top 10 Makes
![](output_images/output.png)

#### Distribution of Base MSRP by Electric Vehicle Type
![](output_images/output2.png)

#### Electric Range by Model Year
![](output_images/output3.png)

#### Top 10 Most Common EV Models
![](output_images/output4.png)

#### Correlation Matrix
![](output_images/output5.png)

## Modeling
Tested several models on both targets:

- **Linear Regression**
- **Ridge Regression**
- **Lasso Regression**
- **Decision Tree**
- **Random Forest**
- **Gradient Boosting**
- **Support Vector Regressor (SVR)**

Iteratively refined models by:
- Removing irrelevant or ID fields
- Handling categorical columns using One-Hot Encoding
- Trying various regressors and hyperparameter settings via `GridSearchCV`

## Results