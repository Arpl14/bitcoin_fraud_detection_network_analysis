# 📊 Trust Dynamics & Fraud Detection in Bitcoin OTC Network

**Author:** Arpita Lonakadi  
**Email:** arlona@iu.edu  
**Date:** 11/03/2024  

---

## 🧾 Overview

In decentralized platforms like Bitcoin OTC, where users remain anonymous and transactions are irreversible, trust becomes a critical factor in ensuring safe peer-to-peer trading. Bitcoin OTC allows users to rate each other on a scale from -10 (distrust) to +10 (trust), forming a directed, weighted trust network. Analyzing this network helps uncover patterns of trust, detect suspicious behavior, and identify influential users or hidden communities. By applying network science and sentiment analysis, we can enhance reputation systems, detect potential fraud early, and ultimately make digital financial ecosystems like Bitcoin OTC more secure and trustworthy.

---

## 📂 Dataset Summary

- **Nodes (Users):** 5,881  
- **Edges (Ratings):** 35,592  
- **Edge Weights:** -10 (distrust) to +10 (trust)  
- **Positive Ratings:** 89%  
- **Format:** SOURCE, TARGET, RATING, TIME  

---

## ✅ Key Analysis Steps & Results

### 1. 🧹 Data Preprocessing & EDA
- Converted timestamps and split into date/time fields.
- **Exploratory Data Analysis** revealed:
  - Skewed distribution with majority **positive trust ratings**.
  - Temporal trends show **monthly fluctuations** in rating behavior.
  - Rating frequency centered around a few influential users.

---

### 2. 🌐 Network Construction
- Constructed a **directed, weighted graph** using NetworkX.
- **Network Density:** `0.001` → Sparse connectivity  
- **Clustering Coefficient:** `0.1775` → Moderate clustering  
- **Avg In/Out Degree:** ~6.05 → Balanced connections  

> **Insight:** Trust is clustered within groups; the network has isolated regions and central hubs.

---

### 3. 🧠 Centrality & Influence Metrics
- **In-Degree** & **Out-Degree** used to identify users receiving/giving the most trust.
- **PageRank** applied to detect influential users.

> Influential nodes emerged as central hubs in user interaction and trust formation.

---

### 4. 🧩 Community Detection
- Used **Louvain Method** to identify clusters of tightly-connected users.
- **Detected:** `371 distinct communities`

> These communities represent **trust-based sub-networks**, with many users interacting more within clusters than across them.

---

### 5. 💬 Sentiment & Reciprocity Analysis
- **Sentiment Ratio:** 0.90 → Network shows overall positive sentiment.
- **Reciprocity Ratio:** 0.76 → High mutual trust in the network.

> Nodes with consistently high or low trust ratings were flagged for further review.

---

### 6. 🚨 Fraud Detection
Used multiple heuristics to detect suspicious behavior:
- **Frequent extreme raters** (-10 or +10 repeatedly)
- **Users with both high and low trust connections**
- **Users with significant trust score changes over time**
- **Non-reciprocal trust relationships**

> Visualizations highlighted users with abnormal trust patterns and flagged 250+ accounts as suspicious.

---

## 🔧 Techniques Used

- Python, Pandas, NetworkX, Matplotlib, Seaborn  
- Centrality Metrics: In/Out-Degree, PageRank  
- Clustering: Average Clustering Coefficient  
- Community Detection: Louvain Algorithm  
- Link Prediction: Jaccard Coefficient  
- Sentiment Metrics: Trust Distribution, Reciprocity Ratio  
- Fraud Detection: Behavior-based heuristics (volatility, extremes, non-reciprocity)

---

## 🧠 Conclusion

This study demonstrates how **network analysis** and **trust dynamics** can be leveraged to uncover **fraudulent behavior** and **user influence** in decentralized platforms.  
Key findings:
- Majority of the network expresses positive trust.
- Trust tends to be **reciprocal** and **clustered**.
- **Sentiment trends and abrupt behavior shifts** are early indicators of fraud.

This approach can be adapted for fraud detection in other **anonymous and trust-based digital ecosystems**.

---# bitcoin_fraud_detection_network_analysis
