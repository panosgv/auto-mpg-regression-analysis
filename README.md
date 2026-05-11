# Vehicle Fuel Efficiency (MPG) Predictive Modeling

## Project Objective
This project investigates the predictive modeling of vehicle fuel efficiency (MPG) using physical engineering attributes . The goal is to compare a baseline linear model against advanced non-linear architectures and regularized techniques.

## Dataset Overview
- **Source**: UCI Machine Learning Repository (Auto MPG Dataset).
- **Instances**: 398 vehicle entries.
- **Features**: 8 explanatory features including vehicle weight, horsepower, displacement, and geographical origin.
- **Target**: Miles Per Gallon (MPG).

## Machine Learning Pipeline
1. **EDA**: Visualizing MPG distribution and identifying non-linear trajectories between weight and fuel efficiency.
2. **Preprocessing**: Statistical imputation for 6 missing horsepower values, one-hot encoding for the "origin" feature, and numerical scaling.
3. **Modeling**:
   - Baseline: Linear Regression.
   - Non-linear: Polynomial Regression and Random Forest Ensembles.
   - Regularized: Ridge, Lasso, and Elastic Net to handle feature multicollinearity.
