# Power BI E-Commerce Sales Analytics Dashboard

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/91cb23c3-c81d-4870-a13d-331070c90374" /> 
</>

An interactive Power BI dashboard analyzing e-commerce sales performance, customer behavior, product demand, and geographic trends using the AdventureWorks retail dataset.

## Project Highlights:

- Hybrid Star + Snowflake data model

- Interactive executive KPI dashboard

- Drill-through navigation for product-level analysis

- Custom tooltip pages for contextual insights

- Row Level Security (RLS) for regional access control

- Price adjustment parameter simulation (what-if analysis)

- Multi-page business intelligence reporting dashboard


## Project Overview:

This project analyzes an **e-commerce retail dataset (AdventureWorks)** using Microsoft Power BI to generate business insights around sales performance, customer behavior, product demand, and geographic distribution.

The dashboard simulates how an **e-commerce organization monitors operational performance**, helping business stakeholders track revenue trends, identify high-performing products, analyze customer segments, and monitor return rates.

The report is designed to support **data-driven decision making through interactive visual analytics**.

## Business Problem:

E-commerce companies generate large volumes of transactional data across products, customers, and geographic regions. Business teams need a clear way to monitor sales performance, identify high-performing products, track return rates, and understand customer purchasing behavior.

Without structured analytics, it becomes difficult for decision-makers to quickly identify trends and take action.

## Analytical Approach:

To address this problem, a Power BI dashboard was developed using the AdventureWorks retail dataset.

The solution includes:

- A hybrid star + snowflake data model supporting scalable product hierarchy analysis

- DAX measures for calculating key business KPIs such as revenue, profit, orders, and return rate

- Interactive visualizations enabling drill-through analysis from summary dashboards to detailed product insights

- Custom tooltip pages for contextual category-level insights

- Row-Level Security (RLS) implementation to simulate regional data access control for enterprise reporting scenarios

## Outcome:

The dashboard enables stakeholders to:

- Monitor overall sales performance and profitability

- Identify top-performing products and categories

- Analyze customer purchasing patterns

- Understand regional sales distribution

- Detect high-return products requiring attention

This demonstrates how Power BI can transform raw transactional data into actionable business intelligence for e-commerce operations.

## Relevant Domain Experience

This project aligns with my professional experience working with large-scale **e-commerce catalog and operational datasets at Amazon**, where I analyzed product performance, returns, and marketplace data to support business decision-making.

## Business Context:

AdventureWorks is modeled as **a global e-commerce retailer** selling products such as bikes, accessories, and clothing across multiple regions.

Business users typically want answers to questions such as:

  - Which product categories generate the most revenue?

  - Which products have high return rates?

  - Which regions generate the highest order volume?

  - Who are the most valuable customers?

  - How are revenue and orders trending over time?

This dashboard provides an interactive environment to explore these questions.


## Tools & Technologies:

- Microsoft Power BI

- DAX (Data Analysis Expressions)

- Power Query

- Data Modeling

- Data Visualization


## Data Model:

**Schema Design:**

The dashboard is built using a **hybrid dimensional model combining Star Schema and Snowflake Schema**.

**Star Schema Components:**

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

**Snowflake Schema (Product Hierarchy):**

The product dimension is normalized into a hierarchical structure:

- Product Lookup
→ Product Subcategory
→ Product Category

This snowflake hierarchy enables scalable product categorization and category-level analysis.


### Data Model Diagram

<img width="1919" height="1018" alt="AW_Dashboard_Data_Model" src="https://github.com/user-attachments/assets/d1002c4a-b6c2-4905-914f-c582256e8832" />



## Key DAX Measures

**Total Revenue:**

```Total Revenue = SUMX('Sales Data','Sales Data'[OrderQuantity] * RELATED('Product Lookup'[ProductPrice]))```

Calculates total revenue generated from all sales transactions.

**Total Orders:**

```Total Orders = DISTINCTCOUNT('Sales Data'[OrderNumber])```

Counts the number of unique customer orders in the dataset.

**Total Cost:**

```Total Cost = SUMX('Sales Data','Sales Data'[OrderQuantity] * RELATED('Product Lookup'[ProductCost]))```

Calculates the total cost incurred for all products sold based on product cost and order quantities.

**Quantity Sold:**

```Quantity Sold = SUM('Sales Data'[OrderQuantity])```

Calculates the total number of product units sold across all sales transactions.

**Total Profit:**

```Total Profit = [Total Revenue] - [Total Cost]```

Measures overall business profitability.

**Return Rate:**

```Return Rate = DIVIDE([Quantity Returned],[Quantity Sold],"No Sales")```

Calculates the percentage of returned products relative to total orders.



## Key Business Metrics (KPIs):

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


## Dashboard Pages:

**1. Executive Dashboard**

Provides a **high-level overview of e-commerce performance**.

Key insights displayed:

- **Total Revenue:** $24.9M

- **Total Profit:** $10.5M

- **Total Orders:** 25.2K

- **Return Rate:** 2.2%

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


## Drill-Through Navigation:

The dashboard supports **context-based drill-through navigation** for deeper analysis.

Users can drill from the **Executive Dashboard’s Top Products table** to a dedicated **Product Detail page**.

**Workflow:**

Executive Dashboard
→ Top 10 Products
→ Drill Through
→ Product Detail Page

The product detail page automatically filters the report based on the selected product, allowing detailed analysis without cluttering the main dashboard.


## Custom Tooltip Pages:

The dashboard uses custom tooltip pages to provide additional contextual insights without cluttering the main visuals.

When users hover over the Orders by Category bar chart, a tooltip panel appears showing:

- Total Revenue

- Total Profit

- Total Orders

- Total Returns

- Return Rate

- Weekly Orders Trend

This tooltip is implemented using a **dedicated tooltip page**, allowing the dashboard to present **rich contextual insights while keeping the primary dashboard clean and focused.**

Custom tooltips improve the user experience by enabling **quick access to deeper insights through simple hover interactions**.

**How This Works (Technical Implementation)**

  1. A tooltip page was created in Power BI.

  2. Page type was configured as Tooltip.

  3. Visualizations were added to display key metrics and trends.

  4. The tooltip page was assigned to the Orders by Category visual.

This allows the tooltip to dynamically filter based on the category being hovered.


## Row Level Security (RLS):

Row-Level Security was implemented to restrict dashboard access based on **regional roles**.

Three roles were configured:

- **EU** → Access to Europe marketplace data

- **NA** → Access to North America marketplace data

- **Pacific** → Access to Asia-Pacific marketplace data

RLS rules were implemented using **DAX filters on the Territory dimension**, ensuring that users only see sales data relevant to their assigned region.

This simulates **enterprise-level data governance and secure reporting access**.


## Analytical Capabilities:

The dashboard enables analysis across multiple business dimensions:

- Product category performance

- Revenue and profit trends

- Regional sales distribution

- Customer segmentation

- Product return analysis

- Pricing impact on profitability

These insights help businesses optimize **inventory, pricing, and marketing strategies**.


## Business Insights:

Example insights derived from the dashboard:

- Accessories generate the highest order volume.

- Tires and Tubes are the most ordered product type.

- Shorts have the highest return rate among product categories.

- Revenue shows a strong upward trend during 2021–2022.

- A small group of customers contributes significantly to overall revenue.

These insights help guide **strategic product and sales decisions**.


## Skills Demonstrated:

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

## Screenshots:

**Executive Dashboard**

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/91cb23c3-c81d-4870-a13d-331070c90374" />

**Geographic Sales Analysis**

<img width="1919" height="1018" alt="image" src="https://github.com/user-attachments/assets/1bf28fd6-7f2d-44f6-b575-72950f928db6" />

**Product Detail Analysis**

<img width="1919" height="1018" alt="image" src="https://github.com/user-attachments/assets/a45abc9d-d0da-43c3-89c9-15f092986cec" />

**Customer Analysis**

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/8028a292-5248-4eff-9f6e-09280cce4c6b" />

**Data Model**

<img width="1919" height="1018" alt="AW_Dashboard_Data_Model" src="https://github.com/user-attachments/assets/d1002c4a-b6c2-4905-914f-c582256e8832" />

**Tooltip**

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/912856b5-f5b8-4a1c-8444-36b3668ad925" />


### Author

**Vishal K**

Data Analyst | SQL | Power BI | Business Intelligence

LinkedIn: www.linkedin.com/in/vishal-io

