# Credit Card Transaction Analysis

Exploratory data analysis of 50,000 real credit card transactions, combining consumer spending behaviour analysis with a three-tier merchant fraud risk assessment — generating actionable business insights relevant to the financial services and fintech industry.

---

## Objective

Analyse consumer spending patterns across merchant categories, demographics and time periods, and assess merchant-level fraud exposure to identify low-risk, high-value partners.

---

## Business KPIs

| Metric | Value |
|---|---|
| Total transactions analysed | 50,000 |
| Total transaction value | $3,525,694.67 |
| Average transaction amount | $70.51 |
| Median transaction amount | $47.66 |
| Unique customers | 932 |
| Unique merchants | 693 |
| Date range | Jan 2019 → Jun 2020 |

> The gap between mean ($70.51) and median ($47.66) indicates a right-skewed distribution — a small number of high-value transactions pull the average upward.

---

## Key Findings

### Spending Behaviour

| Theme | Finding |
|---|---|
| **Categories** | Grocery leads in both frequency (5,051 transactions) and average amount ($118), suggesting bulk purchasing habits. Travel is rare but ranks in the top 3 for average amount (~$94) |
| **Demographics — Gender** | No significant difference in average spending between men ($70.82) and women ($70.26). Men show a slightly higher median ($51–52 vs $45), suggesting women transact more frequently but at lower individual amounts |
| **Demographics — Profession** | Wide variation across professions (Homeopath: ~$1,100 vs lowest: ~$110). Results for rare professions should be interpreted with caution due to small sample sizes |
| **Time of day** | Volume peaks in the afternoon/evening; average amounts are highest overnight (10 PM–11 AM: $74–$83) — a consistent inverse relationship across all analyses |
| **Day of week** | U-shaped pattern: Monday (9,774) and Sunday (9,734) are the busiest; Wednesday is the quietest (4,990) |

### Merchant Fraud Risk Analysis

A three-tier merchant analysis was conducted to distinguish between raw volume and fraud-adjusted performance:

| View | Key Finding |
|---|---|
| **Global volume** | Top 10 merchants drive $12,500–$15,000 in total volume each. Raw volume alone is a misleading indicator of merchant health |
| **Legitimate volume** (is_fraud = 0) | Several top merchants drop out entirely when filtering to legitimate transactions only, revealing significant hidden fraud exposure. `fraud_Kilback LLC` maintains identical rankings in both views — confirming 100% legitimate volume |
| **Zero-fraud merchants** | A distinct group of merchants processes $11,000–$15,000 in volume with zero recorded fraudulent transactions — prime candidates for whitelisting and partnership programmes |

---

## Business Recommendations

- **Monitor overnight high-value transactions** — average amounts between 10 PM and 11 AM ($74–$83) suggest a distinct spending profile worth flagging for real-time fraud detection
- **Design category-based rewards** — grocery and travel show the highest average amounts and are strong cashback candidates
- **Implement a two-tier merchant scoring system** — a composite score (total volume + fraud rate) would enable more accurate risk assessment and preferential routing for verified zero-fraud partners
- **Whitelist zero-fraud, high-volume merchants** — ideal candidates for reduced friction in transaction approval flows and strategic partnership programmes
- **Time campaigns strategically** — Monday and Sunday see peak activity; optimal days for push notifications and promotional offers
- **Move beyond gender-based segmentation** — behavioural and temporal variables are more predictive for customer targeting

---

## Project Structure

```
credit-card-transactions-analysis/
│
├── analyse_transactions.ipynb   # Full analysis notebook
├── README.md                    # Project overview (this file)
└── requirements.txt             # Python dependencies
```

---

## Notebook Structure

1. Data Loading & Exploration
2. Data Cleaning & Preparation
3. Business KPIs Overview
4. Merchant Risk Analysis (Global / Legitimate / Zero-Fraud)
5. Spending Categories Analysis
6. Demographic Analysis (Gender & Profession)
7. Temporal Analysis (Hour of Day & Day of Week)
8. Summary
9. Limitations & Business Recommendations

---

## Tools & Libraries

| Tool | Use |
|---|---|
| Python | Core language |
| Pandas | Data manipulation, groupby, aggregation |
| Matplotlib | Data visualisation |
| Seaborn | Statistical graphics |

---

## Dataset

[Credit Card Transactions Dataset — Kaggle (priyamchoksi)](https://www.kaggle.com/datasets/priyamchoksi/credit-card-transactions-dataset)

- 1.85M transactions in full dataset
- Sample of 50,000 rows used for this analysis (`nrows=50000`)
- 23 columns including: transaction amount, category, merchant, gender, job, datetime, fraud flag (`is_fraud`)

---

## Limitations

- Sample-based analysis (2.7% of full dataset) — results are indicative rather than definitive
- Descriptive analysis only — no causal relationships established
- Key variables (income, age, account type) unavailable for deeper segmentation
- Profession-level results sensitive to sample size for underrepresented categories
- Future work could include predictive modelling, fraud detection models, or customer lifetime value analysis

---

## Author

**Rose Fidalgo Amorim**  
Applied Economics Student — IAE Vannes (Université Bretagne Sud)  

[LinkedIn](https://linkedin.com/in/) · [GitHub](https://github.com/)nes (Université Bretagne Sud)
