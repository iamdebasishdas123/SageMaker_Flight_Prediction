## Usage
To run the project locally:
1. Clone the repository: `git clone https://github.com/iamdebasishdas123/SageMaker_Flight_Prediction`
2. Install dependencies: `pip install -r requirements.txt`
3. Run the Streamlit app: `streamlit run app.py`
---
# Flight Price Prediction Model using Sagemaker Documentation 

## Introduction
This document provides an overview of the Flight Price Prediction project, including the dataset, project files, model training, and prediction process. The project aims to predict flight prices based on various features such as airline, date of journey, source, destination, departure time, arrival time, duration, total stops, and additional information. The prediction model is built using XGBoost and deployed as a web application using Streamlit.

## Project Structure
```
Flight_Price_Prediction/
├── .gitignore
├── README.md
├── app.py
├── aws-xgboost-model
├── XGB-model
├── preprocessor.joblib
├── requirements.txt
├── data/
│   ├── flight_price.csv
│   ├── test.csv
│   ├── train.csv
│   └── val.csv
|── Preprocess file/
│   ├── test-pre.csv
│   ├── train-pre.csv
│   ├── val-pre.csv
├── notebooks/
│   ├── AWS-Model-training.ipynb
│   ├── Data_Cleaning.ipynb
│   ├── EDA.ipynb
│   ├── Feature_engineering.ipynb
│   ├── local-Model-training.ipynb
│   └── train-pre.csv
├── utils/
│   └── eda_helper_functions.py
└── .git/
```

### Existing Project Files
- **app.py**: The main application file for the Streamlit web app.
- **preprocessor.joblib**: The saved preprocessor object used for transforming the input data.
- **XGB-model**: The trained XGBoost model for price prediction in local computer.
- **aws-xgboost-model**: The XGBoost model trained on AWS Sagemaker.
- **requirements.txt**: The list of dependencies required to run the project.
- **notebooks/**: Contains Jupyter notebooks for data cleaning, exploratory data analysis (EDA), feature engineering, and model training.

## Model Training
The model training process involves several steps, as documented in the Jupyter notebooks:

1. **Data Cleaning** (`Data_Cleaning.ipynb`):
   - Handling missing values
   - Correcting data types
   - Removing duplicates

2. **Exploratory Data Analysis (EDA)** (`EDA.ipynb`):
   - Visualizing the distribution of features
   - Identifying correlations between features and the target variable
   - Detecting outliers

3. **Feature Engineering** (`Feature_engineering.ipynb`):
   - Creating new features from existing ones (e.g., extracting date and time components)
   - Encoding categorical variables
   - Scaling numerical features

4. **Model Training**:
   - **Local Model Training** (`local-Model-training.ipynb`): Training the model on local computer.
   - **AWS Model Training** (`AWS-Model-training.ipynb`): Training the model on AWS Sagemaker for better performance and scalability.

### Preprocessing Pipeline
The preprocessing pipeline is defined using scikit-learn and feature-engine transformers. It includes steps for handling categorical and numerical features, as well as feature selection. The pipeline is saved as `preprocessor.joblib`.

### Training the XGBoost Model
The XGBoost model is trained on the preprocessed data. The trained model is saved as `XGB-model` and `aws-xgboost-model` for local and AWS training respectively.

## Web Application
The web application is built using Streamlit and allows users to input flight details to get a price prediction.


### Prediction
When the user inputs the flight details and clicks the "Predict" button, the app:
1. Loads the saved preprocessor and model.
2. Transforms the input data using the preprocessor.
3. Predicts the flight price using the XGBoost model.
4. Displays the predicted price.

### Example
- **Route**: Delhi to Kolkata
- **Airline**: Air India
- **Actual Price**: 5300 INR
- **Predicted Price**: 5920 INR
- **Flight Details**: Non-stop, duration 2h 35min

## Conclusion
The Flight Price Prediction model provides an accurate and user-friendly way to predict flight prices based on various features. The web application allows for easy interaction and quick predictions, making it a valuable tool for travelers and analysts alike.


