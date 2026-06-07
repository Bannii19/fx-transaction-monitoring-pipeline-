# Cross-Border FX Transaction Monitoring & Operational Analytics Pipeline 📈

## 📌 Project Overview
This repository contains an end-to-end data analytics solution designed to monitor retail foreign exchange (FX) transaction patterns, analyze branch-level volume velocity, and optimize operational cash processing workflows. 

By leveraging advanced SQL modeling and structured metrics, this pipeline transforms raw operational cash flows into actionable business intelligence to support profitability ranking and mitigate transactional risks.

---

## 🛠️ Business Problem & Core Objectives
In a fast-paced retail currency exchange environment, management requires a unified mechanism to evaluate branch productivity, protect margins, and identify sudden operational spikes. 

The core objectives of this analytics script are:
1. **Performance Tracking:** Dynamically rank operational branch performance by overall profitability rather than just raw transaction volume.
2. **Operational Risk Management:** Monitor transaction velocity using rolling hourly windows to identify sudden processing surges and support branch compliance frameworks.

---

## 💻 Tech Stack & Methodologies
* **Database Engine:** SQL (PostgreSQL / MySQL compatible)
* **Analytical Techniques:** Common Table Expressions (CTEs), Window Functions (`DENSE_RANK()`, `AVG() OVER()`), Data Aggregations, Data Partitions, and Rolling Time-Window Functions.

---

## 📊 Logic & Breakdown of the SQL Analysis
The project code is hosted in `branch_analysis.sql` and follows a structured pipeline:

* **Transaction Base Modeling (CTE):** Isolates individual transaction values, fees, and calculated retail margins to arrive at true gross revenue per order.
* **Profitability Window Ranking:** Implements a `DENSE_RANK()` window function partitioned across branch outputs. This ensures that the top revenue-generating branch is systematically identified as Rank 1.
* **Velocity Surge Monitor:** Deploys a rolling 3-hour average calculation (`ROWS BETWEEN 2 PRECEDING AND CURRENT ROW`) to pinpoint operational bottlenecks or sudden transaction spikes that require automated compliance checks or liquidity allocation.

---

## 🚀 Key Business Insights Generated
* **True Value vs. Volume:** Successfully highlights instances where high-volume branches are out-performed in true revenue by lower-volume, higher-margin transaction corridors.
* **Proactive Liquidity Planning:** Rolling average thresholds allow corporate headquarters to forecast real-time cash demands across regional hubs.
