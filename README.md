**Project Overview**
This repository contains a Python script for cleaning and preprocessing a messy dataset of used car attributes, followed by basic exploratory data analysis (EDA). The goal is to transform raw, inconsistent data into a clean, standardized format suitable for further analysis or machine learning models, such as predicting car prices.
In this project, I demonstrate essential data wrangling skills using Pandas and NumPy, handling common issues like missing values, data type conversions, unit standardization, normalization, binning, and one-hot encoding. This is particularly relevant for real-world data science tasks where datasets are often incomplete or unstructured. By the end, the cleaned data is saved as clean_df.csv, ready for modeling (e.g., regression to predict prices based on features like engine size, horsepower, and fuel efficiency).
This project showcases my ability to:

Efficiently clean and preprocess large datasets.
Apply statistical methods for imputation and transformation.
Visualize data distributions to inform feature engineering.
Prepare data for downstream tasks like predictive modeling.

It's inspired by common Kaggle datasets (e.g., the classic "Automobile" dataset) and can be extended to build a full used car pricing model.
Dataset
The dataset (auto.csv) includes 205 entries with 26 features describing used cars, such as:

Numerical features: wheel-base, length, width, height, curb-weight, engine-size, bore, stroke, compression-ratio, horsepower, peak-rpm, city-mpg, highway-mpg, price.
Categorical features: make, fuel-type, aspiration, num-of-doors, body-style, drive-wheels, engine-location, engine-type, num-of-cylinders, fuel-system.

Challenges in the raw data:

Missing values represented as '?'.
Inconsistent units (e.g., mpg vs. L/100km).
Mixed data types requiring conversion.
No headers in the original CSV.

Source: This is a sample dataset often used in data science tutorials (e.g., from UCI Machine Learning Repository or Kaggle). You can download it here if needed.
Key Steps in the Script
The script (used_car_cleaning.py or Jupyter notebook equivalent) performs the following steps in sequence:
1. Data Loading and Initial Inspection

Load the CSV file using Pandas.
View the first few rows (df.head()) and last 10 rows (df.tail(10)) to understand the structure.
Assign meaningful column headers for clarity.
Replace '?' placeholders with NaN for proper missing value handling.
Drop rows where 'price' is missing, as it's the target variable and essential for analysis.

2. Data Exploration

Check data types (df.dtypes) to identify columns needing conversion (e.g., strings to floats).
Generate summary statistics:

df.describe() for numerical features (mean, std, min/max).
df.describe(include='all') for all features, including categorical (unique values, top/frequency).
Focused descriptions, e.g., on 'length' and 'compression-ratio'.


Use df.info() for a high-level overview of non-null counts and memory usage.

3. Handling Missing Values

Identify missing data with df.isnull() and count per column using a loop with value_counts().
Impute missing values strategically:

Mean imputation for numerical columns: 'normalized-losses', 'bore', 'stroke', 'horsepower', 'peak-rpm'.
Mode imputation for categorical: Replace missing 'num-of-doors' with the most frequent value ('four').


This ensures no data loss where possible, while maintaining dataset integrity.

4. Data Transformation and Standardization

Convert fuel efficiency units for consistency:

Highway MPG to L/100km: df['highway-mpg'] = 235 / df['highway-mpg'] (and rename to 'highway-L/100km').
City MPG to L/100km: df['city-L/100km'] = 235 / df['city-mpg'].


Normalize dimensions (length, width, height) to a [0,1] scale by dividing by their maximum values, aiding in comparisons and model training.
Reset the index after row drops for clean sequencing.

5. Feature Engineering

Convert 'horsepower' to integer after imputation.
Bin 'horsepower' into categories ('Low', 'Medium', 'High') using pd.cut() with 3 equal-width bins.
Visualize bins:

Bar plot: Counts of each bin using Matplotlib.
Histogram: Distribution of horsepower with 3 bins.


One-hot encode categorical variables:

'fuel-type' → Dummy columns: 'fuel-type-diesel', 'fuel-type-gas'.
'aspiration' → Dummy columns: 'aspiration-std', 'aspiration-turbo'.


Drop original categorical columns to avoid multicollinearity.

6. Output

Save the cleaned and transformed DataFrame to clean_df.csv for future use.

These steps reduce the dataset's messiness, making it analysis-ready. For example, after cleaning, you could easily correlate features with 'price' or build a linear regression model.
Technologies Used

Python 3.x
Libraries:

Pandas: Data manipulation and analysis.
NumPy: Numerical computations (e.g., for NaN handling and binning).
Matplotlib: Basic visualizations (bar plots, histograms).


No additional installations needed beyond these core libraries.
