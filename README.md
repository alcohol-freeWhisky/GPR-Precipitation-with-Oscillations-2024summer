# GPR-Precipitation-with-Oscillations-2024summer
Code and data for Gaussian Process Regression for Predicting Precipitation with Oscillations and Reducing Uncertainty Over Time.

# Gaussian Process Regression for Predicting Precipitation with Periodic Oscillations and Reducing Uncertainty Over Time

This repository contains the code and data for a Gaussian Process Regression (GPR) project focused on predicting precipitation patterns that exhibit periodic oscillations, with the added capability of updating predictions and uncertainty over time as more observations become available.

## Project Structure

The project is organized into the following directories:

1. **ENSO index**: Contains code for experiments using the El Niño-Southern Oscillation (ENSO) index as a dataset. This is a synthetic experiment designed to test GPR models' ability to capture periodic oscillations.

2. **Middle-range synthetic data**: Contains code for experiments using a middle-range synthetic dataset, where the data is generated with predefined periodic features. This is another experimental dataset aimed at testing the efficacy of various kernel functions.

3. **CMIP5**: Contains code for working with precipitation data from the CMIP5 climate model outputs. This directory represents previous work, where GPR was applied to predict long-term trends.

4. **CMIP6**: Contains the primary code for working with real-world precipitation data from the CMIP6 climate model outputs. The focus of the project is on applying GPR to predict both short-term and long-term precipitation oscillations, using the most up-to-date data from CMIP6.

5. **data**: This folder holds all datasets used in the project, including middle-range synthetic data, real-world data from CMIP5, CMIP6, and the ENSO index.

## Gaussian Process Regression (GPR) Overview

Gaussian Process Regression (GPR) is a powerful non-parametric method for regression problems that uses a probabilistic framework to make predictions. A key aspect of GPR is that it not only predicts the mean of the output but also provides uncertainty estimates around the prediction, which can be updated dynamically as more data is observed.

In this project, GPR is employed to capture the periodic oscillatory nature of precipitation data and reduce predictive uncertainty over time. The critical part of this method is constructing suitable kernel functions to model the data's characteristics. Kernel functions measure similarity between data points and define how the model behaves. We use common kernel functions such as the Radial Basis Function (RBF) kernel and periodic kernels, along with customized kernel combinations, to effectively capture oscillations and trends.

### Key Components:
- **Kernel Functions**: We use a variety of standard kernel functions combined with periodic transformations. These include the RBF, ExpSineSquared (periodic), DotProduct, RationalQuadratic kernels, and their combinations and transformation. Additionally, we implement a customized kernel function, **KGCM**, designed to capture long-term trends in precipitation data.
  
- **Model Fitting**: The GPR models are primarily built using the `sklearn` library, with some custom-written code for specialized kernel functions. 

- **Hyperparameter Tuning**: Hyperparameters for the GPR model, such as kernel parameters, are fine-tuned using Bayesian optimization techniques. We leverage the `bayesian-optimization` library to find the optimal set of hyperparameters.

## Workflow

1. **Data Visualization**: The project includes tools for visualizing precipitation data and periodic oscillations. This helps identify patterns and validate the model's predictions.

2. **Periodic Analysis**: Techniques are applied to understand the periodic behavior in the precipitation data, which is crucial for constructing effective kernel functions.

3. **Function and Kernel Construction**: Various kernel functions are constructed and tested using synthetic data from the **ENSO index** and **middle-range synthetic data** experiments.

4. **Real Data Application**: The chosen kernel functions are applied to real-world CMIP6 precipitation data. Predictions are made for short-term and long-term periods, accounting for periodic oscillations and reducing predictive uncertainty over time.

5. **Uncertainty Evolution**: The project analyzes how uncertainty in predictions evolves as more data is observed, particularly focusing on short-term and long-term periodic oscillations in the real-world precipitation data.

## Installation

To run this project, you will need to install the following dependencies:

```bash
pip install numpy pandas scikit-learn matplotlib bayesian-optimization
```

## Usage

To reproduce the results:
1. Navigate to one of the code directories (e.g., `ENSO index` or `CMIP6`).
2. Run the scripts to load the data and fit the GPR models.
3. Experiment with different kernel combinations and hyperparameter settings as desired.
4. Visualize the results and analyze prediction uncertainty.

## Results

Detailed results and visualizations are available in the corresponding folders. For more information, please refer to the project poster.
