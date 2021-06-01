# COVID-19 Vaccine Time Series Analysis
**Authors:** Benjamin Mario Sainz-Tinajero, Dachely Otero Argote, and Carmen Elisa Orozco Mora  
**Paper title:** "COVID-19 Macro Time Series Analysis of Vaccine Impact"  

Source code of the methodology proposed for predicting the group of countries using certain vaccine with the less steep COVID-19 contagion rate using time series analysis.  

**Abstract:** Economic, social encounters, and most importantly, human life was deeply affected by the COVID-19 pandemic, with a vaccination process that started in 2021 for tackling the spread of the virus. This paper offers a broad overview of the worldwide vaccination process along with related relevant factors that are influenced by it, as well as a benchmark between three proposed solutions to track the progress of the COVID-19 vaccination. In this work, we present a methodology using time series for analyzing the vaccines with greatest worldwide presence and to predict which country group using certain vaccine has a less steep curve of confirmed cases for a time period of three weeks. The experiments led to 94\% of the data fitting our models in average, leading to a confident suggestion on the vaccine related to the less steep foreseeable contagion spread.

## Vaccine Selection
Our approach starts with exploratory data analysis for finding the five vaccines with the greatest worldwide presence. The user is encouraged to decide from two metrics the vaccine manufacturers to be analyzed: number of countries that have applied the vaccine at least for one day, and vaccines with greatest quantity of days being applied at least once. We selected Pfizer/BioNTech, Oxford/Astra-Zeneca, Moderna, Johnson&Johnson and Sinovac, but this decision may vary depending on the time of application of the study. The next phase in our methodology is to find all of the countries using each vaccine and summing their daily confirmed COVID-19 cases. The last 21 days are kept as holdout data for testing the models. The notebook offers visualizations of the decomposition of the time series of the cases per vaccine.

## Modeling
Five ARIMA models are trained using the time series with multiple parameters, and the set with lowest AIC and BIC are returned. The five final ARIMA models are trained with the resulting parameters and the Mean Squared Error (MSE) and Root Mean Squared Error (RMSE) using the test data is printed. Afterwards, you can plot the predictions of the ARIMA models per vaccine to compare how they differ from the summed cases of the countries using the vaccine over time.

## Deployment
The predictions of the 21 days posterior to the dataset's last entry are used to train regression model for finding a linear regression that best fits the data. The evaluation metrics for the linear models per vaccine are presented. This phase will return a dictionary containing the vaccine manufacturer in a string, the linear regression coefficient, score, and intercept. Plots are displayed for comparing the ARIMA models' predictions and their linear regression, and for this analysis, we would now have the complete information we need to make a decision. Our study concludes that the group of countries using the vaccine by Johnson&Johnson has the less steep contagion rate for the foreseeable predcition dates.

The proposed methodology is available in this repository in a Python implementation.

# Setup and run using Python
Open the provided notebook and run each cell. You will need two clean datasets containing the clean data related to the daily confirmed cases per country and vaccinatio progress in the countries to be analyzed.  
**Important**: You will need to have previously installed some basic data science and visualization packages such as seaborn, numpy, pandas, and scikit-learn.

We hope this approach is informative and can provide a useful perspective on the worldwide vaccination progress,  
Dachely, Carmen, and Benjamin 
