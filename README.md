# Economic Development and Health Outcomes: GDP, Healthcare Spending, and Life Expectancy

---

## 1. Motivation

Over the last several decades, the relationship between economic development and population health has been a central concern in global policy. Countries with higher GDP often have more resources to invest in healthcare systems, which can translate into better health outcomes — including higher life expectancy. However, the relationship is not always straightforward: some countries achieve high life expectancy despite comparatively lower GDP, suggesting that efficient healthcare spending and strong public health policies can compensate for economic constraints.

This project examines how GDP per capita and healthcare spending are associated with life expectancy across countries. Using official cross-national datasets, the study investigates whether economic prosperity directly improves health outcomes, or whether the impact is mediated by the level and efficiency of healthcare investment.

---

## 2. Research Questions and Sub-Questions

**Main Question**

* How do economic development indicators — such as GDP and healthcare spending — affect life expectancy across countries?

**Sub-Questions**

1. Does higher GDP per capita lead to higher life expectancy?
2. Does higher public and private healthcare spending improve life expectancy, even in countries with moderate GDP?
3. Are countries with similar GDP but different healthcare spending levels showing significant differences in life expectancy?

---

## 3. Hypotheses

* **H1:** Regions with higher GDP per capita and lower healthcare inefficiency will have higher levels of life expectancy.
* **H2:** Countries with higher GDP per capita will show higher life expectancy at birth.
* **H3:** Higher healthcare expenditure (per capita or as % of GDP) is positively associated with longer life expectancy.
* **H4:** The relationship between economic advantage and life expectancy weakens when healthcare spending efficiency is controlled for — countries with similar GDP but better-allocated health budgets achieve superior outcomes.
* **H0 (Null):** GDP and healthcare spending have no significant relationship with life expectancy.

---

## 4. Data Description

| Dataset | Variables | Purpose |
| --- | --- | --- |
| **World Bank – World Development Indicators (WDI)** | GDP per capita (constant USD) | Main indicator of economic development |
| **World Bank WDI / WHO Global Health Expenditure Database** | Total healthcare expenditure per capita (USD) and % of GDP | Measures investment in healthcare systems |
| **WHO / World Bank** | Life expectancy at birth (years) | Primary health outcome of interest |
| **UN Human Development Reports** | HDI, education, urbanization (optional) | Control variables for robustness checks |

### 4.1 Data Collection Methods

- **World Bank – WDI (GDP per capita):** World Bank Open Data REST API via `wbdata` Python library.
- **WHO Global Health Expenditure Database (Healthcare Expenditure):** Bulk download from `apps.who.int/nha/database`.
- **WHO / World Bank (Life Expectancy):** World Bank API using the life expectancy indicator.
- **UN Human Development Reports (HDI, Education, Urbanization):** Bulk CSV download from `hdr.undp.org/data-center`.


---

## 6. Methodology

### 6.1 Exploratory Data Analysis

Exploratory analysis visualizes the distribution of key variables across income groups and regions, time trends in GDP, healthcare spending, and life expectancy, and the bivariate relationships between economic and health indicators.

---

### 6.2 Hypothesis Testing

* **H1 & H2:** Correlation analysis and grouped comparisons (low / middle / high income countries) to assess the GDP–life expectancy relationship.
* **H3:** Regression of life expectancy on healthcare expenditure (per capita and % of GDP), controlling for income level.
* **H4:** Mediation analysis and interaction models to test whether healthcare efficiency moderates the GDP effect on life expectancy.


### 6.3 Machine Learning Analysis

Machine learning methods are used to complement statistical inference with predictive modeling of life expectancy outcomes:

- **Regression models:** Linear Regression (baseline), Ridge, Lasso, ElasticNet, Random Forest, Gradient Boosting, and SVR — predicting life expectancy at birth (years) from GDP per capita, healthcare expenditure per capita, and healthcare spending as % of GDP.
- **Explainability:** SHAP values computed on the best-performing tree-based model to quantify each feature's contribution and test the mediation effect proposed in H4.
- **Classification task:** Countries classified into life expectancy tiers (Low / Middle / High) based on income group, healthcare spending level, and regional indicators.
- **Clustering:** K-Means and hierarchical clustering to identify countries that achieve high life expectancy despite moderate GDP — empirical test of H4.
- **Evaluation:** Time-aware train–test split (pre-2015 train, 2015–present test); regression evaluated using RMSE and R²; classification using accuracy, F1-score, and confusion matrices; clustering using silhouette scores.

---

---

## 7. Expected Results

The project expects to find a positive association between GDP per capita and life expectancy across countries. Higher healthcare spending — both per capita and as a share of GDP — is expected to improve health outcomes across income levels. The positive effect of GDP on life expectancy is anticipated to be partially mediated by healthcare investment, consistent with H3. Countries with efficient healthcare systems are expected to achieve higher life expectancy even at comparatively lower GDP levels, supporting H4.

These findings will highlight that sustained improvements in population health depend not only on economic growth, but equally on the effective and equitable allocation of resources toward healthcare systems.

---

*End of README.md*
