Online Retail — Customer Segmentation with RFM & Clustering

Businesses across the world are growing rapidly. With technology, they can reach wider markets and serve larger customer bases. Customer segmentation—grouping customers with similar characteristics—helps teams understand behavior and tailor strategies for impact.

Notebook: Online_Retail_Customer_Segmentation.ipynb

🧩 Problem Description

Identify the major customer segments from a transnational dataset covering 01/12/2010–09/12/2011 for a UK-based, non-store online retail selling unique all-occasion gifts. Many customers are wholesalers. The analysis builds an RFM model and applies unsupervised clustering to discover actionable groups.

💡 Why Customer Segmentation?

Differences in behavior, demographics, and geography enable meaningful grouping. Understanding segments helps with:

Target marketing

Client understanding

Optimal product placement

Revenue growth

📐 RFM Model (Recency–Frequency–Monetary)

The RFM model is ideal when only transaction data is available:

Recency – How recently did the customer purchase?

Frequency – How often do they purchase?

Monetary – How much do they spend?

Combining these attributes quantifies customer value.
Example: A customer who bought recently, buys often, and spends more is a high-value customer.

🔭 Approach

Data inspection (shape, types, nulls, duplicates)

EDA (top products, countries, time trends)

Data preparation

Drop missing Description and CustomerID

Remove returns (InvoiceNo containing “C”)

Feature engineering: Month, Day, Hour, TotalAmount

Log transforms for R/F/M; standardization

Create RFM model

Recency = Latest_Date – last purchase date

Quartile-based scoring for R, F, M; RFMGroup, RFMScore

Clustering & validation

K-Means (Silhouette & Elbow)

DBSCAN

Agglomerative (Ward linkage)

✅ Conclusions & Insights

Descriptive Analysis

Missing values (notably CustomerID) and duplicates addressed.

Majority of purchases from the United Kingdom.

Peak purchase days: Thursday, Wednesday, Tuesday.

Peak months: November, October, December; lowest: April, January, February.

Peak time of day: Afternoon.

Segmentation Results

Customers segmented using RFM features.

K-Means (Silhouette & Elbow) on RFM favors k = 2 clusters overall.

Cluster 1 (Best/Loyal): low recency, high frequency, high monetary

Cluster 0 (At-risk/Low value): higher recency, lower frequency/monetary

DBSCAN surfaced an alternative 3-cluster view (denser core + sparse groups).

Depending on business preference for granularity, both 2-cluster (clean split) and 3-cluster (finer segmentation) strategies are defensible.

Business Actions

Best/Loyal: loyalty perks, early access, cross-sell/up-sell bundles.

At-risk/Low value: re-engagement emails, time-bound offers, win-back campaigns.

(Optional) 3rd segment from DBSCAN: targeted nudges to convert “promising” customers into best.
