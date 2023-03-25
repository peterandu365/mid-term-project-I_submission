
# Flight Delay Prediction Machine Learning Project

This repository contains code, data, and results for a flight delay prediction machine learning project. The project aims to predict flight delays based on various factors such as airport, carrier, week of the year, and weekday.

## Project Overview

1. **Set up PostgreSQL link for SQL query:** The flight data is stored in a PostgreSQL database. We set up a connection to the database to query the data and download it for further processing.

2. **Download data and save as Parquet:** To accelerate data access, we downloaded the data from the PostgreSQL database and saved it locally as Parquet files.

3. **Exploratory Data Analysis (EDA) using Tableau Desktop:** We used Tableau Desktop to directly access the data from the PostgreSQL database and created various visualizations to explore the data. Tableau Desktop also allowed us to save the visualizations as local `.hyper` files.

4. **Geocoding airport names using Google Maps API:** To obtain the latitude and longitude information for each airport, we used the Google Maps Geocoding API.

5. **Retrieve weather data using OpenWeatherMap API:** We used the OpenWeatherMap API to retrieve weather data for a sample of 1000 entries, using the latitude and longitude information obtained from the geocoding step.

6. **EDA to determine the relationship between weather and flight delay:** We analyzed the relationship between weather and flight delay and concluded that the hypothesis of no relationship between weather and flight delay could not be rejected. As a result, we decided not to include weather information in the modeling process.

7. **Feature Engineering:** We used the observations from the EDA to create engineered features that can be mapped to both the training and test data. Some of the engineered features include airport, carrier, week of the year, and weekday.

8. **Modeling:** We trained and evaluated several machine learning models, including:

    - Decision Trees
    - Random Forest
    - Support Vector Machines (SVM)
    - XGBoost

9. **Model Evaluation:** We used various metrics, such as accuracy, confusion matrix, and classification report for binary variables (e.g., 'cancelled') and R^2 scores and Mean Squared Error (MSE) for numerical variables (e.g., 'carrier_delay', 'weather_delay', 'nas_delay', 'security_delay', 'late_aircraft_delay') to evaluate the performance of the models.

## Results

We found that the XGBoost model provided the best performance among the tested models. The model accurately predicted flight delays with a high degree of precision and recall, and the numerical variables were also well-predicted.

## Instructions for Reproducing Results

1. Clone the repository to your local machine.
2. Install the required Python libraries and set up the necessary API keys for Google Maps and OpenWeatherMap.
3. Run the code in the provided notebooks and scripts in the following order:

    - Set up PostgreSQL link and download data
    - Geocode airport names
    - Retrieve weather data
    - EDA
    - Feature Engineering
    - Modeling (Decision Trees, Random Forest, SVM, and XGBoost)
    - Model Evaluation

4. The trained models, metrics, and predictions will be saved to the local files with their respective prefixes.

Please refer to the individual notebooks and scripts for more detailed instructions and explanations.

