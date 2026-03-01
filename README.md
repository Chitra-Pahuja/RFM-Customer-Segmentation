# RFM Customer Segmentation

Segmenting 540K+ online retail transactions into actionable customer groups using **RFM (Recency, Frequency, Monetary) analysis** and **K-Means clustering** — identifying VIP customers, loyal buyers, at-risk churners, and growth opportunities.

![Python](https://img.shields.io/badge/Python-3.10-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-KMeans-orange)
![Status](https://img.shields.io/badge/Status-Complete-green)

---

3D Cluster Plot <img width="586" height="582" alt="cluster_3d" src="https://github.com/user-attachments/assets/92024528-6207-4f12-a318-01dd435e2269" />


RFM Heatmap <img width="665" height="550" alt="rfm_heatmap" src="https://github.com/user-attachments/assets/9265e2e2-89d2-4dd6-9b6f-1dd6ff846d20" />

---

## Key Findings

- **4 distinct customer segments** identified with clear behavioral differences
- A small group of VIP customers (~top quartile) drives the majority of total revenue
- **Frequency and Monetary are strongly correlated (0.57)** — customers who buy more often also spend more
- Recency is negatively correlated with both metrics, confirming that inactive customers tend to be low-value
- Peak ordering activity: **mid-week** (Thursday highest) and **late morning hours** (10am–1pm)
- The UK dominates order volume, with Germany, France, EIRE, and Belgium as secondary markets

## Segments Overview

| Cluster | Label | Profile | Recommended Strategy |
|---------|-------|---------|---------------------|
| 0 | **VIP / Champions** | Recent, frequent, high spend | Exclusive perks, early access, personalized offers |
| 1 | **Loyal Customers** | Moderate recency & frequency | Loyalty rewards, upsell/cross-sell, referral programs |
| 2 | **At-Risk / Churning** | High recency, low activity | Win-back campaigns, "We miss you" offers, feedback surveys |
| 3 | **New / Potential** | Recent but low frequency | Welcome sequences, bundles, retargeting ads |

## Dataset

[UCI Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail) — 541,909 transactions from a UK-based online retailer (Dec 2010 – Dec 2011).

**Features:** InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country

## Methodology

1. **Data Cleaning** — Removed missing CustomerIDs, duplicates, and engineered `TotalPrice`
2. **RFM Calculation** — Computed Recency, Frequency, and Monetary for each customer
3. **Quartile Scoring** — Assigned 1–4 scores for each RFM metric
4. **K-Means Clustering** — Used Elbow Method to determine optimal k=4, applied StandardScaler + KMeans
5. **Segment Profiling** — Analyzed cluster characteristics and developed marketing strategies
6. **Extended Analysis** — Time patterns, geography, product performance, returns, customer behavior

## Visualizations

The notebook includes:
- RFM distribution histograms and boxplots by cluster
- Elbow method curve for optimal k selection
- 2D and 3D cluster scatter plots
- RFM correlation heatmap and score heatmap
- Radar charts comparing cluster profiles
- Time-based ordering patterns (day, hour, month)
- Geographic and product-level analysis

## Tech Stack

- **Python** — Pandas, NumPy
- **Visualization** — Matplotlib, Seaborn
- **Machine Learning** — scikit-learn (KMeans, StandardScaler)
- **Environment** — Jupyter Notebook

## How to Run

```bash
git clone https://github.com/YOUR_USERNAME/rfm-customer-segmentation.git
cd rfm-customer-segmentation
pip install -r requirements.txt
jupyter notebook customer_segmentation.ipynb
```

## Project Structure

```
rfm-customer-segmentation/
├── README.md
├── requirements.txt
├── .gitignore
├── data.csv
└── customer_segmentation.ipynb
```

## Potential Extensions

- Customer Lifetime Value (CLV) modeling
- Predictive churn analysis using time-series RFM trends
- DBSCAN / Hierarchical clustering comparison
- Real-time segmentation dashboard (Tableau / Streamlit)
