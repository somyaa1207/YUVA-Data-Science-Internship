# Week 4 – Supervised Learning

## Objective

The objective of Week 4 is to implement supervised machine learning techniques using Python and Scikit-learn for a real-world real estate dataset.

The task focuses on building regression models to predict property prices based on selected property characteristics.

## Problem Statement

This project addresses a **regression problem**, where the goal is to predict the price of a property using features such as:

- Area
- BHK Count
- RERA Approval
- Property Status
- Flat Type

The target variable is **Price**.

## Dataset

The dataset contains real estate property listings from Gurugram.

After data cleaning and preprocessing, the dataset contains:

- **14,223 records**
- **12 original columns**

## Data Preparation

The following preprocessing steps were performed:

- Converted price and rate per square foot into numerical values.
- Standardized categorical values.
- Converted RERA approval into a binary feature.
- Selected relevant numerical and categorical features.
- Handled categorical variables using One-Hot Encoding.
- Applied median imputation to numerical features.
- Applied most-frequent imputation to categorical features.
- Standardized numerical features.
- Split the data into training and testing sets using an 80:20 ratio.

## Feature Engineering

The following features were used for prediction:

- `area`
- `bhk_count`
- `rera_approval`
- `status`
- `flat_type`

The feature `rate_per_sqft` was excluded because it is derived from property price and area, which could cause target leakage.

High-cardinality fields such as locality, builder name, society, company name, and property type were also excluded from the final model.

## Models Implemented

Three supervised regression models were implemented:

1. Linear Regression
2. Random Forest Regressor
3. Gradient Boosting Regressor

## Model Evaluation

The models were evaluated using:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score
- 5-Fold Cross-Validation

### Model Comparison

| Model | MAE | RMSE | Test R² | Mean CV R² |
|---|---:|---:|---:|---:|
| Linear Regression | ₹2.62 Cr | ₹5.95 Cr | 6.93% | -1667.24% |
| Random Forest | ₹1.15 Cr | ₹3.39 Cr | 69.86% | 57.06% |
| Gradient Boosting | ₹1.50 Cr | ₹3.64 Cr | 65.20% | 50.93% |

## Best Model

The **Random Forest Regressor** performed the best among the three models.

It achieved:

- **Test R²: 69.86%**
- **Mean Cross-Validation R²: 57.06%**
- **MAE: ₹1.15 Cr**
- **RMSE: ₹3.39 Cr**

Therefore, Random Forest was selected as the final model.

## Feature Importance

The Random Forest model identified **Area** as the most influential feature for predicting property price.

Major feature contributions included:

- Area – 86.31%
- BHK Count – 6.62%
- RERA Approval – 1.23%
- Status – approximately 1%
- Flat Type – approximately 1%

Feature importance indicates the contribution of features to the model's predictions and should not be interpreted as causal relationships.

## Results

The final model was used to generate predictions on the test dataset. The actual and predicted prices were compared through visual analysis, along with residual analysis.

The model performed reasonably well for the available dataset, although larger errors were observed for some high-priced properties.

## Strengths

- Uses a complete Scikit-learn preprocessing pipeline.
- Compares multiple supervised learning algorithms.
- Uses cross-validation for model validation.
- Includes multiple regression evaluation metrics.
- Identifies important predictive features.
- Provides actual property price predictions.

## Limitations

- The dataset contains extreme property prices and areas.
- Some high-priced properties produce larger prediction errors.
- Several high-cardinality categorical variables were excluded.
- The available features do not capture all factors affecting real estate prices.

## Future Improvements

Future work can include:

- Hyperparameter tuning.
- Log transformation of the target variable.
- More detailed location-based features.
- Additional property-related features.
- Advanced ensemble models.
- Larger and more diverse datasets.

## Files Included

- `Real Estate Data Set Week 4.ipynb` – Complete Python notebook
- `real_estate_regression_results.csv` – Actual and predicted results
- `Week_4_Internship_Report.docx` – Detailed internship report
- `README.md` – Project documentation

## Conclusion

Week 4 successfully implemented supervised learning for real estate price prediction. Among the evaluated models, Random Forest provided the strongest predictive performance and was selected as the final model.

The project demonstrates the complete supervised learning workflow, including data preparation, feature engineering, model training, validation, evaluation, prediction, and interpretation.
