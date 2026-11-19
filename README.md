# Customer Behaviour Analysis

End-to-end customer shopping behaviour analysis using **Python (EDA & cleaning)**, **PostgreSQL**, and **Power BI**, with findings presented in a Gamma deck.

**Presentation:** https://customer-shopping-behavi-qhi8rby.gamma.site/

## Dataset
- `data/raw/customer_shopping_behavior.csv`: 3,900 customer transactions, 18 columns (age, gender, item, category, purchase amount, location, season, review rating, subscription status, shipping type, discount applied, previous purchases, frequency of purchases, etc.).

## Tools
Python (Pandas, NumPy, Matplotlib, Seaborn), PostgreSQL (SQLAlchemy, psycopg2), Power BI, Gamma, Jupyter Notebook.

## Workflow
1. **Load & inspect**: checked structure, datatypes and missing values (37 missing review ratings).
2. **Clean & engineer features**: filled missing ratings with the category median, converted columns to snake_case, added `age_group` (quartiles) and `purchase_frequency_days`, dropped `promo_code_used` (identical to `discount_applied`).
3. **Load to PostgreSQL**: cleaned data written to a `customer` table.
4. **SQL analysis**: 10 business questions in `sql/SQL_Queries.sql` (revenue by gender, discount behaviour, subscriber spend, shipping, segmentation, top products per category, revenue by age group).
5. **Dashboard**: interactive Power BI report in `powerbi/`.

## Quick findings (from the raw data)
- Male customers generated about $157.9K in revenue vs about $75.2K from female customers.
- Subscribers spend about the same per order as non-subscribers ($59.49 vs $59.87); non-subscribers are 73% of customers.
- 43% of purchases used a discount.
- Clothing is the top category by revenue (about $104K).

## Project structure
```
├── data/raw/            raw CSV
├── notebooks/           Data_Analysis.ipynb
├── sql/                 SQL_Queries.sql
├── powerbi/             PowerBI_Dashboard.pbix
├── presentation/        Gamma link
└── images/              dashboard screenshots
```

## How to run
```bash
git clone https://github.com/bhuvaneshwari-99/Customer_Behaviour_Analysis.git
cd Customer_Behaviour_Analysis
pip install -r requirements.txt
export PG_PASSWORD=your_password   # for the PostgreSQL step
jupyter notebook notebooks/Data_Analysis.ipynb
```
Then run `sql/SQL_Queries.sql` against the `customer` table and open the `.pbix` in Power BI Desktop.

## Author
Bhuvaneshwari L · [LinkedIn](https://www.linkedin.com/in/bhuvaneshwaril/) · [GitHub](https://github.com/bhuvaneshwari-99) · lbhuvaneshwari729@gmail.com
