🚗 Car Data Analysis & Cleaning Project


📌 Skills Demonstrated
✅ Data Cleaning – Handling missing values (NaN, ?), replacing with mean/mode.
✅ Feature Engineering – Unit conversion (mpg → L/100km), normalization, binning.
✅ Data Preprocessing – One-hot encoding (fuel-type, aspiration).
✅ Exploratory Data Analysis (EDA) – Descriptive stats, histograms, bar plots.
✅ Python Libraries Used – Pandas, NumPy, Matplotlib.

📂 Dataset
Source: Auto Dataset (UCI Machine Learning Repository)
Features:

Numerical: price, horsepower, engine-size, mpg, etc.

Categorical: fuel-type, aspiration, num-of-doors, etc.


🔧 Data Processing Steps
Handled Missing Values

Replaced ? with NaN.

Dropped rows with missing price.

Filled missing numerical values (normalized-losses, bore, stroke) with mean.

Filled missing categorical values (num-of-doors) with mode.

Feature Engineering

Converted highway-mpg → highway-L/100km for better interpretability.

Normalized length, width, height (min-max scaling).

Binned horsepower into categories (Low, Medium, High).

Categorical Data Encoding

One-hot encoded fuel-type (gas/diesel) and aspiration (std/turbo).

Exploratory Analysis

Descriptive statistics (df.describe()).

Visualizations:

Histogram of horsepower distribution.

Bar plot of horsepower bins.

📊 Key Findings
✔ Most Common Car Specs:

Majority have four doors and gas fuel type.

Average horsepower: ~104 HP.

✔ Missing Data Insights:

normalized-losses had X% missing values, filled with mean.

num-of-doors had missing entries, replaced with mode (four).

✔ Feature Relationships:

📂 Project Structure
text
car-data-analysis/  
├── data/  
│   └── auto.csv            # Raw dataset  
├── clean_df.csv            # Processed data  
└── README.md               # Project documentation  

🎯 Goal: This project showcases my ability to clean, analyze, and derive insights from raw data—essential skills for a Data Analyst role.
