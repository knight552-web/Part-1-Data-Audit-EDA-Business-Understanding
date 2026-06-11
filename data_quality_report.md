# Data Quality Report

## 1. Missing Values

- **`loyalty_tier`** and **`skin_type`** contain significant missing values.
  - These represent customers who are either not enrolled in loyalty programs or have not provided profile details.
  - Impact: Missing values may bias segmentation and modeling. These should be treated as a separate category (e.g., “Unknown”) rather than dropped.

- **`rating` (orders)** contains missing values.
  - Missing ratings likely indicate customers who did not provide feedback.
  - Impact: If ignored, this may skew satisfaction metrics. Imputation or indicator variables should be considered.

- Aggregated features such as:
  - `ticket_count`, `avg_sentiment`, `avg_resolution_time`
  - may contain nulls for customers with no support interactions.
  - Impact: These are structural nulls and should be treated as zero or neutral values.

---

## 2. Duplicate Records

- `orders.csv` contains duplicate-like records identified by `_DUP` in `order_id`.
- These simulate real-world duplication issues.

### Impact
- Inflates order count, monetary value, and frequency metrics.
- Must be deduplicated before feature engineering.

---

## 3. Outliers

From the boxplot of `gross_amount`:

- Most orders fall within a reasonable range (~₹0–₹5000).
- However, extreme outliers exist (₹20,000+).

### Impact
- Can heavily skew monetary features (total spend, averages).
- May distort model learning and segmentation.

### Recommendation
- Apply capping (winsorization) or log transformation.

---

## 4. Date Consistency & Leakage Risk

- `orders.csv` includes transactions after the snapshot date (2025-09-30).

### Impact
- Using these records would introduce data leakage, as they belong to the target window.

### Action Taken
```python
orders = orders[orders['order_date'] <= '2025-09-30']
```

---

## 5. Join Integrity

- All datasets are joined using `customer_id`.
- The base dataset (`customers.csv`) contains 2400 customers.

### Observations
- Not all customers have:
  - orders
  - support tickets
- This is expected behavior, not a data issue.

### Impact
- Requires careful handling of nulls post-join.

---

## 6. Feature-Level Observations

- `recency_days` shows wide variation, including very high values (>500 days).
- `total_spend` is right-skewed due to high-value customers.
- `ticket_count` is low for most users (1–2 tickets), limiting variance.
- `avg_sentiment` is mostly negative across customers, indicating general dissatisfaction bias.

---

## Final Assessment

The dataset is realistic and contains:
- Missing values
- Outliers
- Duplicate-like records
- Potential leakage risks

Proper preprocessing is essential before modeling or segmentation.
