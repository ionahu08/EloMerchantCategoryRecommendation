# **EloMerchant Project**

## **1. Overview**
   - **Project Goal**: Predict loyalty scores for card IDs based on transaction history and merchant data.
   - **Datasets**: Description of `train.csv`, `test.csv`, `Historical_Transactions.csv`, and `New_Merchant_Transactions.csv`.

## **2. Data Preprocessing**
   - **Handling Missing Values**: Explanation of how missing values in target variables were handled.
   - **Outlier Detection & Removal**: Steps taken to detect and remove outliers.
   - **Feature Engineering**: Overview of features created, including datetime transformations, aggregated statistics, and encoded categorical features.

## **3. Feature Engineering Details**
   - **Training and Test Data**:
     - Datetime features: `first_active_month`, `quarter`, `elapsed_time`.
     - Interaction features: `elapsed_time * feature1~3`, `elapsed_time / feature1~3`.
     - One-hot encoding for categorical variables like `card_id`.
     - Aggregated features: mean, sum, min, max, variance for selected features.
   - **Historical Transactions**:
     - Handling missing data and outliers.
     - Label encoding for categorical variables: `authorized_flag`, `category_1`, `category_3`.
     - Datetime-based features: extracting month, day, hour, weekday, weekend from `purchase_date`.
     - Calculation of `price = purchase_amount / num_installments`.
     - Creating holiday and month difference features.
   - **New Transactions**:
     - Similar steps as historical transactions.
   - **Merging Datasets**: Combining features from historical and new transaction data.

## **4. Model Training**
   - **Model Selection**: Use of LightGBM for prediction.
   - **Cross-Validation**: k-fold cross-validation for model evaluation.
   - **Hyperparameter Optimization**: Description of the tuning process and optimal hyperparameters.
   
## **5. Model Evaluation**
   - **Performance Metric**: RMSE as the evaluation metric.
   - **Final Results**: Final model performance with RMSE = **3.62782**.

## **6. References**
   - https://www.kaggle.com/competitions/elo-merchant-category-recommendation/overview
