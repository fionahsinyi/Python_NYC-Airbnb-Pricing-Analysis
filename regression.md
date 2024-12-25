# Regression Analysis

## **1. Regression Analysis in All Neighborhoods**

### **Description**:
This section examines the relationship between Airbnb prices and key predictors across all neighborhoods. The analysis employs Ordinary Least Squares (OLS) regression to quantify the influence of factors like neighborhood group, room type, reviews per month, availability, and host listings count on pricing.

### **Results**:
| Predictor                        | Coefficient | p-value  | Interpretation                                  |
|----------------------------------|-------------|----------|------------------------------------------------|
| Intercept                        | 137.02      | 0.000    | Baseline price for Entire Home/Apt in Bronx.   |
| `reviews_per_month`              | -3.42       | 0.000    | Each review/month reduces price by $3.42.     |
| `availability_365`               | 0.12        | 0.000    | Each additional day increases price by $0.12. |
| `calculated_host_listings_count` | 0.06        | 0.000    | Each additional listing increases price by $0.06. |
| `neighbourhood_group_Manhattan`  | 70.99       | 0.000    | Listings are $70.99 more expensive in Manhattan. |
| `room_type_Private room`         | -100.23     | 0.000    | Private rooms are $100.23 cheaper.            |

### **Interpretation**:
The model explains 29.2% of the variance in price (R-squared = 0.292). Room type and neighborhood group are the most significant predictors.
<img width="671" alt="截圖 2024-12-25 下午1 44 23" src="https://github.com/user-attachments/assets/52f5a042-96a5-4e1b-b51b-80c871fc3602" />
<img width="918" alt="截圖 2024-12-25 下午1 44 49" src="https://github.com/user-attachments/assets/18f56f79-9ba8-4b65-a13d-6cba18415813" />

---

## **2. Regression Analysis in Individual Neighborhoods**

### **A. Brooklyn**

#### **Results**:
| Predictor              | Coefficient | p-value  | Interpretation                          |
|------------------------|-------------|----------|------------------------------------------|
| Intercept              | 165.73      | 0.000    | Baseline price for Entire Home/Apt.      |
| `reviews_per_month`    | -4.79       | 0.000    | Each review reduces price by $4.79.     |
| `availability_365`     | 0.09        | 0.000    | Each day increases price by $0.09.      |
| `room_type_Private`    | -96.27      | 0.000    | Private rooms are $96.27 cheaper.       |

#### **Interpretation**:
Brooklyn listings show a strong influence of room type and reviews per month on prices, with a moderate R-squared of 0.278.
<img width="653" alt="截圖 2024-12-25 下午1 45 10" src="https://github.com/user-attachments/assets/2ddb5257-4dc3-4c86-a22b-8c1db2b44560" />
<img width="919" alt="截圖 2024-12-25 下午1 45 27" src="https://github.com/user-attachments/assets/27c90c50-936d-4df6-8b4e-d21d7b528223" />

---

### **B. Manhattan**

#### **Results**:
| Predictor              | Coefficient | p-value  | Interpretation                          |
|------------------------|-------------|----------|------------------------------------------|
| Intercept              | 206.01      | 0.000    | Baseline price for Entire Home/Apt.      |
| `reviews_per_month`    | -1.03       | 0.056    | Weak negative impact of reviews.        |
| `availability_365`     | 0.16        | 0.000    | Stronger positive impact of availability.|
| `room_type_Private`    | -112.47     | 0.000    | Private rooms are $112.47 cheaper.      |

#### **Interpretation**:
Manhattan exhibits higher prices overall, with availability having the strongest influence compared to other neighborhoods.
<img width="651" alt="截圖 2024-12-25 下午1 45 47" src="https://github.com/user-attachments/assets/7925ee96-fbcb-4fc0-8433-effb2d609e8d" />
<img width="913" alt="截圖 2024-12-25 下午1 46 01" src="https://github.com/user-attachments/assets/3178b815-03e5-4cb2-b8a6-c528d3003105" />

---

## **3. Key Insights Across Neighborhoods**

### **A. Reviews per Month vs Price**
- In Staten Island, reviews have the strongest negative correlation with price (-11.55).
- Manhattan shows minimal impact (-1.03), reflecting luxury market behavior.
<img width="903" alt="截圖 2024-12-25 下午1 46 27" src="https://github.com/user-attachments/assets/a6f95aa9-818d-4094-87ff-d31cdfca4667" />
![newplot (13)](https://github.com/user-attachments/assets/0a44553c-c14b-4fff-8bf0-fa198836198a)

### **B. Availability vs Price**
- Manhattan shows the highest positive correlation (0.16), suggesting that greater availability slightly increases price.
<img width="905" alt="截圖 2024-12-25 下午1 46 52" src="https://github.com/user-attachments/assets/fbe3a733-a21c-474e-9383-6411cf6a7876" />
![newplot (14)](https://github.com/user-attachments/assets/eeb1b77a-28c6-4738-be3f-a6bed3d848c9)

### **C. Host Listings Count vs Price**
- Staten Island has a negative impact (-4.61), while Bronx shows a slight positive effect (0.75).
<img width="903" alt="截圖 2024-12-25 下午1 47 18" src="https://github.com/user-attachments/assets/3e1234fa-b609-437b-ae87-411732e04550" />
![newplot (15)](https://github.com/user-attachments/assets/69300249-d83a-49f1-9192-1d96123d0d7e)

### **D. Room Type vs Price in Different Neighborhoods**
![newplot (16)](https://github.com/user-attachments/assets/6f081ca7-a0d4-4510-a28b-505d1a1c499c)

#### **Insights**:
1. **Manhattan**:
   - Prices for `Entire Home/Apt` are significantly higher than other neighborhoods.
   - Even `Private Rooms` in Manhattan often surpass `Entire Home/Apt` prices in Bronx or Staten Island.
2. **Brooklyn**:
   - Shows a more balanced price distribution across room types, but `Entire Home/Apt` still leads.
3. **Queens**:
   - Mid-range pricing with narrower gaps between room types compared to Manhattan or Brooklyn.
4. **Bronx and Staten Island**:
   - Both neighborhoods exhibit lower prices for all room types, catering to budget travelers.

#### **Conclusion**:
This boxplot emphasizes the price disparity between neighborhoods and room types, reinforcing the importance of location and accommodation type as pricing determinants.

---

## **4. Conclusion**
Room type and neighborhood group are the most significant predictors of Airbnb pricing in NYC. Individual neighborhood regressions highlight unique price determinants, aiding targeted pricing strategies for hosts and platforms.
