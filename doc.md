# NYC Airbnb Listings Exploratory Data Analysis

---

## **Table of Contents**
1. Key Business Questions
2. Dataset Overview
3. Analysis Methodologies
4. Exploratory Data Analysis (EDA)
5. Regression Analysis
6. Hypothesis Testing
7. Shortcomings
8. Conclusions and Recommendations
9. References

---

## **1. Key Business Questions**
How do Room Type, Neighborhood, and Other Factors Influence Pricing Trends in the New York City Airbnb Market? This analysis aims to quantitatively determine how attributes like reviews and minimum nights affect prices using statistical tools.

---

## **2. Dataset Overview**
### **Dataset Chosen**
- **Source**: AB_NYC_2019.csv from Kaggle.
- **Attributes**:
  - Hosts, availability, location, room type, and pricing.
- **Purpose**: Supports detailed regression and EDA to answer business questions.

### **Variables and Constraints**
- 16 variables were reviewed; 9 key variables selected for analysis (6 numerical, 3 categorical).
- Key Transformations:
  - `reviews_per_month` chosen to avoid autocorrelation with `number_of_reviews`.
  - Dummy variables for `neighbourhood_group` and `room_type`.


---

## **3. Analysis Methodologies**
- Regression Analysis:
  - Removed price outliers > $1,000.
  - Converted categorical variables into dummy variables.
  - Evaluated R-squared values for model performance.
- Hypothesis Testing:
  - Two-sample t-tests for price differences.
  - Chi-Square test for variable independence.

---

## **4. Exploratory Data Analysis (EDA)**
### **Key Insights**
1. **Room Type**:
   - Entire homes/apartments (52% of listings) have the highest median prices.
   - Private rooms (45%) cater to budget travelers; shared rooms (3%) are least common.
2. **Neighborhood**:
   - Manhattan and Brooklyn host 85.4% of listings, dominating the premium market.
   - Queens (11.6%), Bronx, and Staten Island account for the rest.
3. **Price Distribution**:
   - Skewed with most listings under $200/night and outliers inflating maximums.

---

## **5. Regression Analysis**
### **Model Summary**
- **Model Fit**:
  - R-squared: 29.2% of the variance in price is explained by the predictors.
  - Adjusted R-squared: Adjusted to account for the number of predictors, indicating a moderate model fit.

### **Key Predictors and Their Impact**
- **Intercept**:
  - Baseline price for an entire home/apartment in the Bronx is approximately $137.02.

- **Neighborhood Groups**:
  - Manhattan: Listings are $70.99 more expensive than the Bronx.
  - Brooklyn: Listings are $25.40 more expensive than the Bronx.
  - Queens: Listings are $9.79 more expensive than the Bronx.
  - Staten Island: Prices are $3.40 lower than the Bronx (not statistically significant).

- **Room Types**:
  - Entire home/apartments command the highest prices (baseline category).
  - Private Rooms: $100.23 cheaper than Entire home/apartments.
  - Shared Rooms: $125.61 cheaper than Entire home/apartments.

- **Other Variables**:
  - Reviews per Month: Each additional review decreases price by $3.42, indicating budget-friendly properties attract more reviews.
  - Availability (365): Each additional day of availability increases price by $0.12, showing minimal impact.
  - Host Listings Count: Each additional property listed by the same host increases price by $0.06.

### **Interpretation**
1. **Neighborhood Influence**:
   - Prices are significantly higher in Manhattan and Brooklyn, reflecting their premium market.
2. **Room Type Significance**:
   - Room type is the strongest determinant, with Entire homes/apartments generating the highest prices.
3. **Minimal Impact of Reviews and Availability**:
   - While reviews and availability affect pricing, their impact is relatively minor compared to neighborhood and room type.

### **Conclusion**
The regression model highlights that room type and neighborhood are the most significant factors influencing Airbnb pricing. These findings can guide hosts and platform strategies to optimize revenue.

---

## **6. Hypothesis Testing**
### **T-Test Results**
1. Entire homes/apartments vs. private rooms: Significant price difference.
2. Private vs. shared rooms: Significant price difference.
3. Minimum nights <10 vs. >10: Significant price difference.
4. Brooklyn vs. Manhattan: Significant price difference.

### **Chi-Square Test**
- Tested `neighbourhood_group` and `room_type` dependency.
- Result: Significant dependency (p-value < 0.05), supporting neighborhood-specific pricing trends.

---

## **7. Shortcomings**
- **Limited R-squared**: Model explains only 29.2% of price variance.
- **Right-Skewed Data**: Despite removing outliers, pricing remains skewed.
- **Multicollinearity**: Correlated variables may affect model assumptions.
- **Geographical Scope**: NYC-specific, limiting generalizability.
- **Data Relevance**: 2019 dataset may not reflect post-pandemic conditions.

---

## **8. Conclusions and Recommendations**
### **Conclusions**
- Room type and neighborhood are the strongest determinants of price.
- Manhattan and Brooklyn listings dominate the high-end market.
- Budget travelers prefer private/shared rooms in Bronx or Staten Island.
- Reviews and availability have minimal impact on pricing.

### **Recommendations**
1. **Hosts**:
   - Focus on Entire homes/apartments in Manhattan or Brooklyn for higher earnings.
   - Offer budget-friendly options in Bronx and Staten Island to attract frequent bookings.
2. **Airbnb**:
   - Target marketing campaigns for budget-friendly and luxury segments.
   - Provide pricing insights based on neighborhood and room type.

---

## **9. References**
- Estrada, Grace. New York Airbnb Investment Recommendation. Kaggle.
- Dataset: [New York City Airbnb Open Data](https://www.kaggle.com/code/graceestrada/new-york-airbnb-investment-recommendation).
