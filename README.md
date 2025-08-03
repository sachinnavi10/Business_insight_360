# Business_insight_360

## Problem Statement :  
AtliQ Hardware, a leading consumer electronics company, operates globally with a diverse customer base, similar to well-known brands like HP and Dell. While AtliQ Hardware has been experiencing rapid growth, it has encountered challenges in the Latin American market. These challenges stem from their reliance on Excel files for data management. Excel, although versatile, presents difficulties in terms of data comprehension, visualization capabilities, and scalability. These limitations have led to significant losses in the Latin American market." To address this, our objective is to implement an advanced analytics solution to enable efficient data analysis and drive informed decision-making.

## Interactive Dashboard Link

Explore the live dashboard [here](https://app.powerbi.com/view?r=eyJrIjoiODZhZjM2M2EtODk5OS00YTEyLTg2MDgtMDliYTk5ZjgyOWIzIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9).

## Skills Learned

- Power BI data modeling
- DAX calculations
- Compelling visualization techniques
- Data interpretation
- Dashboard design principles
- User-centric design
- Stakeholder communication
- File size optimization using DAX Studio
- Data integration from various sources like Excel/CSV files, MySQL database, etc.

 ## Data Source Details :
Understanding what data is available will be more helpful while doing analysis. before jumping on to the analysis get good understanding of what are data available.

Dimension table : It will have the static data like details of customer and products

Fact table : It will have the data about the transactions

❇️ gdb041

      ⚫ dim_customer
            👉 27 distinct markets (ex India, USA, spain) 
            👉 75 distinct customers thorough out the market
            👉 2 types of platforms
                ▫️ Brick & Motors - Physical/offline store
                ▫️ E-commerce - Online Store (Amazon, flipkart)
            👉 Three channels
                ▫️ Retailer
                ▫️ Direct
                ▫️ Distributors
       ⚫ dim_market
            👉 27 distinct markets (ex India, USA, spain)
            👉 7 sub-zones
            👉 4 regions
                ▫️ APAC
                ▫️ EU
                ▫️ nan
                ▫️ LATAM
       ⚫ dim_product
            👉 Divisions
                 ◾ P & A
                     ▫️ Peripherals
                     ▫️ Accessories
                 ◾ PC
                     ▫️ Notebook
                     ▫️ Desktop
                 ◾ N & S
                     ▫️ Networking
                     ▫️ Storage
             👉 There are 14 different categories, Like Internal HDD, keyboard
             👉 There are different variants available for the same product
       ⚫ fact_forecast_monthly
             👉 This table is used to forecast the customer’s need in advance, which can help in 
                   ▫️ Higher customer satisfaction 
                   ▫️ Reduced cost in warehouses for storage purpose
             👉 The table is denormalized by data engineering team, as it is a data warehouse which is aimed to be used for analytical work.
             👉 All the date of the month will be replaced by the start date of the month
             👉 It will have all the column names and in the end it will have the forecast quantity need of the customer
       ⚫ fact_sales_monthly
             👉 This table is more or less is same as fact_forecase_monthly table, but the last column has the value of sold quantity instead of forecast value.
  ❇️ gdb056 
  
       ⚫ freight_cost
              This table has details of travel cost and other cost for each market with fiscal year
       ⚫ gross_price
             Has the details of gross prices with product code
       ⚫ manufacturing_cost
             Has the details of manufacturing cost with product code with year
       ⚫ Pre_invoice_dedutions
             Has the details of pre invoice deductions percentage for each cutomer with year
       ⚫ Post_invoice_deductions
             Post invoice deductions and other deductions details
 **Note** : Target values/Bench mark values were only given for 2022 fiscal year,only withrespective market column.


## Data Model :
   <img width="504" alt="Data Modelling Snap" src="https://github.com/kishanchand9989/Business-Insights-360/assets/86097586/51df038b-ab3d-4911-b942-78159dea6dfb">
   
   In this project, we have followed Snowfall data modeling method.

## Real-Time SQL Data Connection via Azure
- The Power BI dashboard was connected to a real-time SQL database using Azure.
- The backend SQL Server database was hosted on **Azure SQL Database**. Using **Power BI Gateway**, a direct connection was established to allow **live or scheduled refreshes** of data. This ensured that business users always had access to **up-to-date reports** on sales, forecasts, and operations without manual uploads.
- **Process**:
  - Azure SQL Database credentials were securely stored.
  - Power BI Service used an **On-Premises Data Gateway** for scheduled refresh.
  - Datasets in Power BI were configured for **daily refresh** or **DirectQuery** mode for real-time updates.

## Objective :
To Deploy an advanced analytics solution for AtliQ Hardware to enhance data analysis efficiency. which will offer comprehensive insights tailored to meet the needs of business leaders across various domains, such as  Sales, Finance, Marketing, Supply Chain, and Execution.

   ### **👉 Sales View**
   <img width="682" alt="Sales View Snap" src="https://github.com/kishanchand9989/Business-Insights-360/assets/86097586/55a828e4-ab3b-499b-9858-16d4655a9dfe">

     
  Decode customer and product performances influenced by Key metrics such as Net Sales and Gross Margin Percentage ,make an performance matrix b/w NS and Np % for 
  market, customer as values ,then explore the Break down for Needful P & L values of Sales View such as Net Sales , COGS , Gross Marigin.
   
  ### **👉 Finance View**
  <img width="699" alt="Finanace View Snap" src="https://github.com/kishanchand9989/Business-Insights-360/assets/86097586/45fd5905-8467-45c8-ac4b-1ba0c3ed3b0d">

  
Unveil an Profit and Loss Statements for financial performance across Markets Products,Customers and list down the Top and Bottom Products and Customer Net Sales

  ### **👉 Marketing View** 
  <img width="761" alt="Marketing Snap View" src="https://github.com/kishanchand9989/Business-Insights-360/assets/86097586/69672013-26cb-4944-a5fe-e4e309fdc29d">


Discover Region and market performances influenced by Key metrics such as NS,NS%,GM,GM% ,make an performance matrix b/w NS and GM % for segment, category as Values ,then explore the Break down of Needful P & L values for Marketing View such as Gross Marigin ,Operational Expenses  

  ### **👉 Supply Chain View** 
  <img width="572" alt="Supply Chain View Snap" src="https://github.com/kishanchand9989/Business-Insights-360/assets/86097586/446369fe-0b8e-4340-9ed3-ff652b392fcf">


Track the Customer and Product Key Metrics such as Forecast Accuracy,FA%,Net Error,NE%,ABS Error ,Also plot an Trendline over the Selected period of Net Error and Forecast Accuracy

  ### **👉 Execution View** 
  <img width="608" alt="Executive View Snap" src="https://github.com/kishanchand9989/Business-Insights-360/assets/86097586/26f1a100-a81c-4f1c-b387-cdb01a8e9696">


 Evaluating departmental performance at a glance by  plotting Yearly Trends of KPI’s (GM %,NP%, Market share%), Market Share Trends etc.., which enables business leaders 
 to bridge gap between strategy and results by closely monitoring and managing the execution of initiatives.

## Business Insights Derived from Business Insights 360 Power BI Project

### 1. Sales Drop in Latin America
- **Insight**: Monthly sales in Latin America dropped significantly in Q2.
- **Example**: In May and June, the dashboard showed sales fell by **25%** compared to Q1. This alerted the sales head to re-evaluate local distributors and adjust pricing.

### 2. High Freight Costs in Europe
- **Insight**: Supply chain freight cost was unusually high in the European market.
- **Example**: Freight expenses in the EU region were **₹2.5M higher** than APAC, despite lower sales volume. This led the logistics team to renegotiate vendor contracts.

### 3. APAC Market Outperforming
- **Insight**: APAC showed consistent growth in both revenue and forecast accuracy.
- **Example**: Forecast accuracy in APAC was **92%**, while LATAM was only **61%**. This helped top management shift marketing and inventory focus to APAC.

### 4. Poor Marketing ROI in LATAM
- **Insight**: Marketing campaigns in LATAM were ineffective.
- **Example**: In Q3, digital marketing spend was ₹3M, but the sales uplift was only ₹0.8M. The marketing team stopped the campaign and focused on email and referral programs instead.

### 5. High-Revenue, Low-Profit Products
- **Insight**: Some products had high sales but low profit margins.
- **Example**: "Gaming Mouse Pro X" had ₹10M revenue but only **5% profit margin**. The pricing and cost structure were re-evaluated.

### 6. Excess Inventory Due to Overforecasting
- **Insight**: Demand forecast was overestimated in LATAM.
- **Example**: The dashboard showed a **30% gap** between forecasted and actual sales. The supply team adjusted future orders to avoid storage losses.

### 7. Expense Spike in Finance
- **Insight**: Operating costs increased suddenly in Q2.
- **Example**: Total operating costs went up by ₹1.8M due to unplanned software license renewals. The finance team added alerts in their budget review process.

### 8. Top Performing Product
- **Insight**: Identified which products were top contributors to profit.
- **Example**: "Ultra HD Monitor Z" contributed ₹5M in profit with a **40% margin**. More marketing budget was allocated to this product.

## Conclusion :
The dashboard has equipped AtliQ Hardware with the capability to assess sales trends across different departments and make decisions guided by data. Moreover, a notable/significant trend on consistent rise in Atliq  market share, witnessing a substantial growth from its initial share of less than 0.5% to an impressive 5.9%. This encouraging trajectory highlights AtliqQ increasing presence and competitiveness in the market
