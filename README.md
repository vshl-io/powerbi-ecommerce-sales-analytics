# AdventureWorks-PowerBI-Dashboard

**Project Overview:**

This project analyzes an **e-commerce retail dataset (AdventureWorks)** using Microsoft Power BI to generate business insights around sales performance, customer behavior, product demand, and geographic distribution.

The dashboard simulates how an **e-commerce organization monitors operational performance**, helping business stakeholders track revenue trends, identify high-performing products, analyze customer segments, and monitor return rates.

The report is designed to support **data-driven decision making through interactive visual analytics**.

**Business Context:**

AdventureWorks is modeled as **a global e-commerce retailer** selling products such as bikes, accessories, and clothing across multiple regions.

Business users typically want answers to questions such as:

  - Which product categories generate the most revenue?

  - Which products have high return rates?

  - Which regions generate the highest order volume?

  - Who are the most valuable customers?

  - How are revenue and orders trending over time?

This dashboard provides an interactive environment to explore these questions.

**Tools & Technologies:**

- Microsoft Power BI

- DAX (Data Analysis Expressions)

- Power Query

- Data Modeling

- Data Visualization

**Data Model:**

**Schema Design**

The dashboard is built using a **hybrid dimensional model combining Star Schema and Snowflake Schema**.

**Star Schema Components**

The model contains two main **fact tables**:

**Sales Data**

- Stores transactional sales records

- Includes order quantity and price metrics

- Connected to product, customer, territory, and calendar dimensions

**Returns Data**

- Tracks product returns

- Used to calculate return rates and product quality indicators

**Dimension Tables**

- Customer Lookup

- Product Lookup

- Territory Lookup

- Calendar Lookup

These dimensions allow analysis across time, customer segments, product attributes, and geographic regions.

**Snowflake Schema (Product Hierarchy)**

The product dimension is normalized into a hierarchical structure:

- Product Lookup
→ Product Subcategory
→ Product Category

This snowflake hierarchy enables scalable product categorization and category-level analysis.

**Data Model Diagram**

<img width="1919" height="1018" alt="AW_Dashboard_Data_Model" src="https://github.com/user-attachments/assets/d1002c4a-b6c2-4905-914f-c582256e8832" />

**Key Business Metrics (KPIs):**

The dashboard tracks several important **e-commerce performance indicators**:

- Total Revenue

- Total Profit

- Total Orders

- Return Rate

- Revenue per Customer

- Unique Customers

- Monthly Revenue Trend

- Monthly Orders

- Monthly Returns

- Top Products by Revenue

- Orders by Category

These KPIs allow stakeholders to quickly monitor business performance.

**Dashboard Pages:**
**1. Executive Dashboard**

Provides a **high-level overview of e-commerce performance**.

Key insights displayed:

- Total Revenue: $24.9M

- Total Profit: $10.5M

- Total Orders: 25.2K

- Return Rate: 2.2%

Other visualizations include:

- Revenue trend over time

- Orders by product category

- Top 10 products by revenue

- Monthly order and return trends

This page enables executives to quickly assess overall business health.

**2. Geographic Sales Analysis**

This page visualizes **global sales distribution using map visualizations**.

Key capabilities:

Sales distribution across **North America, Europe, and Pacific regions**

Interactive filtering by region

Order volume comparison between countries

This helps businesses identify **regional demand patterns and market opportunities**.

**3. Product Performance Analysis**

This page analyzes **product-level performance and pricing impact**.

Key features include:

- Monthly orders vs target

- Monthly revenue vs target

- Monthly profit vs target

- Product profitability trends

Price adjustment simulation using parameter control

This helps evaluate **product profitability and pricing strategy impact**.

**4. Customer Analysis**

Provides insights into **customer purchasing behavior and segmentation**.

Key insights include:

- Total Unique Customers: 17.4K

- Revenue per Customer

- Top 100 Customers by Revenue

- Orders by Income Level

- Orders by Occupation

This helps businesses identify **high-value customer segments**.

**Drill-Through Navigation:**

The dashboard supports **context-based drill-through navigation** for deeper analysis.

Users can drill from the **Executive Dashboard’s Top Products table** to a dedicated **Product Detail page**.

**Workflow**

Executive Dashboard
→ Top 10 Products
→ Drill Through
→ Product Detail Page

The product detail page automatically filters the report based on the selected product, allowing detailed analysis without cluttering the main dashboard.

**Row Level Security (RLS):**

Row-Level Security was implemented to restrict dashboard access based on **regional roles**.

Three roles were configured:

- **EU** → Access to Europe marketplace data

- **NA** → Access to North America marketplace data

- **Pacific** → Access to Asia-Pacific marketplace data

RLS rules were implemented using **DAX filters on the Territory dimension**, ensuring that users only see sales data relevant to their assigned region.

This simulates **enterprise-level data governance and secure reporting access**.

**Analytical Capabilities:**

The dashboard enables analysis across multiple business dimensions:

- Product category performance

- Revenue and profit trends

- Regional sales distribution

- Customer segmentation

- Product return analysis

- Pricing impact on profitability

These insights help businesses optimize **inventory, pricing, and marketing strategies**.

**Business Insights:**

Example insights derived from the dashboard:

- Accessories generate the highest order volume.

- Tires and Tubes are the most ordered product type.

- Shorts have the highest return rate among product categories.

- Revenue shows a strong upward trend during 2021–2022.

- A small group of customers contributes significantly to overall revenue.

These insights help guide **strategic product and sales decisions**.

**Skills Demonstrated:**

This project demonstrates the following analytical and BI skills:

- Data modeling (Star + Snowflake schema)

- DAX calculations for business metrics

- Interactive dashboard design

- Drill-through navigation

- Row-Level Security implementation

- E-commerce analytics

- Customer segmentation analysis

- Geographic data visualization

- Business KPI tracking
