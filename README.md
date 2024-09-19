# Insurance-Claims-Predictive-Modelling

# Insurance Claims Prediction with GLM

This repository contains code for building a **Generalized Linear Model (GLM)** to predict the probability of claims (`claim_status`) and the claim amount (`claim_amount`) using a dataset of insurance records. The goal is to help in dynamic pricing by modeling customer and vehicle characteristics to predict the likelihood of claims.

## Table of Contents



## Dataset

The dataset contains the following key variables:

- `subscription_length`: How long the customer has been subscribed (continuous).
- `vehicle_age`: Age of the vehicle (continuous).
- `customer_age`: Age of the customer (continuous).
- `region_density`: Population density in the customer's region.
- `claim_status`: Binary target variable indicating whether a claim was made (0 or 1).
- `claim_amount`: Continuous target variable representing the claim amount.

### Example of Dataset Structure:
| subscription_length | vehicle_age | customer_age | region_density | claim_status | claim_amount |
|---------------------|-------------|--------------|----------------|--------------|--------------|
| 9.3                 | 1.2         | 41           | 8794           | 0            | 0            |
| 8.2                 | 1.8         | 35           | 27003          | 0            | 0            |
| 9.5                 | 0.2         | 44           | 8794           | 0            | 0            |

## Installation

To run this project, you'll need to have Python installed along with the following libraries:

```bash
pip install pandas statsmodels scikit-learn matplotlib
# Example of metrics calculation:
rmse = np.sqrt(mean_squared_error(y_true, y_pred))
mae = mean_absolute_error(y_true, y_pred)
r2 = r2_score(y_true, y_pred)

.
├── data/
│   └── Insurance_claims_data_export.xlsx  # Dataset used for modeling
├── glm_model.py                           # Main script for running the GLM model
├── README.md                              # This readme file
├── requirements.txt                       # List of required Python libraries
└── results/
    └── glm_results.txt                    # Output of the GLM model summary


Model Description
We implemented a Binomial GLM with Logit link for classification tasks (predicting claim status) and a Gaussian GLM for regression tasks (predicting claim amount). Both models use customer and vehicle features such as subscription length, vehicle age, and region density.

Features:
GLM for Binary Classification (Claim Status Prediction): Logistic regression using features like subscription_length, vehicle_age, and others to predict the likelihood of a claim.
GLM for Regression (Claim Amount Prediction): Gaussian family used to predict continuous values of claim_amount based on similar features.
Key Findings:
The subscription length and vehicle age significantly influence both the probability of a claim and the claim amount.
The model's explanatory power (Pseudo R-squared) is relatively low, indicating room for improvement with additional features or model complexity.
Metrics
Root Mean Squared Error (RMSE): Measures the average magnitude of the prediction errors.
Mean Absolute Error (MAE): Average of the absolute differences between predicted and actual values.
R-squared (R²): Proportion of variance explained by the model (not commonly used for classification but shown here for reference).
python
