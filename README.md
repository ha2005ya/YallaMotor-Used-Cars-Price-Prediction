# YallaMotor Used Cars Price Prediction

A Web Scraping and Machine Learning project that collects used-car data from YallaMotor pages and builds a Linear Regression model to predict used-car prices in the UAE.

## Project Overview

The project is divided into two main notebooks:

- `Step1_220230264.ipynb` — extracts used-car information from saved YallaMotor HTML pages and creates the raw dataset.
- `Step2_220230264.ipynb` — preprocesses the dataset, encodes categorical features, trains a Linear Regression model, evaluates it, and saves the cleaned dataset.

## Dataset

The final dataset contains **216 car records** and the following fields:

- `Title`
- `Brand`
- `Model`
- `Year`
- `KM`
- `Location`
- `Price`

The scraped cars include six brands:

- BMW
- Toyota
- Mercedes
- Nissan
- Hyundai
- Ford

## Web Scraping

The scraping notebook uses:

- `BeautifulSoup`
- `glob`
- `pandas`

The saved YallaMotor HTML pages are parsed to extract the car title, brand, model, year, mileage, location, and price.

## Data Preprocessing

The preprocessing stage includes:

- Checking missing values
- Standardizing brand names
- Removing Arabic text and commas from `KM` and `Price`
- Converting `KM` and `Price` to numeric data types
- Selecting features for the regression model
- Encoding categorical variables using `OneHotEncoder`

## Machine Learning Model

The model uses:

- **Algorithm:** Linear Regression
- **Features:** Brand, Model, Year, KM, Location
- **Target:** Price
- **Train/Test Split:** 80% / 20%
- **Categorical Encoding:** OneHotEncoder
- **Pipeline:** Scikit-learn Pipeline + ColumnTransformer

## Model Results

The model achieved approximately:

- **MAE:** 12,264.92 AED
- **MSE:** 452,141,209.05
- **RMSE:** 21,263.61 AED
- **R² Score:** 0.917

The R² score indicates that the model explains about **91.7%** of the variation in used-car prices in this dataset.

## Project Structure

```text
YallaMotor-Used-Cars-Price-Prediction/
│
├── Step1_220230264.ipynb
├── Step2_220230264.ipynb
├── yallamotor_used_cars_raw.csv
├── yallamotor_used_cars_cleaned.csv
└── README.md
```

If you want the first notebook to be fully reproducible, also include the saved `.html` pages used by the scraping notebook.

## How to Run

1. Install the required packages:

```bash
pip install -r requirements.txt
```

2. Place the saved YallaMotor HTML pages in the same folder as `Step1_220230264.ipynb`.

3. Run `Step1_220230264.ipynb` to generate:

```text
yallamotor_used_cars_raw.csv
```

4. Run `Step2_220230264.ipynb` to preprocess the data, train the model, evaluate it, and generate:

```text
yallamotor_used_cars_cleaned.csv
```

## Technologies

- Python
- BeautifulSoup
- Pandas
- NumPy
- Scikit-learn
- Jupyter Notebook

## Conclusion

The project successfully collected 216 used-car records from YallaMotor pages, cleaned and prepared the data, and trained a Linear Regression model. The final model achieved an R² score of approximately 0.917, showing strong predictive performance on this dataset.
