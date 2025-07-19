# NYC Yellow Taxi Fare Prediction using BigQuery ML

This project demonstrates how to use **Google BigQuery** and **BigQuery ML** to explore, prepare, model, and predict taxi fare amounts from the **New York City Yellow Taxi Trips** public dataset. The process involves data exploration, feature engineering, model training, evaluation, and prediction.

## 🗂 Project Structure

The SQL file includes the following key tasks:

### 1. **Dataset Exploration**
- Query trip counts per month for 2015.
- Calculate average taxi trip speeds across different hours.

### 2. **Data Preparation**
- Extract relevant features (pickup/dropoff coordinates, time, day, passenger count).
- Create training and evaluation splits using fingerprint-based partitioning.

### 3. **Model Training**
- Train a **Linear Regression model** using `CREATE MODEL` in BigQuery ML to predict total fare (`fare_amount + tolls_amount`).

### 4. **Model Evaluation**
- Evaluate the model using Root Mean Square Error (RMSE) via `ML.EVALUATE`.

### 5. **Prediction**
- Use the trained model with `ML.PREDICT` to predict fares for evaluation data.

### 6. **Feature Engineering (Model Improvement)**
- Limit dataset to realistic ranges for fare and geolocation.
- Engineer features such as:
  - Euclidean distance between pickup and dropoff points.
  - Separate longitude and latitude distances.

### 7. **Retraining and Evaluation**
- Retrain the model (`taxifare_model_2`) with improved features.
- Re-evaluate using RMSE to verify performance improvements.

## 📊 Dataset

- **Source:** `bigquery-public-data.new_york.tlc_yellow_trips_2015` and `nyc-tlc.yellow.trips`
- **Fields Used:** `pickup_datetime`, `dropoff_datetime`, `fare_amount`, `tolls_amount`, `passenger_count`, GPS coordinates

## 📌 Technologies

- Google BigQuery
- BigQuery ML (Linear Regression)
- SQL (Standard SQL dialect)

## 📈 Model Goals

- **Prediction Task:** Estimate the total fare amount based on trip characteristics.
- **Evaluation Metric:** RMSE (Root Mean Squared Error)

## 📎 How to Use

1. Open the Google Cloud Console.
2. Navigate to BigQuery.
3. Open a new SQL workspace and paste the queries from the `.sql` file.
4. Run section by section to understand and execute tasks.

## 🧠 Learning Outcomes

- Efficient querying of large public datasets using BigQuery.
- Data transformation and partitioning for ML training and testing.
- Building and improving ML models directly in SQL using BigQuery ML.
- Evaluating and interpreting regression model results.

## 📁 File

- `project_4_big_query_taxi_fare.sql`: Complete SQL script for all tasks from data exploration to model evaluation.

---