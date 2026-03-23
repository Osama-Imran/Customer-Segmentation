Here you go!

---

# Customer Segmentation Using KMeans Clustering

## Overview
This project applies unsupervised machine learning to group mall customers into distinct segments based on their purchasing behavior. By identifying patterns in the data, businesses can tailor marketing strategies for each customer group.

---

## Dataset
**Source:** Mall Customers Dataset (Kaggle)
**Records:** 200 customers
**Features:** CustomerID, Gender, Age, Annual Income (k$), Spending Score (1-100)

---

## Project Steps

**1. Data Loading & Exploration**
Explored the dataset structure, checked for null values (none found), and examined data types.

**2. Preprocessing**
- Dropped `CustomerID` — no predictive value
- Label Encoded `Gender` (Male/Female → 1/0)
- Applied `StandardScaler` to normalize all features — essential for KMeans since it is distance-based

**3. Finding Optimal K — Elbow Method**
Trained KMeans for K=1 to K=10 and plotted inertia values. The elbow curve clearly bent at **K=5**, indicating 5 as the optimal number of clusters.

**4. Training KMeans**
Trained the final model with `n_clusters=5` and `random_state=42` for reproducibility. Cluster labels were assigned back to the original dataframe.

**5. Visualization**
Plotted clusters using Annual Income vs Spending Score scatter plot, revealing 5 clearly separated and visually distinct customer groups.

**6. Cluster Analysis**
Analyzed each cluster's average Age, Income, and Spending Score to build meaningful customer profiles.

---

## Customer Segments Identified

| Cluster | Avg Age | Avg Income | Avg Spending | Profile |
|---|---|---|---|---|
| 🔴 0 | 32.7 | $86.5k | 82.1 | Young High Earners, Big Spenders |
| 🔵 1 | 36.5 | $89.5k | 18.0 | High Earners, Low Spenders |
| 🟢 2 | 49.8 | $49.2k | 40.1 | Middle Aged, Average Customers |
| 🟡 3 | 24.9 | $39.7k | 61.2 | Young Low Earners, High Spenders |
| 🟣 4 | 55.7 | $53.7k | 36.8 | Older, Conservative Spenders |

---

## Key Insights
- **Age drives spending behavior** — younger customers spend more regardless of income level
- **Cluster 0 vs Cluster 1** — nearly identical age and income but completely opposite spending habits, showing that income alone doesn't predict spending
- **Cluster 3** — lowest income yet high spending, suggesting impulse or lifestyle driven purchases
- **Cluster 4** — oldest group and most conservative spenders, likely more financially cautious

---

## Business Recommendations
- **Cluster 1** — highest priority for targeted promotions, they have the income but need engagement
- **Cluster 0** — reward and retain with loyalty programs, they are your best customers
- **Cluster 3** — engage carefully, high spenders but financially stretched

---

## Libraries Used
- `pandas` — data manipulation
- `numpy` — numerical operations
- `matplotlib` — visualization
- `scikit-learn` — preprocessing and KMeans clustering

---

## How to Run
1. Download `Mall_Customers.csv` from Kaggle
2. Upload to Google Colab
3. Run notebook cells in order
4. Scatter plot and cluster profiles will be generated at the end
