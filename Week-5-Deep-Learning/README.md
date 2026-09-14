# Week 5 – Deep Learning Application in Data Science

## Project Overview

Week 5 focuses on applying deep learning concepts to a real-world regression problem using Python and TensorFlow.

The project uses a Gurugram real-estate dataset to develop a neural network model for predicting property prices. The workflow covers data preparation, feature preprocessing, neural network design, model training, validation, evaluation, experimentation, and interpretation.

## Problem Statement

The objective is to predict the price of a property based on available property characteristics.

This is formulated as a **regression problem** because the target variable, price, is a continuous numerical value.

## Dataset

The project uses the cleaned Gurugram real-estate dataset developed during the internship.

- Records: 14,223
- Target variable: `price`
- Numerical features: `area`, `bhk_count`, `rera_approval`
- Categorical features: `status`, `flat_type`
- Training observations: 11,378
- Test observations: 2,845

## Data Preprocessing

The following preprocessing steps were applied:

- Converted RERA approval into a binary numerical feature.
- Applied median imputation and standardization to numerical features.
- Applied most-frequent imputation and one-hot encoding to categorical features.
- Used a consistent preprocessing workflow for training and testing.
- Standardized the target variable during the final neural-network experiment.

The `rate_per_sqft` feature was not used because it is derived from price and area and could introduce target leakage.

## Neural Network Approach

A feed-forward neural network was implemented using TensorFlow and Keras.

The final architecture consists of:

- Dense layer with 64 neurons and ReLU activation
- Dropout layer with 20% dropout
- Dense layer with 32 neurons and ReLU activation
- Dropout layer with 20% dropout
- Dense layer with 16 neurons and ReLU activation
- Output layer with 1 neuron

The model was trained using the Adam optimizer and Mean Squared Error loss.

Early stopping with restoration of the best weights was used to reduce unnecessary training and help control overfitting.

## Model Experiments

Three neural-network approaches were evaluated:

| Model | MAE | RMSE | R² Score |
|---|---:|---:|---:|
| Baseline Neural Network | ₹2.65 Cr | ₹6.01 Cr | 5.20% |
| Log-Transformed Neural Network | ₹2.53 Cr | ₹6.17 Cr | 0.18% |
| Scaled-Target Neural Network | ₹1.79 Cr | ₹4.57 Cr | 45.09% |

The **Scaled-Target Neural Network** was selected as the final deep learning model because it achieved the lowest MAE and RMSE and the highest R² score among the tested neural-network approaches.

## Final Model Performance

The final model achieved:

- MAE: ₹17,913,580
- MSE: 2.091 × 10¹⁵
- RMSE: ₹45,727,510
- R² Score: 45.09%
- Test samples: 2,845

The R² score indicates that the final neural network explains approximately 45.09% of the variation in property prices on the held-out test data.

## Training and Evaluation

Training and validation loss were monitored throughout the training process.

The final model trained for approximately 37 epochs before early stopping. The training and validation loss curves were used to examine learning behaviour and potential overfitting.

Actual-versus-predicted and residual plots were also used to evaluate prediction quality.

The results show that the model performs more consistently for the majority of lower-to-mid-priced properties, while extreme high-value properties remain more difficult to predict accurately.

## Challenges and Insights

The major challenge was the highly variable scale of property prices.

The baseline neural network produced weak predictive performance. A log-transformed target was then tested, but it did not improve the overall R² score.

Standardizing the target variable produced a substantial improvement, increasing the R² score from 5.20% to 45.09%.

The analysis also showed that extreme property prices contribute to larger prediction errors.

## Limitations

- The model uses a limited set of property characteristics.
- Detailed location, builder, society, and company information was not directly incorporated.
- Extreme property-price observations remain difficult to predict.
- The current model does not capture all market and location-specific factors.
- The model is intended for analytical and educational purposes rather than professional property valuation.

## Future Improvements

Future work could improve the model by:

- Incorporating carefully encoded location-related features.
- Adding property amenities and market-related variables.
- Testing additional neural-network architectures.
- Performing systematic hyperparameter tuning.
- Experimenting with alternative target transformations.
- Using larger and richer real-estate datasets.
- Evaluating model performance separately across different price ranges.

## Project Files

- `Deep Learning Model.ipynb` – Executed deep learning notebook
- `deep_learning_predictions.csv` – Test-set predictions and residuals
- `deep_learning_training_history.csv` – Training and validation history
- `Week_5_Internship_Report_Final.docx` – Complete internship report

## Conclusion

This project demonstrates a complete deep learning workflow for real-estate price prediction, from data preparation and neural-network design to training, evaluation, experimentation, and interpretation.

The final Scaled-Target Neural Network achieved an R² score of 45.09%, demonstrating meaningful predictive capability while also highlighting the challenges of applying neural networks to real-estate data containing substantial price variation and extreme observations.
