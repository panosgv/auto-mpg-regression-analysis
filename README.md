# Vehicle Fuel Efficiency (MPG) Predictive Modeling

## Project Objective
This project investigates the predictive modeling of vehicle fuel efficiency (MPG) using physical engineering attributes [3]. The goal is to compare a baseline linear model against advanced non-linear architectures and regularized techniques.

## Dataset Overview
- **Source**: UCI Machine Learning Repository (Auto MPG Dataset) [2].
- **Instances**: 398 vehicle entries [1, 4].
- **Features**: 8 explanatory features including vehicle weight, horsepower, displacement, and geographical origin [1, 5].
- **Target**: Miles Per Gallon (MPG) [5].

## Machine Learning Pipeline
1. **EDA**: Visualizing MPG distribution and identifying non-linear trajectories between weight and fuel efficiency [1, 6, 7].
2. **Preprocessing**: Statistical imputation for 6 missing horsepower values, one-hot encoding for the "origin" feature, and numerical scaling [1, 4, 8].
3. **Modeling**:
   - Baseline: Linear Regression [3].
   - Non-linear: Polynomial Regression and Random Forest Ensembles [3].
   - Regularized: Ridge, Lasso, and Elastic Net to handle feature multicollinearity [3, 9].
