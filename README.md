# COVID-19 Vaccine Time Series Analysis
**Authors:** Benjamin Mario Sainz-Tinajero, Dachely Otero Argote, and Carmen Elisa Orozco Mora  
**Paper title:** "A COVID-19 Macro Time Series Analysis of Vaccine Impact"  

Source code of the methodology proposed for predicting the group of countries using a specific vaccine with the less steep COVID-19 contagion rate using time series analysis.  

**Abstract:** Economic, social encounters, and most importantly, human life were deeply affected by the COVID-19 pandemic, with a vaccination process that started in 2021 to tackle the spread of the virus. This paper offers a broad overview of the worldwide vaccination process and related relevant factors that are influenced by it, as well as a benchmark between three proposed solutions to track the progress of the COVID-19 vaccination. In this work, we present a methodology using time series to analyze the vaccines with the greatest worldwide presence and predict which country group using certain vaccines has a less steep curve of confirmed cases for three weeks. The experiments led to 94\% of the data fitting our models on average, leading to a confident suggestion on the vaccine-related to the less steep foreseeable contagion spread.

## Vaccine Selection
Our approach starts with exploratory data analysis for finding the five vaccines with the most significant worldwide presence. The user is encouraged to decide from two metrics the vaccine manufacturers be analyzed: the number of countries that have applied the vaccine at least for one day and vaccines with the greatest quantity of days being used at least once. We selected Pfizer/BioNTech, Oxford/Astra-Zeneca, Moderna, Johnson&Johnson and Sinovac, but this decision may vary depending on the time of application of the study. The next phase in our methodology is to find all of the countries using each vaccine and summing their daily confirmed COVID-19 cases. The last 21 days are kept as holdout data for testing the models. The notebook offers visualizations of the decomposition of the time series of the cases per vaccine.

## Modeling
Five ARIMA models are trained using the time series with multiple parameters, and the set with the lowest AIC and BIC are returned. The five final ARIMA models are trained with the resulting parameters, and the Mean Squared Error (MSE) and Root Mean Squared Error (RMSE) using the test data are printed. Afterwards, you can plot the predictions of the ARIMA models per vaccine to compare how they differ from the summed cases of the countries using the vaccine over time.

## Deployment
The predictions of the 21 days posterior to the dataset's last entry are used to train the regression model for finding a linear regression that best fits the data. The evaluation metrics for the linear models per vaccine are presented. This phase will return a dictionary containing the vaccine manufacturer in a string, the linear regression coefficient, score, and intercept. Plots are displayed for comparing the ARIMA models' predictions and their linear regression, and for this analysis, we would now have the complete information we need to make a decision. Our study concludes that the group of countries using the vaccine by Johnson&Johnson has the less steep contagion rate for the foreseeable prediction dates.

The proposed methodology is available in this repository in a Python implementation.

# Setup and run using Python
Open the provided notebook and run each cell. You will need two clean datasets containing the clean data related to the daily confirmed cases per country and vaccination progress in the countries to be analyzed.  
**Important**: You will need to have previously installed some basic data science and visualization packages such as seaborn, NumPy, pandas, and sci-kit-learn.

We hope this approach is informative and can provide a helpful perspective on the worldwide vaccination progress,  
Dachely, Carmen, and Benjamin  

# References
1. Bhandarkar, P.: Covid-19 eda: Man vs disease (Feb 2021), https://www.kaggle.com/pawanbhandarkar/covid-19-eda-man-vs-disease
2. Dong, E., Du, H., Gardner, L.: An interactive web-based dashboard to track covid- 19 in real time. The Lancet infectious diseases 20(5), 533–534 (2020)
3. Ho, S.L., Xie, M.: The use of arima models for reliability forecasting and analysis. Computers & industrial engineering 35(1-2), 213–216 (1998)
4. Le, T.T., Andreadakis, Z., Kumar, A., Roma ́n, R.G., Tollefsen, S., Saville, M., Mayhew, S., et al.: The covid-19 vaccine development landscape. Nat Rev Drug Discov 19(5), 305–306 (2020)
5. Mathieu, E., Ritchie, H., Ortiz-Ospina, E.: A global database of covid-19 vaccina- tions (2021), https://github.com/owid/covid-19-data/
6. Mathieu, E.: Usa covid-19 vaccinations. Our World in Data (2021), https://ourworldindata.org/us-states-vaccinations
7. Mooney, P.: Usa covid-19 vaccinations (May 2021), https://www.kaggle.com/paultimothymooney/usa-covid19-vaccinations
8. Pozdniakov, A.: Covid-19: Can we predict the future? (Mar 2021), https://www.kaggle.com/gpreda/covid-world-vaccination- progress/tasks?taskId=3176
9. Preda, G.: Covid19 daily updates (Feb 2021), https://www.kaggle.com/gpreda/coronavirus-2019ncov/version/140
10. Reback, J., McKinney, W., jbrockmendel, den Bossche, J.V., Augspurger, T., Cloud, P., Hawkins, S., gfyoung, Sinhrks, Roeschke, M., Klein, A., Petersen, T., Tratner, J., She, C., Ayd, W., Naveh, S., patrick, Garcia, M., Schendel, J., Hayden, A., Saxton, D., Jancauskas, V., Gorelli, M., Shadrach, R., Mc- Master, A., Battiston, P., Seabold, S., Dong, K., chris b1, h vetinari: pandas- dev/pandas: Pandas 1.2.4 (apr 2021). https://doi.org/10.5281/zenodo.4681666, https://doi.org/10.5281/zenodo.4681666
11. Ritchie, H., Ortiz-Ospina, E., Beltekian, D., Mathieu, E., Hasell, J., Macdonald, B., Giattino, C., Appel, C., Roser, M., Rod ́es-Guirao, L.: Coronavirus pandemic (covid-19). Our World in Data (2020), https://ourworldindata.org/coronavirus
12. Rolland, E., Patterson, R.A., Ward, K., Dodin, B.: Decision support for disaster management. Operations Management Research 3(1-2), 68–79 (2010)
13. Sevgi, S.: Covid-19 world vaccination progress with tableau (Feb 2021), https://www.kaggle.com/sevgisarac/covid-19-world-vaccination-progress-with- tableau
14. Van Rossum, G., Drake, F.L.: Python 3 Reference Manual. CreateSpace, Scotts Valley, CA (2009)
15. Waskom, M.L.: seaborn: statistical data visualization. Journal of Open Source Software 6(60), 3021 (2021). https://doi.org/10.21105/joss.03021, https://doi.org/10.21105/joss.03021
16. Wirth, R., Hipp, J.: Crisp-dm: Towards a standard process model for data mining. In: Proceedings of the 4th international conference on the practical applications of knowledge discovery and data mining. vol. 1. Springer-Verlag London, UK (2000)
17. World Health Organization: Who director-general’s opening remarks at the media briefing on covid-19 - 11 march 2020 (2020), https://www.who.int/director- general/speeches/detail/who-director-general-s-opening-remarks-at-the-media- briefing-on-covid-19—11-march-2020
18. Worldometers.info: Real time world statistics (May 2021), https://www.worldometers.info/
