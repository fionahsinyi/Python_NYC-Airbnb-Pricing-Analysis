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
<img width="580" alt="截圖 2024-12-25 中午12 51 47" src="https://github.com/user-attachments/assets/f6d13bbd-b493-49ce-a3ce-96033cd642a2" />

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
1. **Room Type Distribution**:
   - Entire homes/apartments account for 52% of listings, commanding the highest median prices.
   - Private rooms make up 45% and are popular among budget travelers.
   - Shared rooms represent only 3% of listings, serving niche markets.

2. **Neighborhood Distribution**:
   - Manhattan and Brooklyn dominate with 85.4% of all listings.
   - Queens contributes 11.6%, while Bronx and Staten Island together account for just 3%.
   - Listings are concentrated in high-demand areas like Manhattan's Central Park vicinity and Brooklyn's waterfronts.
![newplot (6)](https://github.com/user-attachments/assets/2111659e-085d-4287-91be-ea70c910e9e7)

3. **Price Distribution**:
   - Most listings are priced below $200 per night, but outliers inflate the average.
   - Entire homes/apartments exhibit the widest price range, from affordable units to luxury properties.
   - Private and shared rooms have tighter price distributions, catering to budget-conscious travelers.
<img width="882" alt="截圖 2024-12-25 中午12 53 14" src="https://github.com/user-attachments/assets/95b25067-4ebb-4d03-98db-3f6efca73c65" />

4. **Price by Neighborhood**:
   - Manhattan leads with the highest median prices due to its premium location and high demand for entire homes/apartments.
   - Brooklyn offers slightly lower median prices, appealing to mid-range travelers.
   - The Bronx and Staten Island have the most affordable options, with fewer luxury offerings.
![newplot (7)](https://github.com/user-attachments/assets/8ce26311-0a9a-4ebd-919e-fd442e34f57f)

5. **Geographical Trends**:
   - Heatmaps of listings reveal high-density clusters around Central Park in Manhattan and Williamsburg in Brooklyn.
   - Listings are sparsely distributed in outer boroughs like Staten Island and the Bronx.
<img width="575" alt="截圖 2024-12-25 中午12 55 28" src="https://github.com/user-attachments/assets/b30ddbf8-00e0-41c0-9779-a21c71551f1a" />

6. **Correlation Analysis**:
   - Weak correlation between availability and price, indicating limited impact of availability on pricing.
   - Negative correlation between reviews per month and price, suggesting budget-friendly properties attract more frequent reviews.
<img width="699" alt="截圖 2024-12-25 中午12 56 05" src="https://github.com/user-attachments/assets/92c75043-86a6-4add-9fdc-2544f8d9f106" />

---

## **5. Regression Analysis**
### **Model Summary**
- **Model Fit**:
  - R-squared: 29.2% of the variance in price is explained by the predictors.
  - Adjusted R-squared: Adjusted to account for the number of predictors, indicating a moderate model fit.
<img width="667" alt="截圖 2024-12-25 中午12 56 48" src="https://github.com/user-attachments/assets/11eece18-e1fb-4bc2-b04f-fb3a65fb04e4" />

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

