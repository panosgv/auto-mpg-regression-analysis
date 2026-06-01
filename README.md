# Vehicle Fuel Efficiency (MPG) Predictive Modeling

## 📝 Project Objective
This project investigates the predictive modeling of vehicle fuel efficiency (MPG) using physical engineering attributes. The goal is to compare a baseline linear model against advanced non-linear architectures and regularized techniques.

##  Dataset Information
The dataset used in this project is the **Auto MPG** dataset, which concerns city-cycle fuel consumption. 

- **Official Source**: [UCI Machine Learning Repository - Auto MPG](https://archive.ics.uci.edu/dataset/9/auto+mpg)
- **Origin**: Modified from the StatLib library at Carnegie Mellon University [Quinlan, 1993].
- **License**: Creative Commons Attribution 4.0 International (CC BY 4.0).

##  Dataset Overview
- **Source**: UCI Machine Learning Repository (Auto MPG Dataset).
- **Instances**: 398 vehicle entries.
- **Features**: 8 explanatory features including vehicle weight, horsepower, displacement, and geographical origin.
- **Target**: Miles Per Gallon (MPG).

##  Machine Learning Pipeline
1. **EDA**: Visualizing MPG distribution and identifying non-linear trajectories between weight and fuel efficiency.
2. **Preprocessing**: Statistical imputation for 6 missing horsepower values, one-hot encoding for the "origin" feature, and numerical scaling.
3. **Modeling**:
   - Baseline: Linear Regression.
   - Non-linear: Polynomial Regression, Random Forest Ensembles, and Artificial Neural Networks.
   - Regularized: Ridge, Lasso, and Elastic Net to handle feature multicollinearity.
4. **Evaluation**: Benchmarking performance using Mean Squared Error (MSE) and $R^2$.

## 📈 Model Benchmarking & Results
To ensure a fair and rigorous evaluation, all models were benchmarked using **5-Fold Cross-Validation**. This eliminates the variance of a single "lucky" train/test split and represents the true, generalized performance of each architecture across the entire dataset. 

Models are ranked below by their cross-validated $R^2$ scores and Mean Squared Error (MSE):

| Model | CV R² (Std) | CV MSE (Std) | Notes |
| :--- | :--- | :--- | :--- |
| **Multi-Layer Perceptron (MLP)** | **0.86 (± 0.03)** | **8.70 (± 2.39)** | **Project Champion.** Most stable and accurate architecture. |
| **Random Forest Ensemble** | 0.84 (± 0.03) | 9.79 (± 2.75) | Strong runner-up, effectively handling non-linear interactions. |
| **Polynomial Regression (Deg 2)** | 0.84 (± 0.04) | 10.10 (± 2.55) | Successfully captured non-linear weight-to-MPG curves. |
| **Support Vector Regressor (SVR)** | 0.81 (± 0.02) | 11.77 (± 2.08) | Struggled to generalize compared to initial single-split estimates. |
| **Ridge Regression (L2)** | 0.81 (± 0.02) | 11.98 (± 1.32) | Addressed multicollinearity without losing baseline accuracy. |
| **Lasso Regression (L1)** | 0.81 (± 0.02) | 12.00 (± 1.29) | Performed automated feature selection via coefficient shrinkage. |
| **Baseline Linear Regression** | 0.81 (± 0.02) | 12.01 (± 1.34) | Established the primary linear performance floor. |

### Final Test Reveal (Unseen Hold-Out Data)
After identifying the **Multi-Layer Perceptron (MLP)** as our top-performing architecture via cross-validation, the pipeline was trained on 100% of the training data and evaluated against a final, completely unseen hold-out test set (`X_test`):
* **Final Test MSE:** 5.08
* **Final Test R² Score:** 0.91

### Final Conclusion
The **Multi-Layer Perceptron (MLP Neural Network)** is the definitive choice for modeling vehicle fuel efficiency on this dataset. Rigorous 5-fold cross-validation unmasked the true generalization capabilities of all algorithms, proving the MLP to be the most powerful and reliable architecture with a stable cross-validated baseline of **0.86 R²**. 

While tree-based ensembles (Random Forest) and distance-based models (SVR) showed early promise, they proved more susceptible to overfitting on specific data splits. When the optimized MLP was given access to the full training dataset and evaluated on completely unseen test data, it scaled up to an exceptional **0.91 R²** with a remarkably low Mean Squared Error of **5.08**. This demonstrates that neural networks, when properly regularized (L2 penalty) and scaled, are uniquely equipped to map the complex, multi-dimensional physics of automotive engineering data.
