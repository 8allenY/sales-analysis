
# House Sales in King County, USA – Price Prediction

This project explores and models house sale prices in King County, USA (including Seattle), using the classic
`kc_house_data_NaN.csv` dataset from the IBM Data Analysis with Python course.

The goals are to:

- Perform basic data cleaning and exploratory data analysis (EDA)
- Build baseline and more advanced regression models to predict house prices
- Compare model performance and interpret the most important features


## 1. Dataset

The notebook uses:

- **File:** `kc_house_data_NaN.csv`
- **Source:** IBM Developer Skills Network – *Data Analysis with Python* final project
- **Direct URL:**

  ```text
  https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DA0101EN-SkillsNetwork/labs/FinalModule_Coursera/data/kc_house_data_NaN.csv
  ```

You have two options:

1. **Recommended:** Let the notebook download the CSV automatically.  
   If `data/kc_house_data_NaN.csv` is missing, the notebook will fetch it from the URL above and save a local copy.

2. **Manual:** Download `kc_house_data_NaN.csv` from the URL and place it in a local `data/` folder at the root
   of the repository.

## 2. Environment and requirements

This project uses:

- Python 3.8+
- pandas
- numpy
- seaborn
- matplotlib
- scikit-learn

Install the dependencies with:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn
```

(Or put them into a `requirements.txt` and run `pip install -r requirements.txt`.)

## 3. What the notebook does

The cleaned notebook `House_Sales_in_King_Count_USA_clean.ipynb` follows these steps:

1. **Setup**
   - Imports all required libraries
   - Configures plotting and suppresses non-critical warnings

2. **Dataset & loading**
   - Defines the official IBM dataset URL
   - Tries to load a local CSV from `data/kc_house_data_NaN.csv`
   - If the local file is missing, downloads the CSV from the URL and saves it under `data/`

3. **Data wrangling**
   - Drops identifier columns (`id`, `Unnamed: 0`)
   - Handles missing values in `bedrooms` and `bathrooms` using mean imputation

4. **Exploratory data analysis**
   - Examines the distribution of `floors`
   - Compares prices for waterfront vs. non-waterfront properties
   - Visualizes the relationship between `sqft_above` and `price`
   - Computes correlations between numerical features and `price`

5. **Model development**
   - Builds a **baseline linear regression** model using `sqft_living`
   - Builds a **multivariate linear regression** model with several predictive features
   - Trains a **polynomial-features pipeline** (scaling + polynomial features + linear regression) and evaluates it with cross-validated R²

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

4. Run the notebook:

   ```bash
   jupyter notebook House_Sales_in_King_Count_USA_clean.ipynb
   ```

   The notebook will:
   - Look for `data/kc_house_data_NaN.csv`
   - If it's not there, download it from the official IBM URL
