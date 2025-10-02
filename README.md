# Elevate-Labs-Internship-Task5_Exploratory_Data_Analysis_-EDA-

# Titanic Dataset Exploratory Data Analysis (EDA)

## Project Overview
This repository contains an Exploratory Data Analysis (EDA) of the Titanic dataset using Python, Pandas, Matplotlib, and Seaborn. The goal is to identify patterns, trends, and anomalies in the dataset to understand factors influencing passenger survival. The analysis includes statistical summaries, handling missing values, and visualizations to uncover relationships between variables like gender, class, age, fare, and embarkation port.

## Files
- **Titanic_EDA.ipynb**: Jupyter Notebook with the complete EDA, including code, visualizations, and observations.
- **Titanic_EDA.pdf**: PDF export of the notebook for easy viewing.
- **train.csv**: The Titanic dataset used for analysis (sourced from [Kaggle](https://www.kaggle.com/c/titanic/data)).
- **README.md**: This file, providing an overview of the project.

## Dataset Description
The Titanic dataset (`train.csv`) contains 891 passenger records with the following columns:
- **PassengerId**: Unique identifier for each passenger.
- **Survived**: Survival status (0 = Did Not Survive, 1 = Survived).
- **Pclass**: Passenger class (1 = 1st, 2 = 2nd, 3 = 3rd).
- **Name**: Passenger name.
- **Sex**: Gender (male, female).
- **Age**: Age in years (177 missing values).
- **SibSp**: Number of siblings/spouses aboard.
- **Parch**: Number of parents/children aboard.
- **Ticket**: Ticket number.
- **Fare**: Ticket fare.
- **Cabin**: Cabin number (687 missing values).
- **Embarked**: Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton; 2 missing values).

## Analysis Steps
1. **Initial Exploration**:
   - Used `.info()`, `.describe()`, and `.isnull().sum()` to understand dataset structure and identify missing values.
   - Calculated value counts for categorical variables (`Survived`, `Sex`, `Pclass`, `Embarked`).

2. **Data Preprocessing**:
   - Filled 177 missing `Age` values with the median (28).
   - Filled 2 missing `Embarked` values with the mode ('S').
   - Dropped `Cabin` due to 77% missing values.
   - Converted `Survived` to string for plotting and back to float for numerical analysis.

3. **Visualizations**:
   - **Countplot**: Survival by `Embarked`, showing Cherbourg passengers had higher survival rates.
   - **Histograms**: `Age` (right-skewed, peak at 28) and `Fare` (highly skewed, outliers >500).
   - **Boxplots**: `Age` by `Pclass` (1st class older) and `Fare` by `Survived` (survivors paid higher fares).
   - **Scatterplot**: `Age` vs `Fare` by `Survived`, showing higher fares linked to survival.
   - **Pairplot**: Relationships between numerical features (`Pclass`, `Fare` show survival patterns).
   - **Heatmap**: Correlation matrix (strong negative correlation between `Pclass` and `Fare`: -0.55).
   - **Barplot**: Survival rate by `Sex` (females ~74%, males ~19%).

4. **Key Insights**:
   - **Gender**: Females had a higher survival rate (74.2%) than males (18.9%), likely due to "women and children first" protocols.
   - **Class**: 1st class (63.0%) > 2nd class (47.3%) > 3rd class (24.2%) in survival rates.
   - **Fare**: Higher fares correlated with survival (correlation: 0.26).
   - **Age**: Most passengers were 20-40 years old; weak survival correlation.
   - **Embarkation**: Cherbourg passengers had better survival, possibly due to more 1st class passengers.
   - **Anomalies**: Zero fares and extreme fares (>500) noted.

5. **Summary**:
   - Gender, class, and fare were key survival predictors. Missing data was handled, and anomalies were identified. This EDA provides insights for predictive modeling.
