# Used Car Data Preprocessing

This project demonstrates a complete data preprocessing workflow for a used car resale price dataset using Python, Pandas, and Scikit-learn.

## 📌 Project Overview

The dataset contains information about used cars such as brand, year, mileage, engine capacity, power, fuel type, transmission, city, condition, previous owners, accidents, service score, and resale price.

The main goal is to clean and preprocess the dataset so that it can be used effectively for machine learning.

## 🎯 Objectives

* Identify and handle outliers
* Handle missing values
* Encode categorical variables
* Convert ordinal categories into numerical values
* Scale numerical features
* Separate features and target
* Split the dataset into training and testing sets
* Prevent data leakage
* Verify the processed datasets

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Jupyter Notebook / Google Colab

## 📂 Dataset

The dataset contains **320 records and 15 columns**.

Important columns include:

* `Brand`
* `Year`
* `Mileage_Km`
* `Engine_CC`
* `Power_BHP`
* `Fuel_Type`
* `Transmission`
* `City`
* `Seller_Type`
* `Condition`
* `Previous_Owners`
* `Accidents_Reported`
* `Service_Score`
* `Resale_Price_Lakh`

Target variable:

`Resale_Price_Lakh`

## 🔧 Preprocessing Steps

### 1. Train-Test Split

The dataset was divided into:

* Training data: 80% — 256 records
* Testing data: 20% — 64 records

A `random_state` of 42 was used for reproducibility.

### 2. Outlier Handling

The **IQR (Interquartile Range)** method was used to identify extreme values.

The IQR is calculated as:

`IQR = Q3 - Q1`

Values outside:

`Q1 - 1.5 × IQR`

and

`Q3 + 1.5 × IQR`

were clipped to the acceptable range.

### 3. Missing Value Handling

* Numerical missing values were handled using the **median**.
* Categorical missing values were handled using the **most frequent value**.

### 4. Categorical Encoding

Nominal categorical variables were converted into numerical values using **One-Hot Encoding**.

Columns include:

* Brand
* Fuel Type
* Transmission
* City
* Seller Type

Unknown categories in test data are handled safely using:

`handle_unknown="ignore"`

### 5. Ordinal Encoding

The `Condition` column has a natural order:

* Poor → 1
* Fair → 2
* Good → 3
* Excellent → 4

### 6. Feature Scaling

Numerical features were standardized using `StandardScaler`.

This transforms numerical values so that features are on a comparable scale.

### 7. Preventing Data Leakage

The preprocessing transformations were **fitted only on the training data**.

The same fitted transformations were then applied to the test data.

This prevents information from the test dataset from influencing the training process.

## 📊 Final Dataset

The processed training and testing datasets were exported as CSV files.

The `Car_ID` column was retained for record tracking but was excluded from the machine-learning feature set.

## 📁 Files

* `Day12_Used_Car_Data_Preprocessing.ipynb` — Complete preprocessing notebook
* `Day12_Used_Car_Preprocessed_Train.csv` — Processed training dataset
* `Day12_Used_Car_Preprocessed_Test.csv` — Processed testing dataset
* `Day12_Used_Car_Preprocessing_Dataset.csv` — Original dataset

## ▶️ How to Run

1. Download or clone this repository.
2. Open `Day12_Used_Car_Data_Preprocessing.ipynb`.
3. Upload the dataset if using Google Colab.
4. Run the notebook cells from top to bottom.
5. The processed training and testing CSV files will be generated.

## ✅ Conclusion

This project demonstrates the major steps required to prepare real-world used car data for machine learning.

The workflow handles missing values, outliers, categorical encoding, ordinal encoding, feature scaling, train-test splitting, and data leakage prevention.

The resulting datasets are ready to be used for further machine-learning tasks such as predicting used car resale prices.

### Day 12 Assignment – Used Car Data Preprocessing
