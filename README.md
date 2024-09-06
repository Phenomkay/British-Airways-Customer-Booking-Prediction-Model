# British Airways Customer Booking Prediction Model

## Overview
This project focuses on developing a machine learning model to predict customer bookings for British Airways. The model employs a Random Forest Classifier, following a series of steps from data preprocessing to evaluation, with high accuracy in predicting booking outcomes.

## Objective
The primary goal is to predict whether a customer will book a flight based on key features, providing British Airways with insights that can help optimize marketing efforts and improve resource allocation.

## Problem Statement
British Airways faces the challenge of efficiently predicting customer bookings to better allocate resources and offer personalized experiences. An accurate booking prediction system can optimize customer service and marketing strategies.

## Challenge
The dataset included both categorical and numerical features that required significant preprocessing, feature engineering, and careful handling to ensure optimal performance. Additionally, the target variable was imbalanced, necessitating the use of resampling techniques.

## Solution
A Random Forest Classifier was used to build the predictive model. The steps involved data preprocessing, feature engineering, model training, evaluation, and validation through Stratified K-Fold Cross-Validation. The final model achieved high accuracy and other performance metrics, demonstrating its reliability.

---

### Loading the Data
The dataset was loaded using `encoding="ISO-8859-1"` to handle special characters without issues.

### Exploratory Data Analysis (EDA)
The analysis revealed no missing values. However, categorical columns were identified, requiring further preprocessing steps like encoding for proper model training.

### Data Preprocessing
1. **Encoding Categorical Data**: Label encoding was applied to convert categorical variables to numerical formats, with `flight_day` reserved for feature engineering.
2. **Standardizing Numerical Features**: To normalize the data, numerical features were standardized, ensuring consistent scale across the dataset.

### Feature Engineering
Several new features were created:
- A sum of service requests to capture overall service needs.
- A binary feature indicating if the flight is on a weekend.
- A feature representing the ratio between purchase lead time and length of stay, providing insights into customer behavior patterns.

Afterward, the `flight_day` feature was encoded for use in the model.

### Separating Feature and Target Variables
The dataset was split into feature variables and the target variable (whether a booking was made), preparing the data for model training.

### Balancing the Target Variables
To address class imbalance, SMOTE (Synthetic Minority Over-sampling Technique) was employed, ensuring an equal representation of both classes in the training data.

### Train-Test Split
The dataset was divided into training and testing sets to evaluate the model's performance on unseen data.

### Model Training
A Random Forest Classifier was trained on the preprocessed dataset, leveraging the power of decision trees to create a highly accurate model.

### Model Evaluation
The model achieved **90% accuracy**, and the classification report showed balanced performance between both classes:

- **Precision**: Class 0: 89%, Class 1: 91%
- **Recall**: Class 0: 91%, Class 1: 89%
- **F1-Score**: Class 0: 90%, Class 1: 90%

### Confusion Matrix

[c_matrix.png
](https://github.com/Phenomkay/British-Airways-Customer-Booking-Prediction-Model/blob/227875dfb78ea7f9d136dbe7a9932374f6267154/c_matrix.png)
The confusion matrix was visualized using a heatmap, providing insights into the true positive, true negative, false positive, and false negative rates.

### Cross-Validation
Stratified K-Fold Cross-Validation was used to ensure the model's performance was consistent across different subsets of the data. The mean cross-validation score was **0.8975**, further confirming the robustness of the model.

### Feature Importance

[feature importance.png](https://github.com/Phenomkay/British-Airways-Customer-Booking-Prediction-Model/blob/227875dfb78ea7f9d136dbe7a9932374f6267154/feature%20importance.png)

A feature importance analysis was conducted to visualize how each feature contributed to the model’s predictions. Key features like purchase lead time and the ratio of purchase lead to length of stay played significant roles.

### ROC Curve and AUC Score

[ROC curve.png](https://github.com/Phenomkay/British-Airways-Customer-Booking-Prediction-Model/blob/227875dfb78ea7f9d136dbe7a9932374f6267154/ROC%20curve.png)

The ROC curve was plotted, and the model’s AUC score was calculated to be **96%**, indicating a strong ability to distinguish between the classes.

---

## General Insights & Conclusion

The insights from this metrics tell a lot about the effectiveness and reliability of your model. Here's a breakdown of what they signify:

1. **High Accuracy (90%)**: This shows that the model correctly predicts customer bookings 90% of the time, which is quite impressive. It indicates that the model is well-trained and able to handle the complexity of the data effectively.

2. **Balanced Precision and Recall**: The precision (89%-91%) and recall (89%-91%) for both classes (bookings vs. non-bookings) suggest that the model isn't biased toward one class over the other.  
   - **Precision** measures how often the model is correct when it predicts a booking (or non-booking). High precision means fewer false positives, i.e., it's not mistakenly predicting bookings.
   - **Recall** measures how well the model catches all the actual bookings. High recall means fewer false negatives, i.e., it’s not missing too many bookings that actually occur.

3. **Balanced F1-Scores**: The F1-score (90% for both classes) is the harmonic mean of precision and recall. A high F1-score indicates that the model maintains a strong balance between precision and recall. This is crucial because it means the model performs well even in cases where one class could dominate the dataset.

4. **Cross-Validation Results (Mean: 89.75%)**: The cross-validation scores show that the model’s performance is consistent across different subsets of the data, with very little variation between the folds. This suggests that the model is robust and not overfitting to the training data. It generalizes well to new, unseen data.

5. **AUC Score (96%)**: The Area Under the ROC Curve (AUC) score of 96% means that the model is very good at distinguishing between the two classes (bookings and non-bookings). It indicates that the model has a strong ability to predict positive outcomes (actual bookings) and negative outcomes (non-bookings) with high confidence.

6. **Feature Importance**: The feature importance analysis shows that certain variables, like purchase lead time and service requests, significantly impact booking predictions. This gives valuable insights into customer behavior and helps British Airways understand which factors influence bookings the most.

### What This Says About the Model:
- **Reliable & Accurate**: The model performs exceptionally well across different metrics, making it a reliable tool for predicting customer bookings.
- **Generalizability**: The consistent cross-validation scores and high AUC suggest that the model generalizes well and isn’t overfitting, meaning it will likely perform similarly on other data sets.
- **Balanced & Robust**: With balanced precision, recall, and F1-scores, the model can accurately predict both bookings and non-bookings without leaning too much in one direction. This makes it robust and suitable for real-world application.
- **Actionable Insights**: The feature importance analysis offers actionable insights into what drives customer behavior, helping British Airways fine-tune their booking strategies.

In summary, the model is not only highly accurate but also reliable and robust, making it a strong tool for optimizing British Airways' customer booking processes.
