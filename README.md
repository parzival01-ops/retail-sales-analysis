# Online Retail Analytics Project

A full retail analytics project using Python, SQL, visualization, RFM segmentation, cohort retention analysis, and market basket analysis to uncover revenue patterns, customer behavior, retention trends, and product associations in the Online Retail II dataset.

This project takes raw transaction data and turns it into business insight through cleaning, structured querying, exploratory analysis, customer segmentation, retention analysis, and association rule mining.

---

## Project Overview

The goal of this project is to analyze customer transactions and answer questions such as:

- Which products generate the most revenue?
- Which countries contribute the most sales?
- How does revenue change over time?
- Which customers are the most valuable?
- How do customers behave over time after their first purchase?
- Which products are often bought together?

The project is designed to show the full workflow from raw data to actionable business insights.

---

## Dataset

The dataset used in this project is the **Online Retail II** dataset.

It contains invoice-level retail transactions with fields such as:

- Invoice
- StockCode
- Description
- Quantity
- InvoiceDate
- Price
- CustomerID
- Country

A cleaned version of the dataset is stored in the `data/processed/` folder and is used throughout the analysis.

---

## Project Structure

```text
D:.
│   README.md
│
├───.ipynb_checkpoints
│       01_download_data-checkpoint.ipynb
│
├───data
│   ├───output
│   │       cohort_retention_matrix.csv
│   │       market_basket_rules.csv
│   │       market_basket_strong_rules.csv
│   │       rfm_segment_summary.csv
│   │
│   ├───processed
│   │       online_retail_cleaned.csv
│   │       retail_analysis.db
│   │       rfm_customer_segments.csv
│   │
│   └───raw
│       └───online_retail_ii
│               online_retail_II.csv
│
└───notebooks
    │   01_download_and_clean_data.ipynb
    │   02_sqlite_queries.ipynb
    │   03_EDA_visualization.ipynb
    │   04_rfm_analysis.ipynb
    │   05_cohort_retention_analysis.ipynb
    │   06_market_basket_analysis.ipynb
    │
    └───.ipynb_checkpoints
```

---

## Workflow

### 1. Data download and cleaning
The raw retail dataset was downloaded, cleaned, and prepared for analysis.

Steps included:

- Standardizing column names
- Converting `InvoiceDate` to datetime
- Creating a `Revenue` column using `Quantity * Price`
- Checking missing values and data types
- Saving the cleaned dataset for later analysis

### 2. SQLite database analysis
The cleaned data was loaded into SQLite to support structured querying and business analysis.

SQL was used to explore:

- Top products by revenue
- Top customers by revenue
- Revenue by country
- Monthly revenue trends
- Customer concentration
- Product-level and basket-level patterns

### 3. Exploratory data analysis and visualization
EDA was used to identify major business trends in the data.

This included:

- Revenue by month
- Top products
- Top countries
- Customer concentration
- Average customer monthly revenue
- Revenue by customer segment
- Product pairing/co-occurrence analysis

### 4. RFM analysis
RFM segmentation was used to classify customers based on:

- **Recency**: how recently they purchased
- **Frequency**: how often they purchased
- **Monetary**: how much they spent

This helped identify different customer types such as:

- High-value customers
- Loyal repeat buyers
- Recent active customers
- Low-engagement or one-time buyers

RFM analysis adds a customer-value perspective to the project and helps show which segments matter most to the business.

### 5. Cohort retention analysis
Cohort analysis was used to study customer retention over time.

Customers were grouped by their first purchase period, and their behavior was tracked across later periods to understand:

- Retention patterns
- Repeat purchase behavior
- How customer activity changes over time
- Which cohorts stay active longer

This makes the project stronger because it does not just analyze who buys, but also how customers behave after their first transaction.

### 6. Market basket analysis
Market basket analysis was added to find products that are frequently purchased together.

Using Apriori and association rules, the project identified strong item pairings that may support:

- Cross-selling
- Product bundling
- Recommendation ideas
- Merchandising strategy

---

## Key Findings

Some of the main findings from the project include:

- The **United Kingdom** contributes the majority of revenue.
- A relatively small number of customers drive a large portion of total sales.
- Revenue changes over time, with visible monthly and seasonal variation.
- RFM segmentation reveals that customers differ widely in value and engagement.
- Cohort analysis shows how retention changes by acquisition period.
- Several product pairs have strong association rules, suggesting useful bundle opportunities.

---

## RFM Insights

RFM analysis helps identify customer groups based on value and behavior.

Typical segment patterns include:

- **VIP customers** with high purchase value and strong engagement.
- **Loyal customers** who buy repeatedly and contribute steady revenue.
- **Repeat customers** who purchase often but spend less than the top segment.
- **One-time customers** who contribute the least over time.

This is useful for:
- loyalty campaigns,
- reactivation strategies,
- retention efforts,
- targeted promotions.

---

## Cohort Insights

Cohort analysis helps reveal how customer retention changes over time.

The analysis can show:

- which acquisition cohorts retain better,
- when drop-off happens,
- whether customers keep coming back after their first purchase,
- and whether retention improves or weakens across time periods.

This is valuable for understanding long-term customer behavior rather than only first-purchase activity.

---

## Market Basket Results

The market basket analysis used:

- support
- confidence
- lift

Rules with higher lift were treated as stronger associations because they indicate products are bought together more often than expected by chance.

Examples of strong pairings included:

- Dolly Girl Lunch Box → Spaceboy Lunch Box
- Alarm Clock Bakelike Green → Alarm Clock Bakelike Red
- Sweetheart Ceramic Trinket Box → Strawberry Ceramic Trinket Box
- Lunch Bag Pink Polkadot → Lunch Bag Red Retrospot
- Wooden Picture Frame White Finish → Wooden Frame Antique White

These relationships can support bundling and cross-sell ideas.

---

## Output Files

The project produces the following outputs:

- `data/processed/online_retail_cleaned.csv`
- `data/processed/retail_analysis.db`
- `data/processed/rfm_customer_segments.csv`
- `data/output/rfm_segment_summary.csv`
- `data/output/cohort_retention_matrix.csv`
- `data/output/market_basket_rules.csv`
- `data/output/market_basket_strong_rules.csv`

---

## Tools Used

- Python
- Pandas
- NumPy
- SQLite
- Matplotlib
- Seaborn
- Plotly
- mlxtend
- Jupyter Notebook

---

## How to Run

1. Clone the repository.
2. Open the notebooks in Jupyter.
3. Run the notebooks in this order:

   - `01_download_and_clean_data.ipynb`
   - `02_sqlite_queries.ipynb`
   - `03_EDA_visualization.ipynb`
   - `04_rfm_analysis.ipynb`
   - `05_cohort_retention_analysis.ipynb`
   - `06_market_basket_analysis.ipynb`

4. Make sure the cleaned dataset exists in `data/processed/`.
5. Install the required packages if needed:

```bash
pip install pandas numpy matplotlib seaborn plotly mlxtend
```

---

## Notes

- The project is built around cleaned transaction-level retail data.
- RFM analysis and cohort analysis add a customer-focused layer to the project.
- Market basket analysis was run on the most frequent products to reduce noise and keep the rules meaningful.
- Some notebook outputs are exploratory and can be refined further for presentation.

---

## Future Improvements

Possible next steps for this project:

- Build an interactive dashboard in Power BI or Tableau
- Create a final presentation deck
- Add more visual explanation for RFM segments
- Add cohort retention heatmaps into the README
- Build product recommendation logic from association rules
- Add a summary report with business recommendations

---

## Conclusion

This project demonstrates a complete retail analytics workflow, from raw data cleaning to SQL analysis, EDA, customer segmentation, retention tracking, and market basket mining.

It shows not only what customers buy, but also how valuable they are, how long they stay active, and what products belong together.

The project is meant to be practical, readable, and useful as a portfolio piece.