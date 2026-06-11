# Business Memo: Customer Churn Risk Insights

## Overview

An analysis of customer behavior, transaction patterns, support interactions, and engagement signals reveals several key drivers of churn. These insights should guide retention strategy before launching large-scale campaigns.

---

## Key Findings

### 1. Customer Inactivity is the Strongest Churn Indicator

- Customers who churn show significantly higher recency_days.
- Median recency for churned users is substantially higher than retained users.

**Interpretation:**  
Customers who have not purchased recently are highly likely to churn.

---

### 2. Lower Spending Customers Are More Likely to Churn

- Churned customers show lower median total spend compared to retained users.

**Interpretation:**  
Lower-value customers are less engaged and easier to lose.

However:
- Some high-value outliers also churn, representing high business risk.

---

### 3. Support Interactions Alone Are Weak Predictors

- Ticket count distribution is similar for churned and retained users.

**Interpretation:**  
Volume of support requests alone is not sufficient to predict churn.

---

### 4. Negative Customer Sentiment is Widespread

- Average sentiment scores are consistently negative across both groups.

**Interpretation:**  
Customer dissatisfaction is broadly present and may not be the sole driver of churn, but still signals systemic experience issues.

---

### 5. Engagement Gaps Drive Churn Risk

- Churned users tend to show:
  - lower activity
  - longer inactivity periods
- Abandoned carts show slight variation but not strong separation.

**Interpretation:**  
Lack of engagement is a stronger signal than browsing intent.

---

### 6. Extreme Purchase Behavior Exists

- A small number of customers show very high spending (₹20k+).

**Interpretation:**  
These high-value customers require special attention as their churn would result in disproportionate revenue loss.

---

## Key Risks

- High inactivity customers are not being re-engaged effectively
- Negative sentiment suggests broader product/service issues
- High-value customers are not sufficiently protected
- Retention strategies may not be targeted enough

---

## Recommendations

### 1. Prioritize Recently Inactive Customers
- Target customers with high recency_days
- Use re-engagement campaigns (email, offers)

### 2. Protect High-Value Customers
- Identify high spenders at risk of churn
- Provide premium support or exclusive incentives

### 3. Improve Customer Experience
- Address root causes of negative sentiment
- Reduce delivery delays and product dissatisfaction

### 4. Move Toward Behavioral Segmentation
- Avoid blanket discounting
- Segment customers based on:
  - recency
  - spending
  - engagement

### 5. Build Early Warning System
- Use recency and engagement signals to proactively identify churn risk

---

## Conclusion

Customer churn in this dataset is primarily driven by inactivity and disengagement, rather than isolated factors like support interactions.

Retention strategies should focus on:
- re-engaging inactive users,
- protecting high-value customers,
- and improving overall customer experience.
