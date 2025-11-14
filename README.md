# 🛴 GoFast Scooter Rental Service: Business & Statistical Analysis

This project involves a comprehensive data analysis of the GoFast scooter rental service's 2021 usage data. The goal is to perform an exploratory data analysis (EDA), calculate monthly user revenue, and use statistical hypothesis testing (t-tests) to provide data-driven recommendations for improving business profitability.

## 📊 Key Findings & Business Recommendations

The analysis confirms the economic value of the 'Ultra' subscription, providing a clear path for business strategy.

* **Higher Profitability:** **Ultra subscription users generate significantly higher average monthly revenue** compared to Free users.
* **Greater Engagement:** Ultra users have a **statistically longer average ride duration**.
* **Low Wear Risk:** The average ride distance for Ultra users **does not significantly exceed the optimal scooter wear distance** (3130 meters).
* **Primary Recommendation:** Focus marketing efforts on **converting Free users to Ultra subscribers** to maximize long-term company revenue.

***

## ⚙️ Methodology & Technologies

### Data Preprocessing
1.  **Data Cleaning:** Handled explicit duplicates (31 removed) and checked for implicit duplicates.
2.  **Feature Engineering:** Calculated the month number from the ride date.
3.  **Billing Logic:** Ride durations were **rounded up to the nearest whole minute** ($\text{np.ceil}$) to align with the company's billing policy.
4.  **Revenue Calculation:** Created a detailed `profit` column by summing monthly fee, trip start costs, and per-minute costs for each user.

### Statistical Analysis
The project utilized **two-sample t-tests** (with Welch's correction) and a **one-sample t-test** to compare group means and test against a predefined benchmark ($\mu = 3130 \text{m}$).

* **Hypothesis 1 (Duration/Profit):** Used Levene's test to check for unequal variances, leading to the application of Welch's t-test for a robust comparison of means.
* **Optimization Implemented:** The final version of the notebook included a check for the equality of variances before running two-sample t-tests to ensure statistical rigor.

### Tools & Libraries
* **Python 3.x**
* **Pandas** (Data manipulation and aggregation)
* **NumPy** (Numerical operations, incl. duration ceiling)
* **Matplotlib / Seaborn** (Exploratory Data Analysis and visualization)
* **SciPy.stats** (T-tests and Levene's test)

***

## 📝 Data Description (Pricing)

| Subscription Type | Monthly Fee | Start Ride Price | Cost per Minute |
| :--- | :--- | :--- | :--- |
| **Free** | 0 RUB | 50 RUB | 8 RUB |
| **Ultra** | 199 RUB | 0 RUB | 6 RUB |
