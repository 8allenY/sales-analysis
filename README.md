
# House Sales in King County, USA – Price Prediction

This project explores and models house sale prices in King County, USA (including Seattle), using the classic
`kc_house_data_NaN.csv` dataset from the IBM Data Science curriculum.

The goal is to:

- Perform basic data cleaning and exploratory data analysis (EDA)
- Build baseline and more advanced regression models to predict house prices
- Compare model performance and interpret the most important features

## Repository structure

```text
.
├── House_Sales_in_King_Count_USA_clean.ipynb   # Clean, runnable analysis notebook
├── data/
│   └── kc_house_data_NaN.csv                   # Dataset (not included here by default)
└── README.md                                   # Project documentation
```

## 1. Dataset

The notebook expects the file:

- `data/kc_house_data_NaN.csv`

You can obtain this dataset from the IBM Skills Network / Coursera project resources for
**"House Sales in King County, USA"**. Save it into a local `data/` folder inside the repository.

## 2. Environment and requirements

This project uses:

- Python 3.8+
- pandas
- numpy
- seaborn
- matplotlib
- scikit-learn

You can install the dependencies with:

```bash
pip install -r requirements.txt
```

or directly:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn
```

## 3. What the notebook does

The cleaned notebook `House_Sales_in_King_Count_USA_clean.ipynb` follows these steps:

1. **Setup**
   - Imports all required libraries
   - Configures plotting and suppresses non-critical warnings

2. **Data loading & inspection**
   - Loads the King County housing dataset from `data/kc_house_data_NaN.csv`
   - Displays structure, types, and summary statistics

3. **Data wrangling**
   - Drops identifier columns (`id`, `Unnamed: 0`)
   - Handles missing values in `bedrooms` and `bathrooms` using mean imputation

4. **Exploratory data analysis**
   - Examines the distribution of `floors`
   - Compares prices for waterfront vs. non‑waterfront properties
   - Visualizes the relationship between `sqft_above` and `price`
   - Computes correlations between numerical features and `price`

5. **Model development**
   - Builds a **baseline linear regression** model using `sqft_living`
   - Builds a **multivariate linear regression** model with several predictive features
   - Trains a **polynomial-features pipeline** (scaling + polynomial features + linear regression) and evaluates it with cross‑validated R²

6. **Model evaluation & refinement**
   - Splits the data into training and test sets
   - Fits a **Ridge regression** model on the original feature space
   - Fits a **Ridge + polynomial features** model and compares R² and RMSE on the test set

7. **Conclusions**
   - Summarizes key drivers of house prices and model performance

## 4. How to run the project locally

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/house-sales-analysis.git
   cd house-sales-analysis
   ```

2. (Optional) Create and activate a virtual environment.

3. Install dependencies:

   ```bash
   pip install pandas numpy seaborn matplotlib scikit-learn
   ```

4. Create a `data/` folder and place `kc_house_data_NaN.csv` inside it.

5. Open the notebook:

   ```bash
   jupyter notebook House_Sales_in_King_Count_USA_clean.ipynb
   ```

6. Run all cells.

## 5. Notes

- This notebook is a cleaned, platform‑independent version of the original IBM project notebook.
- It is designed to be easy to read and suitable for a professional GitHub portfolio (Business · Data · AI focus).
- You can extend it by:
  - Adding feature engineering (e.g., log‑transforming skewed variables)
  - Trying other models (e.g., RandomForestRegressor, GradientBoostingRegressor)
  - Building visual dashboards or reports summarizing the findings.
