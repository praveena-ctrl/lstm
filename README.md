# lstm
a project on Time Series Forecasting with LSTMs, you should use words that clearly communicate the project's purpose, the methodology, the data, and the expected results.
 Project Overview and Goals
This project implements a deep learning approach using Long Short-Term Memory (LSTM) Recurrent Neural Networks to perform multivariate time series forecasting on key global metrics related to Artificial Intelligence (AI) adoption and its impact on the workforce.

The primary goal is to:

Accurately predict the future trajectory of critical economic and labor indicators.

Model the temporal dependencies and complex, non-linear relationships between variables (e.g., how AI Investment may influence Automation Rate or Job Creation).

Provide a robust forecasting model that can be extended to other macroeconomic time series data.

 Data Source and Description
The analysis uses the Global AI and Workforce Automation Dataset (2015-2025).

Source File: global_ai_workforce_automation_2015_2025.csv

Time Period: Annual data spanning from 2015 to 2025.

Nature: Multivariate Time Series (multiple time-dependent variables are used to make predictions).

Key Features (Input/Output Variables): The dataset includes features such as:

AI_Investment_BillionUSD

Automation_Rate_Percent

Average_Salary_USD

Productivity_Index

Job_Creation_Million and Job_Displacement_Million

...and other country-specific metrics.

 Methodology: LSTM Deep Learning
The forecasting model is built upon the LSTM architecture, which is specifically designed to handle and remember patterns over long sequences of data, effectively mitigating the vanishing gradient problem common in simple Recurrent Neural Networks.

 Data Preprocessing
Feature Selection: Identifying the most relevant features (exogenous variables) for the target prediction variable (e.g., Automation_Rate_Percent or Job_Creation_Million).

Normalization/Scaling: All numerical features are scaled (e.g., using MinMaxScaler) to a range between 0 and 1. This ensures that features with larger numerical values (like Average_Salary_USD) do not dominate the training process.

Sequence Creation (Sliding Window): The multivariate data is restructured into sequences of lagged observations (e.g., using the last N time steps to predict the next T time steps).

3.2 Model Architecture
Model Type: A Stacked LSTM or Encoder-Decoder LSTM architecture is employed to enhance the model's ability to learn complex representations.

Layers: The model typically consists of multiple LSTM layers, followed by one or more Dense (Fully Connected) layers to produce the final forecast.

Training: The model is trained using the Adam optimizer and minimizing the Mean Squared Error (MSE) loss function.

 Installation and Setup
Prerequisites
Python (3.7+)

The following libraries:

pandas

numpy

matplotlib

scikit-learn (for scaling/splitting)

tensorflow or pytorch (for the LSTM model)

Bash

# Example installation command
pip install pandas numpy matplotlib scikit-learn tensorflow
 How to Run the Project
Clone the Repository (or Download Files):

Bash

git clone [your_repo_link]
Ensure Data is in Place: Place the global_ai_workforce_automation_2015_2025.csv file in the correct directory.

Run the Notebook: Execute the cells in the timeserieslstm.ipynb notebook sequentially to perform data loading, preprocessing, model training, and evaluation.

 Results and Evaluation
The model's performance is evaluated based on standard time series metrics, particularly for the multi-step-ahead forecasts on the test set.

Primary Metrics:

Root Mean Squared Error (RMSE): Measures the standard deviation of the residuals (prediction errors).

Mean Absolute Error (MAE): Measures the average magnitude of the errors.

Visualization: The results are visually presented by plotting the model's predicted values against the actual historical values to assess the forecasting accuracy and generalization ability.
