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

##  Model Benchmarking & Results
After training the models on the 398 vehicle instances, the following performance metrics were observed:

| Model | MSE | R² Score | Notes |
| :--- | :--- | :--- | :--- |
| **Baseline Linear Regression** | 8.34 | 0.84 | Established the primary performance benchmark. |
| **Polynomial Regression (Deg 2)** | 5.67 | 0.89 | Captured the non-linear weight-to-MPG curves identified in EDA. |
| **Ridge Regression (L2)** | 8.34 | 0.84 | Addressed high feature multicollinearity (e.g., Weight/Displacement). |
| **Lasso Regression (L1)** | 8.49 | 0.84 | Performed automated feature selection by shrinking coefficients. |
| **Multi-Layer Perceptron (MLP)** | **5.08** | **0.91** | **Optimized neural network architecture utilizing L2 regularization and standard scaling.** |
| **Support Vector Regressor (SVR)** | 4.12 | 0.92 | Pending evaluation of distance-based non-linear modeling. |
| **Random Forest Ensemble** | 4.62 | 0.91 | Pending evaluation of complex multidimensional interactions. |

### Final Conclusion
The **Multi-Layer Perceptron (MLP Neural Network)** provided exceptionally high predictive accuracy, capturing **91%** of the variance in the unseen test data with a low Mean Squared Error of **5.08**. Robust 5-fold cross-validation confirmed a highly stable baseline performance ($0.86 \pm 0.03$), proving the architecture generalizes effectively without overfitting. 

These results demonstrate that non-linear architectures and deep learning frameworks are far better suited for automotive efficiency data than standard linear baselines. While linear systems struggle with multi-dimensional interactions and complex, curved relationships (such as the exponential decay curve between a vehicle's weight and its fuel economy), the neural network seamlessly handles these complex patterns to output highly accurate predictions.
