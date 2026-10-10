# Data Mining Projects

Two projects from the Data Mining module of my MSc Data Science at the University of East Anglia (2026). Both are written up as full reports in this repository.

## 1. Customer Service Escalation Risk Analytics

**Report:** [customer_escalation_risk_report.pdf](customer_escalation_risk_report.pdf) (Python code is in the appendix)

**Question:** which customer service interactions are likely to escalate, and what do high-risk cases have in common?

**Data:** 12,362 customer service interactions across phone, chat, email and in-app messaging.

**What I did**

- Removed 122 duplicate records, treated outliers and filled missing values.
- Engineered nine extra features, giving 47 features in total.
- Trained and tuned five classifiers: Decision Tree, k-NN, Random Forest, XGBoost and LightGBM.
- Grouped customers with K-Means and Agglomerative clustering.

**What I found**

| Model | Macro F1 |
|---|---|
| XGBoost | 0.999 |
| LightGBM | 0.996 |
| Decision Tree | 0.989 |
| Random Forest | 0.987 |
| k-NN | 0.774 |

- The tree-based scores were too good to be true. One feature, the post-interaction quality score, is only known after the interaction ends, so it leaks the answer. I flagged it and reported k-NN's Macro F1 of 0.77 as the realistic figure.
- K-Means found a high-risk group with 21% longer wait times and more negative sentiment.

**Tools:** Python, pandas, scikit-learn, XGBoost, LightGBM, Matplotlib, Seaborn

## 2. Supermarket Queue Time and Customer Satisfaction

**Report:** [supermarket_queue_analysis_report.pdf](supermarket_queue_analysis_report.pdf)

**Question:** do longer queues make customers less satisfied, and where and when are queues worst?

**Data:** about 5,000 customer survey records from five Norfolk supermarkets.

**What I did**

- Cleaned impossible values (a recorded wait of 9,920 minutes, ages over 100) and fixed misspelt store names and categories.
- Capped extreme queue times at 60 minutes instead of deleting them, leaving 4,674 records.

**What I found**

- Longer queues go with lower satisfaction (r = -0.49). Queue time alone explains about 24% of the variation in satisfaction.
- Customers who waited over 20 minutes scored 1.95 out of 5 on average.
- Thetford and Wymondham had the longest queues; mornings were the slowest time of day.

**Tools:** Python, pandas

## About

Garapati Nandala Harsha, MSc Data Science, University of East Anglia. [LinkedIn](https://www.linkedin.com/in/garapati-nandala-harsha)
