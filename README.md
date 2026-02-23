# MS-AAI-Azure-Analysis: Predicting Latency in Serverless Functions
**Course:** AAI-500  
**Institution:** University of San Diego 

## Project Overview
This repository contains the code, data visualizations, and final technical report for our statistical analysis of Microsoft Azure Serverless Functions. The primary objective of this project is to determine if invocation load (`Count`) can accurately predict execution latency (`Average` duration) using machine learning models.

## Repository Structure
To maintain a clean and reproducible environment, this repository is structured as follows:

* `FinalProject.ipynb`: The primary Jupyter Notebook containing the full data pipeline. This includes data cleaning, logarithmic transformations, exploratory data analysis (EDA), and the training/evaluation of the Linear Regression and Random Forest models.
* `Technical_Report.pdf`: The finalized academic report detailing our statistical methodology, assessment of assumptions, and operational conclusions.
* `rf_actual_vs_predicted.png`: The generated scatter plot visualizing the Random Forest model's performance and the dispersion of latency predictions.
* `README.md`: This project overview and structural guide.

*(Note: The raw Azure Functions dataset is excluded from this repository to adhere to data privacy and GitHub file-size best practices. The code assumes the data file is placed in the local root directory).*

## Key Statistical Findings
1. **Target Leakage Identification:** Initial multivariate models utilizing `Minimum` and `Maximum` execution times yielded artificially high R² scores (>0.90). This was identified as target leakage, as these metrics are aggregated concurrently with the target variable (`Average`). They were intentionally discarded to preserve operational validity.
2. **Model Performance:** The valid models (using only Invocation Load) yielded extremely low explanatory power. The Random Forest model outperformed the Linear baseline but still resulted in an R² of 0.098.
3. **Operational Conclusion:** The low correlation mathematically proves that Microsoft Azure’s underlying infrastructure effectively decouples scale from speed. Auto-scaling mechanisms successfully provision resources to handle traffic spikes without proportional performance degradation.

## Team Contributors
* Kunal Gurtoo
* Moinuddin Ghouse
* Raj Dave