# ConnectaTel Customer Behavior Analysis

## 📌 Context
As a data analyst, the goal is to evaluate the behavior of customers at ConnectaTel, a telecommunications company operating in Latin America, using data recorded through 2024. The analysis explores customer demographics, plan usage, and churn to build a statistical customer profile, detect atypical behaviors, and support retention strategy.

## 🎯 Objective
- Build a clean, unified customer usage profile
- Identify data quality issues and resolve them with clear, justified decisions
- Segment customers by usage level and age
- Translate findings into actionable retention and product recommendations

## 🗂️ Data
- **plans.csv** — plan pricing, included minutes/GB, and overage costs
- **users.csv** — customer demographics, registration date, plan, and churn status
- **usage.csv** — call and message activity detail
- **Coverage:** ~4,000 customers, 40,000 usage records, Latin America, through 2024

## 🛠️ Tools
Python · Pandas · NumPy · Seaborn · Matplotlib · Jupyter Notebook

## 🔍 Methodology
1. Data quality assessment: identified missing values, sentinel values (age = -999, city = "?"), and an impossible registration year (2026)
2. Confirmed that missing values in `duration`/`length` were Missing At Random (MAR), driven by the `type` column, and kept accordingly
3. Cleaned and standardized all three datasets, converting date columns and correcting sentinels
4. Aggregated usage data by customer (total calls, messages, call minutes) and merged with customer demographics
5. Explored distributions and outliers via histograms and boxplots, validated with the IQR method
6. Segmented customers into usage groups (Low/Medium/High) and age groups (Young/Adult/Senior)
7. Delivered an executive summary with data quality findings, segment behavior, and business recommendations

## 📊 Key Findings
- No plan type shows a strong correlation with message, call, or minute usage — customers across both plans use the service similarly
- The customer base peaks in the 43–48 age range; Adults (30–60) are the largest overall segment
- **Notable pattern:** Premium plan adoption rises sharply among customers over 73 — a segment worth targeted marketing investigation
- Outliers in usage metrics (especially call minutes) reflect real heavy-user behavior rather than data errors, and are relevant to fraud/anomaly monitoring
- Most customers fall into the Medium usage group; High usage customers are the smallest segment

## 💡 Recommendations
- **Shift focus beyond calls/messages** — invest in added value (support, coverage, connectivity) since most customers already have ample allowance
- **Investigate the Young-to-Adult drop-off** in customer numbers over time
- **Build loyalty programs for the Young segment** to capitalize on their early interest in Premium
- **Design targeted minute packages** for high-usage Basic customers not ready to upgrade to Premium
- **Launch Premium marketing campaigns aimed at Seniors**, given the sharp adoption increase after age 70

## 📁 Repository Structure
```
├── connectatel_customer_analysis.ipynb   # Full analysis notebook
├── images/                                # Chart exports
│   ├── age_distribution_by_plan.png
│   ├── message_count_distribution.png
│   ├── call_count_distribution.png
│   ├── call_minutes_distribution.png
│   ├── boxplot_01.png
│   ├── boxplot_02.png
│   ├── boxplot_03.png
│   ├── boxplot_04.png
│   ├── usage_group_distribution.png
│   ├── age_group_distribution.png
│   └── age_vs_usage_group.png
└── README.md
```
