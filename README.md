# Predicting Profitable Regions for Oil Well Development
## Project Overview
You are working for OilyGiant, a mining company tasked with finding the best location for a new oil well. The project involves analyzing geological data from three regions to predict the volume of oil reserves in new wells, identify the most promising wells, and ultimately select the region with the highest potential profit margin. The analysis includes a comprehensive risk assessment using the Bootstrapping technique.

## Objective
- Primary Goal: Build a machine learning model to predict oil reserves in wells across three regions and identify the region with the highest total profit.
- Secondary Goal: Assess potential profit and risks using the Bootstrapping technique and provide recommendations for investment decisions.

## Data Source
The dataset contains geological exploration data from three regions, stored in separate files:

- geo_data_0.csv
- geo_data_1.csv
- geo_data_2.csv

Each dataset includes the following features:

- id: Unique oil well identifier
- f0, f1, f2: Three features of points (their specific meaning is unimportant, but the features themselves are significant)
- product: Volume of reserves in the oil well (thousand barrels)
- Tools and Libraries
- Pandas: For data manipulation and analysis.
- Scikit-learn: For model training, testing, and evaluation.
- NumPy: For numerical computations and bootstrapping analysis.

## Project Workflow
1. Data Preprocessing
- Data Loading: Loaded data from the three regions into separate dataframes.
- Splitting the Data: Split the data for each region into a training set (75%) and a validation set (25%).
- Model Training: Trained a Linear Regression model for each region and made predictions on the validation set.
- Model Evaluation: Calculated the average predicted reserves and the Root Mean Squared Error (RMSE) for each model to assess prediction accuracy.
2. Profit Calculation Preparation
- Key Values for Calculation: Defined all necessary parameters, including budget, revenue per barrel, and the number of wells to be selected.
- Reserve Volume Threshold: Calculated the minimum reserve volume needed to break even and compared this with the average reserve volume in each region.
3. Profit Calculation and Region Selection
- Profit Calculation Function: Developed a function to calculate profit based on selected wells with the highest predicted reserves.
- Region Selection: Used the profit calculation function to select the most profitable region based on the highest average profit and lowest risk of loss.
4. Risk Assessment using Bootstrapping
- Bootstrapping Simulation: Performed 1000 bootstrap simulations to assess the distribution of profits for each region.
- Risk Metrics: Calculated the average profit, 95% confidence interval, and risk of loss (percentage of simulations where profit was negative) for each region.

## Results and Conclusions
Region 0:
- Mean Profit: $4,028,465.14
- 95% Confidence Interval: [-$1,129,119.72, $9,203,146.13]
- Risk of Loss: 5.1%

Region 1:
- Mean Profit: $4,422,033.42
- 95% Confidence Interval: [$453,430.28, $8,611,047.25]
- Risk of Loss: 1.2%

Region 2:
- Mean Profit: $3,846,202.77
- 95% Confidence Interval: [-$1,852,021.09, $9,099,954.80]
- Risk of Loss: 7.6%

Conclusion:
- Region 1 stands out as the best option for investment, offering the highest mean profit and the lowest risk of loss (1.2%). The confidence interval for Region 1 does not include negative values, indicating more stable profit outcomes.
- Region 0 is a viable secondary option, but with a higher risk of loss (5.1%) and wider variability in profit.
- Region 2 poses the highest risk of loss (7.6%) and is therefore the least attractive for investment.
- The Bootstrapping analysis provided valuable insights into the expected financial outcomes and their variability, guiding a data-driven investment decision for OilyGiant.
