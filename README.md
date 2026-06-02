# Vehicle Fuel Efficiency (MPG) Predictive Modeling

## 📝 Project Objective
This project investigates the predictive modeling of vehicle fuel efficiency (MPG) using physical engineering attributes. The goal is to compare a baseline linear model against advanced non-linear architectures and regularized techniques.

## Dataset Information
The dataset used in this project is the Auto MPG dataset, which concerns city-cycle fuel consumption. 

- **Official Source**: [UCI Machine Learning Repository - Auto MPG](https://archive.ics.uci.edu/dataset/9/auto+mpg)
- **Origin**: Modified from the StatLib library at Carnegie Mellon University [Quinlan, 1993].
- **License**: Creative Commons Attribution 4.0 International (CC BY 4.0).

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
   - Non-linear: Polynomial Regression, Random Forest Ensembles.
   - Regularized: Ridge and Lasso to handle feature multicollinearity.
4. **Evaluation**: Benchmarking performance using Mean Squared Error (MSE) and R².

## 📈 Model Benchmarking & Results
To ensure a rigorous evaluation, all models were benchmarked using 10-Fold Cross-Validation. This process evaluates each model across multiple data subsets to measure true generalization performance and stability.

Models are ranked below by their cross-validated R² scores:

| Model | CV R² (Std) | CV MSE (Std) |
| :--- | :--- | :--- |
| **Random Forest Ensemble** | 0.85 (± 0.04) | 9.03 (± 3.18) |
| **Polynomial Regression (Deg 2)** | 0.85 (± 0.04) | 9.09 (± 1.73) |
| **Support Vector Regressor (SVR)** | 0.82 (± 0.04) | 11.10 (± 3.57) |
| **Ridge Regression (L2)** | 0.80 (± 0.03) | 12.04 (± 2.59) |
| **Lasso Regression (L1)** | 0.80 (± 0.03) | 12.03 (± 2.78) |
| **Baseline Linear Regression** | 0.80 (± 0.03) | 12.07 (± 2.59) |

## Final Conclusion
The benchmarking results indicate that non-linear architectures perform consistently better than linear baselines on this dataset. The Random Forest Ensemble and Polynomial Regression (Degree 2) achieved the highest predictive accuracy, both reaching an R² of 0.85.

While the Polynomial Regression and Random Forest models showed similar R² performance, the Polynomial Regression exhibited lower standard deviation in its MSE (1.73), suggesting higher stability across different data folds. The linear models (Baseline, Ridge, and Lasso) all performed near-identically, confirming that while a linear relationship exists, capturing non-linear interactions is essential for maximizing predictive performance on this specific feature set.

An additional observation emerged during the evaluation process regarding the influence of the train-test split selection. The initial split performed using a random state of 42 produced slightly optimistic results compared to the final cross-validation metrics, indicating that this partition represented a comparatively favorable distribution of the dataset. To further investigate this behavior, an additional implementation cell was included using a random state of 72, which generated results substantially closer to the cross-validation performance. This observation further supports the use of cross-validation as a more reliable and representative framework for evaluating model generalization.
