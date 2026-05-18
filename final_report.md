# Economic Development and Health Outcomes: GDP, Healthcare Spending, and Life Expectancy

This final report examines how economic development and healthcare expenditure are associated with life expectancy across countries. The project combines exploratory data analysis, hypothesis testing, and machine learning to evaluate whether GDP per capita and healthcare expenditure can explain and predict differences in population health outcomes.

## 1. Motivation

The relationship between economic development and population health has long been an important topic in global development research. Countries with higher GDP per capita generally have greater financial capacity to invest in healthcare systems and public services. These factors can contribute to better health outcomes, especially longer life expectancy.

However, the relationship between economic development and life expectancy is not always linear or economic. Some middle-income countries achieve relatively high life expectancy despite having lower GDP per capita than wealthier countries. This suggests that healthcare efficiency, accessibility, and public health policy might be as important as the economic resources.

This project investigates how GDP and healthcare expenditure per capita are associated with life expectancy across countries and over time. The main goal is to understand whether higher economic development is linked to better health outcomes and whether healthcare spending helps explain this relationship. To address this, the project combines exploratory data analysis, hypothesis testing, and machine learning models.

## 2. Datasets and Data Enrichment

The analysis uses three main country-level datasets:

- **Life expectancy at birth:** This dataset measures average life expectancy in years and works as the main health outcome variable.
- **GDP per capita:** GDP per capita is used as the main indicator of economic development. It captures the average level of economic output per person in a country.
- **Healthcare expenditure per capita:** This variable represents the level of investment in healthcare systems.

The datasets were merged using country, country code, and year. This created a country-year panel dataset that allows the project to compare economic and health indicators across both countries and time. During preprocessing, column names were standardized, numerical variables were converted to proper formats, invalid country codes were removed, and missing values were dropped.

To reduce skewness, log-transformed variables were created for GDP per capita and healthcare expenditure. These transformations were especially useful because economic variables are highly skewed: a small number of countries have very high GDP and healthcare spending compared to the rest of the dataset.

## 3. Final Dataset

After data cleaning and merging, the EDA and hypothesis testing notebook produced a final merged dataset with 4,043 country-year observations and 7 variables. The key variables used in the analysis were country, country code, year, life expectancy, GDP per capita, region, and healthcare expenditure per capita.

The machine learning notebook used a similar merged dataset after additional preprocessing and applied a time-aware train-test split. The test set consisted of the most recent years, while earlier years were used for training. This split was selected to reduce temporal leakage and evaluate whether the models can generalize to newer country-year observations.

## 4. Hypothesis Testing

The main hypotheses were defined as follows:

- $H_0$: GDP per capita and healthcare expenditure have no significant relationship with life expectancy.
- $H_1$: GDP per capita is associated with healthcare expenditure.
- $H_2$: GDP per capita is associated with life expectancy.
- $H_3$: Healthcare expenditure is associated with life expectancy.

The results support all three alternative hypotheses. GDP per capita and healthcare expenditure showed a very strong positive relationship. The Pearson correlation was *r* = 0.937, and the Spearman correlation was *rho* = 0.943, both with p-values reported as approximately zero. This suggests that countries with higher GDP per capita generally spend more on healthcare.

GDP per capita was also strongly and positively associated with life expectancy. The Pearson correlation between log GDP and life expectancy was *r* = 0.823, with a p-value approximately equal to zero. A t-test comparing high-GDP and low-GDP groups also showed a significant difference in life expectancy. The low-GDP group had an average life expectancy of 64.58 years, while the high-GDP group had an average of 76.33 years.

Healthcare expenditure was strongly and positively associated with life expectancy as well. The Pearson correlation was *r* = 0.831, with a p-value approximately equal to zero. The t-test comparing high and low healthcare spending groups showed that countries with lower healthcare expenditure had an average life expectancy of 64.69 years, while countries with higher healthcare expenditure had an average of 76.22 years.

Overall, the tests provide strong evidence against the null hypothesis. GDP per capita and healthcare expenditure are both significantly related to life expectancy.

## 5. Machine Learning Models

Machine learning models were used to predict life expectancy from economic and healthcare indicators in order to complement the statistical analysis.

Several models were tested: Dummy Regressor, Linear Regression, Ridge Regression, Decision Tree, and Random Forest. The Dummy Regressor acted as a baseline model. The goal was to check whether economic and healthcare variables can predict life expectancy better than simply predicting the average value.

The best-performing model was Random Forest Regression. It performed better than the baseline model, showing that GDP per capita, healthcare expenditure, time, and regional information contain useful signals for predicting life expectancy. Instead of focusing only on individual scores, the model results were interpreted together with cross-validation, tuning, feature importance, and residual analysis.

After hyperparameter tuning, Random Forest remained the strongest regression model. This suggests that the relationship between economic indicators and life expectancy is partly non-linear. However, the model should not be interpreted as perfect, because some country-year observations still had noticeable prediction errors.

A possible limitation is overfitting. Random Forest models can learn complex patterns from the training data, especially when countries differ strongly in income levels, healthcare systems, and regional conditions. Cross-validation and a time-aware train-test split were used to reduce this risk, but the model may still generalize better to some countries and years than to others.

Feature importance analysis showed that region, GDP per capita, and healthcare expenditure per capita were among the most influential predictors. This supports the main finding that economic capacity and healthcare investment are related to life expectancy, while regional and structural differences also matter.

The largest prediction errors were treated as an important limitation rather than ignored. These errors may occur in country-years where life expectancy is affected by factors not fully captured in the dataset, such as conflict, pandemics, sudden economic shocks, inequality, public health policy, or differences in healthcare access and efficiency.

An optional classification task was included only as a secondary extension by grouping countries into broad life expectancy tiers. Since the main objective of the project is life expectancy prediction, the main conclusions of the machine learning section are based on the regression task rather than the classification task.

## 6. Results

The findings consistently show that economic development and healthcare expenditure are related to life expectancy across exploratory analysis, hypothesis testing, and machine learning.

The correlation analysis showed strong positive relationships among life expectancy, GDP per capita, and healthcare expenditure. Life expectancy was positively related to both log GDP per capita and log healthcare expenditure, while GDP and healthcare spending were also closely related to each other. This supports the idea that countries with stronger economic capacity often have more resources to invest in health systems.

The hypothesis tests confirmed that countries with higher GDP and higher healthcare expenditure tend to have higher life expectancy. However, the relationship is not perfectly proportional. The visual analysis suggests diminishing returns: after a certain level of economic development or healthcare spending, additional increases are associated with smaller gains in life expectancy.

The machine learning models reinforced these findings in the prediction setting. Random Forest performed best among the regression models, suggesting that economic and healthcare indicators can help predict life expectancy.

## 7. Summary

This project demonstrates that life expectancy is connected to both economic development and healthcare investment. Countries with higher GDP per capita generally spend more on healthcare.

The results support the main argument of the project: economic resources matter for health outcomes, but healthcare investment and broader structural factors also play important roles. The strong correlation between GDP and healthcare expenditure suggests that richer countries often have more capacity to invest in health systems.

The combination of hypothesis testing and machine learning provides a broader understanding of the topic. Statistical tests confirm significant relationships, while machine learning shows that these variables have predictive value for the main life expectancy regression task.

## 8. Limitations and Future Work

There are several limitations to this project.

First, the analysis is observational. The results show strong associations, but they do not prove causality. Higher GDP and healthcare spending are linked with higher life expectancy, but this does not mean that GDP or healthcare spending alone directly causes longer life expectancy.

Second, the analysis is based on country-level data. This means that individual-level differences such as income inequality, personal access to healthcare, education, lifestyle, and local health conditions are not directly observed.

Third, the dataset focuses mainly on GDP per capita, healthcare expenditure, region, and life expectancy. Other important variables such as education, urbanization, government effectiveness, inequality, nutrition, environmental quality, and healthcare efficiency were not fully included in the final modeling stage.

Fourth, GDP and healthcare expenditure are highly correlated. This creates multicollinearity, making it harder to separate the independent effect of each variable.

Fifth, the machine learning results may have generalization limitations. Although cross-validation and the time-aware split make the evaluation more reliable, the model is still trained on historical country-level patterns and may not fully capture unusual future events or country-specific conditions.

Sixth, the largest prediction errors show that GDP and healthcare expenditure alone cannot explain every life expectancy outcome. In some countries, life expectancy may be strongly influenced by factors outside the model.

Future work could improve the project by adding more control variables such as education level, income inequality, and healthcare quality indicators.

## 9. Usage of LLMs and AI

AI tools, including large language models, were used to support this project through code debugging, explanation of statistical concepts, notebook organization, and language refinement.

All analytical decisions, dataset choices, modeling steps, and final interpretations remain the responsibility of the author. AI was used as a supportive tool and does not replace the original analysis conducted in the project.
