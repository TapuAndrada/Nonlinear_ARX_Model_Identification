# Nonlinear_ARX_Model_Identification
This project implements a nonlinear ARX (AutoRegressive with eXogenous input) model to identify an unknown dynamic system using polynomial regression. The goal is to approximate the system's behavior by selecting optimal model orders (na, nb) and polynomial degree (m). The model is trained using least-squares estimation and evaluated on a separate validation dataset.  

## Problem Overview
Given an unknown system with one input and one output, the objective is to build a black-box nonlinear ARX model. The dataset contains noisy measurements, and the system's dynamics may be nonlinear with an order not exceeding three. The model uses delayed input-output pairs to predict future outputs.

## Methodology
Polynomial ARX Model: Constructs a nonlinear ARX model using polynomial terms of past inputs and outputs.  
Feature Generation: The regression model incorporates delayed values and their interactions (e.g., y(k-1), u(k-1), y(k-1)^2, y(k-1) * u(k-1)).  
Parameter Estimation: Uses linear regression to determine the best-fitting model coefficients.  
Model Evaluation: Compares performance using Mean Squared Error (MSE) for both training and validation data.  
 Prediction vs. Simulation:  
One-step-ahead prediction: Uses real past outputs for accurate short-term forecasting.  
Free-run simulation: Uses only predicted values, mimicking a real-world scenario.  
## Files
iddata-18.mat – Dataset file containing identification and validation data.  
Nonlinear_ARX_Identification.m – The primary script implementing the nonlinear ARX model.
## Results
Error Analysis: MSE is computed for different model orders (na, nb) to determine the optimal complexity.
Model Selection: The best polynomial degree and order are chosen based on validation performance, balancing underfitting and overfitting.
Visualization: Graphs illustrate prediction errors and simulation accuracy for different configurations.
