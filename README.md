# Airline Ticket Prices vs Oil & Fuel Costs

## 1. Motivation
Throughout the last decades, the relationship between energy prices and transportation costs has been an important concern globally. Airlines rely heavily on fuel, and increases in oil and jet fuel prices can significantly affect operational costs. This often leads to higher ticket prices or additional charges such as fuel surcharges.  

However, this relationship is not always straightforward: some airlines absorb fuel costs through efficiency or hedging strategies, while others directly pass the costs to passengers.  

This project examines how oil and jet fuel prices are associated with airline ticket prices and airline financial outcomes. Using multiple datasets, the study investigates whether fuel costs directly increase ticket prices or whether the effect is mediated through airline strategies such as surcharges and operational adjustments.

---

## 2. Research Questions and Sub-Questions

### Main Question  
How do oil and fuel costs affect airline ticket prices?

### Sub-Questions  
- Does higher oil and jet fuel price lead to higher airline ticket prices?  
- Do fuel surcharges increase when fuel prices rise?  
- Do airlines respond differently depending on route type or airline category?  
- Do conflict-related disruptions affect ticket prices and fuel costs?  

---

## 3. Hypotheses  

- **H1:** Higher oil and jet fuel prices will lead to higher airline ticket prices  
- **H2:** Fuel surcharges will increase as fuel prices rise  
- **H3:** Airlines operating long-haul routes will be more affected by fuel price increases  
- **H4:** Conflict-related disruptions will amplify the effect of fuel prices on ticket prices  
- **H0 (Null):** Oil and fuel prices have no significant relationship with airline ticket prices  

---

## 4. Data Description  

| Dataset | Variables | Purpose |
|--------|----------|--------|
| airline_ticket_prices.csv | Ticket price, fuel surcharge, airline, route | Main airfare data |
| oil_jet_fuel_prices.csv | Brent crude, jet fuel price | Fuel price indicators |
| fuel_surcharges.csv | Surcharge values by airline | Measures cost pass-through |
| route_cost_impact.csv | Route cost, fuel usage | Operational impact |
| airline_financial_impact.csv | Revenue, fuel cost, profit | Airline financial outcomes |
| conflict_oil_events.csv | Conflict events, oil shocks | External disruptions |

---

## 4.1 Data Collection Methods  

- **Airline Ticket Prices:** CSV dataset including fare components and airline characteristics  
- **Oil and Jet Fuel Prices:** Monthly fuel price data including Brent crude and jet fuel prices  
- **Fuel Surcharges:** Airline-level surcharge data  
- **Route Cost Impact:** Route-level fuel consumption and cost dataset  
- **Airline Financial Impact:** Financial performance dataset including fuel costs and profit  
- **Conflict Events:** Dataset containing geopolitical events affecting oil supply and aviation  

---

## 6. Methodology  

### 6.1 Exploratory Data Analysis  
Exploratory analysis visualizes distributions of ticket prices, fuel prices, and surcharges, as well as time trends and relationships between fuel costs and airfare.  

---

### 6.2 Hypothesis Testing  

- **H1 & H2:** Correlation analysis between fuel prices and ticket prices / surcharges  
- **H3:** Group comparisons based on route type (short vs long haul)  
- **H4:** Analysis of conflict events and their effect on fuel prices and airfare  

---

### 6.3 Machine Learning Analysis  

- **Regression models:** Linear Regression, Ridge, Lasso, Random Forest, Gradient Boosting  
- **Classification:** Categorizing ticket prices into low / medium / high groups  
- **Clustering:** Identifying airline groups with similar pricing behavior  
- **Evaluation:** RMSE, R², Accuracy, F1-score, Silhouette score  

---

## 7. Expected Results  

The project expects to find a positive relationship between oil and jet fuel prices and airline ticket prices. Fuel surcharges are expected to increase with rising fuel costs.  

Airlines operating long-haul routes are expected to be more sensitive to fuel price changes. Conflict-related disruptions are expected to further increase both fuel prices and ticket prices.  

These findings will highlight that airline pricing is strongly influenced by energy markets and external geopolitical factors.
