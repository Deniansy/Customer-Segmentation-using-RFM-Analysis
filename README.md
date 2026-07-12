# Customer Segmentation using RFM Analysis 🛍️

Segmenting 5,800+ customers of a UK-based global e-commerce retailer using **RFM Analysis (Recency, Frequency, Monetary)** to uncover who the most valuable customers are, who's about to churn, and which products drive the most revenue.

**Author:** [Deni Ansyah](https://www.linkedin.com/in/deni-ansyah) · [GitHub](https://github.com/Deniansy)

---

## 📋 Project Overview

**Online Retail II** is a UK-based e-commerce company serving customers globally. Between **December 2009 and December 2011**, the business attracted a large base of registered members — but as the customer base grew, so did the challenge of retaining existing customers, boosting loyalty, spotting revenue opportunities, and understanding each customer's purchasing behavior and preferences.

To address this, the company applies **RFM Analysis** to group customers into segments and design more targeted, effective marketing strategies.

## ❓ Business Questions

1. What is the total number of customers, transactions, and sales — and the average Recency, Frequency, and Monetary values?
2. How are customers distributed across segments, and which segment dominates?
3. Which customer segment contributes the most to the business based on total spending?
4. How does transaction frequency compare to total customer spending — is there a significant difference?
5. How do spending and purchase frequency trend over time — are they aligned?
6. Which products sell the most, generate the highest revenue, and sell in the highest quantity?

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Google Colab (Python) | Data cleaning, preprocessing, feature engineering |
| Power BI | RFM scoring, customer segmentation, interactive dashboard |
| Pandas, NumPy | Data manipulation |

## 📊 Dataset Overview

Dataset downloaded from **[Online Retail II UCI](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci/data)**.

| Column Name | Description |
|---|---|
| `Invoice` | Invoice number (transactions starting with "C" are cancellations) |
| `StockCode` | Product/item code |
| `Description` | Product name |
| `Quantity` | Quantity of each item per transaction |
| `InvoiceDate` | Date and time of the transaction |
| `Price` | Unit price of the product |
| `Customer ID` | Unique identifier for each customer |
| `Country` | Country where the customer is located |

- **Rows:** 1,067,371 transactions (before cleaning)
- **Period:** 1 December 2009 – 9 December 2011 (~2 years)

## 🧹 Data Preprocessing

| Step | Action |
|---|---|
| Missing Values | Dropped rows with missing values |
| Cancelled Transactions | Removed transactions with invoice numbers starting with "C" (cancelled orders) |
| Duplicates | Removed duplicate rows |
| Negative Values | Checked and handled negative values in `Quantity` and `Price` |
| Data Types | Corrected mismatched data types |
| Feature Engineering | Added `Total Price` column; converted `InvoiceDate` to datetime format |

**Result:** 1,067,371 rows / 8 columns → **805,620 rows / 9 columns** after cleaning.

## 🧮 Methodology: RFM Analysis

Each customer was scored on three dimensions, then combined into an RFM score used to assign a segment:

- **Recency (R)** – how recently a customer made a purchase
- **Frequency (F)** – how often a customer purchases
- **Monetary (M)** – how much a customer spends in total

Customers were grouped into 5 segments: **Champions, Loyal, At Risk, Potential, Uncategorized**.

## 📈 Key Results & Insights

### Overall Metrics
| Metric | Value |
|---|---|
| Total Customers | 5,881 |
| Total Transactions | 779,495 |
| Total Revenue | £17.37M |
| Avg. Frequency | 6.29 transactions/customer |
| Avg. Monetary | £2.95K/customer |

The business has a fairly large, engaged customer base with high-value average spending per customer.

### Customer Segmentation
| Segment | % of Customers | Customers | Total Spending | Transactions |
|---|---|---|---|---|
| At Risk | 39.87% (largest) | 2,350 | £2.2M | 112.8K |
| Champions | 22.85% | 1,340 | **£12.0M (highest)** | 490.0K |
| Loyal | 21.51% | 1,270 | £2.8M | 147.7K |
| Potential | 9.61% | 570 | £0.3M | 23.3K |
| Uncategorized | 6.16% | 360 | £0.1M | 5.7K |

- **At Risk** is the largest segment (39.87%) — customers who were previously active but haven't transacted in a long time, signaling high churn risk.
- **Champions** contribute the most revenue by far (£12.0M, ~69% of total spending) despite being only the 2nd largest group — the core of the business.
- **Loyal** customers show strong potential to be upgraded into Champions.
- Customer spending and purchase frequency trends move in tandem, with notable spikes in **early and mid-2011**.

### Product Performance
| Category | Top Product |
|---|---|
| Best-selling (by transactions) | White Hanging Heart T-Light (5.0K transactions) |
| Highest revenue | Regency Cakestand 3 Tier (£278K) |
| Highest quantity sold | World War 2 Gliders (105K units) |

- **White Hanging Heart T-Light** appears consistently across all top-10 categories — a stable, high-demand product.
- **World War 2 Gliders** sells the most units but isn't a top revenue earner — indicating a low unit price.
- **Regency Cakestand 3 Tier** has the highest revenue despite moderate sales volume — indicating a premium price point.
- Customers show a clear preference for decorative and gifting products (party/home decor items).

> 📌 *Add your Power BI dashboard screenshots here, e.g.:*
> `![Customer Segmentation Dashboard](assets/segmentation_dashboard.png)`

## ✍️ Recommendations

**Loyalty & Retention**
- Offer exclusive perks (discounts, cashback, early access) to Champions and Loyal customers.
- Implement a tiered loyalty program based on customer scoring — the higher the tier, the greater the benefit.

**Reactivating At-Risk Customers**
- Send personalized promotions, purchase reminders, or incentives to encourage them back.

**Product Optimization & Upselling**
- Use best-selling product data (e.g., White Hanging Heart T-Light) to power personalized recommendations and bundling.
- Upsell high-volume, low-price products like World War 2 Gliders toward higher-margin alternatives.

**Sharper Acquisition Campaigns**
- Use early-behavior data (low frequency, low monetary value) to build a lead-scoring model for new members.
- Run more aggressive welcome campaigns (bonuses, first-purchase discounts) to accelerate conversion into repeat buyers.

## 🔗 Related Links

- 📄 [Presentation Slides (PDF)](./PPT_FINAL_PROJECT_DATA_ANALYST.pdf)
- 📊 Full Power BI Dashboard *(add your link here)*
- 🔬 Google Colab Notebook *(add your link here)*
- 🌐 [My Portfolio Website](https://deniansy.github.io/portfolio/)
