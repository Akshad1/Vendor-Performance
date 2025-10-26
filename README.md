# Vendor Performance and Inventory Analysis

## 🎯 Executive Summary & Business Problem

Effective inventory and sales management are essential for retail and wholesale profitability. The goal of this analysis is to optimize operational efficiency by reducing losses, mitigating vendor dependency, and improving inventory turnover.

This project addresses the core business challenge of identifying inefficiencies across the supply chain by focusing on the following objectives:

* **Underperforming Brands:** Isolate brands that require promotional or pricing intervention.
* **Vendor Contribution:** Quantify the financial impact and risk associated with reliance on top suppliers.
* **Bulk Purchasing:** Analyze the financial benefits of large-quantity orders on unit cost savings.
* **Inventory Efficiency:** Identify vendors contributing to slow-moving inventory to optimize stock levels.
* **Profit Variance:** Investigate statistical differences in profitability between high- and low-performing vendor groups.

---

## 🛠️ Repository Architecture

This project follows a streamlined analytical pipeline:

| File / Folder                  | Purpose                                                                    | Status              |
|--------------------------------|-----------------------------------------------------------------------------|---------------------|
| **ingestion.ipynb**            | Data extraction, cleansing, and loading into a persistent SQL database (SQLite). | Core ETL            |
| **EDA.ipynb / EDA_visualization.ipynb** | Exploratory Data Analysis, statistical validation, and visualization of key insights. | Analysis Layer      |
| **Check For sales.ipynb**      | Ancillary notebook for specific sales and data integrity checks.            | Validation          |
| **data/**                      | Raw source files (excluded from version control).                           | Ignored             |
| **logs/**                      | Processing and ingestion logs (excluded from version control).               | Uploaded             |


🔒 Security Assurance

SECURITY NOTE: All sensitive database connection information has been censored from the committed files. Data access credentials rely on environment variables or local configuration files excluded via the .gitignore file.

🧹 Data Integrity and Preprocessing

Preprocessing was critical to ensuring the validity of derived insights. The data was subjected to rigorous filtration to exclude anomalous records:

Loss Mitigation: Records where Gross Profit $\le 0$ were excluded to focus on economically viable transactions.

Profitability Focus: Transactions with Profit Margin $\le 0$ were filtered out to concentrate the analysis on profitable sales.

Sales Validation: Inventory records where Total Sales Quantity $= 0$ were eliminated, focusing the dataset exclusively on items that have undergone the sales cycle.

Granular Value and Outlier Detection

The EDA confirmed the presence of significant variability and opportunities for process improvement:

Cost Variance: Freight Cost exhibited extreme volatility ($0.09$ to $257,032.07$), strongly suggesting inefficiencies in logistics, disparate bulk shipment costs, or erratic supplier pricing models.

Inventory Velocity: Stock Turnover varied widely ($0$ to $274.5$), confirming substantial capital tied up in slow-moving inventory.

Extreme Values: Outliers in Purchase and Actual Prices were detected, potentially indicating specialized or premium-tier product lines.

💡 Key Analytical Findings

1. Vendor Concentration and Risk Assessment

The analysis identified a significant concentration risk within the supply chain:

The top $10$ vendors account for $65.69\%$ of total purchases.

This pronounced reliance on a small number of suppliers introduces considerable vulnerability to supply chain disruptions or vendor-specific policy changes, necessitating a strategy for vendor diversification.

$$Placeholder: Vendor Contribution Chart$$

2. Impact of Volume Procurement on Cost

A strong correlation was established between order volume and unit cost savings:

Vendors procuring in large quantities secured a $72\%$ reduction in unit purchase price compared to smaller orders.

This underscores the value of maintaining bulk purchasing agreements to maximize profitability at the acquisition stage.

3. Inventory Efficiency and Capital Strain

Slow-moving inventory was quantified as a material financial burden:

The total unsold inventory capital identified was $2.71 Million.

This slow-moving inventory increases storage costs, diminishes cash flow, and directly impairs overall financial performance. Detailed vendor listings for low-turnover items enable targeted stock management interventions.

4. Statistical Validation: High vs. Low-Performing Vendors

Hypothesis testing confirmed that a statistically significant difference exists in the profit margins between top-selling (high-volume) and low-selling (high-margin) vendor groups.

Top-Performing Vendors (High Volume): Mean Profit Margin is $31.17\%$.

Low-Performing Vendors (High Margin): Mean Profit Margin is $41.55\%$.

This confirms that the groups operate under fundamentally distinct profitability models. Low-performing vendors maintain superior margins but suffer from insufficient sales penetration.

$$Placeholder: Profit Margin Comparison Chart$$

✅ Final Recommendations

Based on the quantitative findings, the following strategic actions are recommended to enhance operational efficiency and profitability:

Profitability Re-evaluation: Re-assess the pricing structure for high-margin, low-sales brands to aggressively boost sales volume without sacrificing the existing strong profitability.

Vendor Diversification: Actively seek and integrate new vendor partnerships to dilute over-reliance on the current top $10$ suppliers and mitigate supply chain risks.

Inventory Liquidation: Leverage clearance sales or revise storage strategies to optimize capital tied up in slow-moving inventory.

Marketing Enhancement: Implement focused marketing and distribution strategies for high-margin, low-performing vendors to drive sales volume and capture latent market share.

By implementing these data-driven recommendations, the organization can achieve sustainable profitability, mitigate vendor concentration risks, and substantially enhance operational efficiency
