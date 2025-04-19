# Sports Product Tracker - Power BI Report 

![Power BI Report - Home View](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/Power-BI-report-H.jpg)

## Problem Statement

Stakeholders across various departments currently lack a centralized, data-driven view to effectively monitor and analyze sports product performance across different categories, regions, time periods, and sales channels. This data gap makes it difficult to identify underperforming product lines, evaluate sales volumes and return rates, and make informed decisions based on critical indicators such as total orders, revenue, operational costs, return percentages, and profitability metrics. There is a clear need for an interactive dashboard that provides actionable insights across key sales, operational, and financial dimensions.

The dashboard delivers data-driven insights to uncover sales trends, identify cost and revenue leakages, optimize inventory and distribution strategies, and maximize sales efficiency and profitability. It empowers key stakeholders with an interactive view to monitor product performance, assess historical and current margin trends, track return rates and revenue generation, and make data-backed decisions with a clear understanding of cost drivers and product dynamics.

This dashboard enables stakeholders to track and analyze sports product performance and profitability based on parameters such as:

- Product Category, Product ID, Region
- Time Frame: Year, Month, Quarter

- Product Type and Subcategory

- Sales Metrics: Total Orders, Monthly Orders, Units Sold, Return Volume

- Revenue Metrics: Monthly Revenue, Campaign Revenue, Channel Contributions, Total Product Revenue

- Cost Metrics: Manufacturing Costs, Shipping, Warehousing, Marketing Spend, Returns - Processing, Discounts, and Total Cost

- Profitability Metrics: Gross Profit, Gross Profit %, Net Profit, Margin Ranges

- Performance Metrics: Return Rate %, Sales Growth, Stock Turnover, Delivery Performance 

The dashboard will be extremely helpful to multiple stakeholders including: 

- E-commerce & Digital Sales Managers
 
- Marketing & Campaign Teams
 
- Product & Inventory Analysts
 
- Sales Strategists & Finance Teams

# Objective

`Establish a Centralized Dashboard`
Develop a comprehensive and interactive dashboard to provide a unified, real-time view of sports product performance across categories, regions, time periods, and sales channels.

`Enhance Data-Driven Decision Making`
Empower stakeholders with actionable insights into key KPIs such as total orders, revenue, costs, net profit, and return rate % to support strategic and operational decision-making.

`Identify and Address Performance Gaps`
Analyze sales and return trends to pinpoint underperforming products or categories and optimize pricing, promotions, and stock availability accordingly.

`Optimize Operational Efficiency and Profitability`
Monitor cost drivers like warehousing, logistics, and marketing spend to control expenses and improve gross and net profit margins across product lines.

`Improve Cross-Functional Collaboration`
Enable marketing, analytics, product, and sales teams to work collaboratively using shared metrics and insights for campaign planning, demand forecasting, and inventory optimization.

## Key Questions

    Q : Which product categories generate the highest revenue and which ones have the highest return rates?

    Q : Are there specific regions or sales channels where sales consistently underperform or overperform?

    Q : What are the trends in total orders, revenue, and net profit over the last 6 to 12 months?

    Q : Which products or categories have the lowest performance?

    Q : how do return rates vary by product or region?

    Q : How do sales and profitability compare across different time periods (monthly, quarterly, yearly)?

    Q : How do the revenues look like in terms of different regions? 

    Q : How do the revenue trends look like over a period of time frame (monthly, semi-yearly and yearly) ?

    Q : Which customers are the highest contributors of the overall revenue?  

## Steps followed 

As a Business Analyst for a leading sports brand organization, I was responsible for creating an interactive Sports Products Tracker Analysis Dashboard to support stakeholders in tracking product performance, sales trends, return rates, and overall operational activity across multiple regions, product categories, and sales channels.

The objective was to deliver actionable insights that would help optimize product assortment, enhance sales and marketing efficiency, improve profitability, and support strategic decision-making across departments.

Below is my step-by-step approach to designing this dashboard in Power BI:

- Step 1 : Upload all csv data files in mySQL work bench. After that, connect it with the Power BI platform using Connector by giving mySQL workbench credentials. Lastly, select the tables from the mySQL database.

- Step 2: Open the Power Query Editor and go to the View tab. In the Data Preview section, enable the options for Column Distribution, Column Quality, and Column Profile.

- Step 3: By default, the column profiling is based on the first 1000 rows only. To ensure a comprehensive analysis, change the setting to "Column profiling based on entire dataset."

- Step 4: Once the data has been thoroughly reviewed and cleaned, it no longer contains any errors or empty values across the columns—indicating that we now have a high-quality dataset ready for further transformation and visualization.

- Step 5: In the Report View, under the View tab, the default theme was applied.

- Step 6: **Designing KPI Cards for Key Metrics** – To provide stakeholders with a concise overview, I created four KPI cards that highlight key engagement metrics. These indicators offer a real-time view of user interactions and support fast, informed decision-making.

      Total Orders = DISTINCTCOUNT('Sales Data'[OrderNumber])

      Total Cost = SUMX('Sales Data’,'Sales Data'[OrderQuantity] *RELATED('Product Lookup'[ProductCost]))

      Total Revenue = SUMX('Sales Data’,'Sales Data'[OrderQuantity] *RELATED('Product Lookup'[ProductPrice]))

      Total Profit = [Total Revenue] - [Total Cost]

      Return Rate = DIVIDE([Quantity Returned],[Quantity Sold],"No Sales")

      Quantity Returned = SUM('Returns Data'[ReturnQuantity])

      Quantity Sold = SUM('Sales Data'[OrderQuantity])


  I formatted the KPI cards using currency symbols to enhance visual clarity, enabling executives to instantly understand key performance metrics without delving into detailed data.

  ![KPI Highlights](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/KPI-H.jpg)
           
- Step 7 : **Visualizing Revenue Trend Over Time** – I incorporated a line chart to effectively represent the revenue growth over a monthly timeline from January 2020 to present.

        Fields Used:

        X-axis: Start of Month

        Y-axis: Total Revenue

   The chart clearly demonstrates a steady and significant upward trend in revenue over the two-year period. Initially, revenue remained relatively flat from Jan 2020 to mid-2021, hovering around the $0.3M to $0.5M range.

   The presence of the dotted trendline further confirms a strong positive trajectory, suggesting consistent long-term growth. The light yellow forecast band indicates a high level of confidence in continued growth, with minimal deviation expected.

 ![Revenue Trend](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/Revenue-trend-H.jpg)


  Monthly Revenue vs Last Month Revenue highlights the financial growth or decline, helping to measure the overall sales performance.

  Monthly Orders vs Last Month Orders tracks the change in customer demand and purchasing activity.

  Monthly Returns vs Last Month Returns monitors the rate of product returns, offering insights into customer satisfaction and potential product issues.


![Monthly Revenue, Orders, Returns](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/Monthly-Rev-order-returen-H.jpg)


- Step 8 : **Analyzing Product Category Performance** – I implemented a horizontal bar chart to illustrate the volume of orders segmented by product categories, helping stakeholders easily spot which segments are driving the most sales.

        Fields used:

        X-Axis: Total Orders 

        Y-axis: CategoryName (Accessories, Bikes, Clothing)

   The chart reveals that Accessories are the top-performing category, with 17.0K orders, making it the most in-demand product line. Following closely is the Bikes category, generating 13.9K orders, suggesting consistent interest but slightly lower traction than Accessories.

   On the other hand, Clothing saw significantly fewer orders at 7.0K, which is less than half the volume of Accessories. This indicates a potential area for improvement or re-evaluation in terms of inventory, marketing strategy, or product offerings.

 ![Order by Category](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/order-category-H.jpg)

- Step 9 :  **Evaluating Product Performance and Return Behavior** – I created a tabular visualization to showcase the relationship between Orders, Revenue, and Return Rate % at the product level, enabling stakeholders to assess high-performing items and identify potential return-related issues.

        Fields used (Table format):

        Product Name: The name of the product

        Orders: The no. of orders received

        Revenue: The revenue obtained

        Return Rate %: The rate of product return in percentage

  From the data, the "Water Bottle - 30 oz." generated the highest number of orders (3,983) and a solid revenue of $39,755, with a moderate return rate of 1.95%, indicating strong demand.

  In contrast, the "Sport-100 Helmet, Red" and "Sport-100 Helmet, Blue" each had significantly higher return rates of 3.33% and 3.31%, respectively—despite also contributing substantial revenue ($73,444 and $67,120). This suggests potential quality, or other issues that result in its returning.

  The lowest return rate was seen in the "AWC Logo Cap" at just 1.11%, signaling excellent customer satisfaction despite a modest order volume.

  ![Data Table View](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/table-H.jpg)

- Step 10 : **Most ordered and most returned product** - This small section describes the two leading products in each of these respective classifications. This is to quickly know which product is the highest in terms of orders and which one gets returned the most.

        Fields used:

        Most Ordered Product Type: Product subcategory Name type

        Most Returned Product Type: Product subcategory Name type


- Step 11: **Adding Filters to the Dashboard** - To improve user interaction, I integrated two slicers that allow users to customize the data view according to their preferences. These slicers are conveniently accessible through a filter icon located at the top of the dashboard.

  Setting Up Slicers for Interactive Filtering –
  I configured the slicers to enable users to explore the report dynamically and focus on specific segments of interest. These interactive filters empower users to drill into essential dimensions for deeper, targeted analysis.

  I added slicers for:

      Year (2020, 2021, 2022)

      Continent Name (Europe, North America, Pacific)

  To maintain a clean and professional layout, I used dropdown-style slicers, ensuring they impact all visuals across the report. This setup enables business stakeholders to, for instance, compare trends across different years or analyze performance variations between continents effortlessly.

- Step 12: To improve the usability and interactivity of the Power BI report, I added a Reset Filters icon that enables users to quickly clear all selections and revert the report to its original default view. This feature enhances user confidence by making it easy to undo any filter changes, providing more flexibility and a smoother experience.

  First, I inserted a reset or refresh icon using the Insert > Image option and positioned it to the left of the filter icon.

  Next, I manually cleared all filter selections, including Year and Continent name.

  Finally, I enabled the Action feature on the reset icon by setting the Type to Bookmark and linking it to the Clear all Filters bookmark. This configuration ensures that clicking the icon resets all filters to their default (unselected) state.
  
# **Customer Analysis**  

This dashboard is specifically designed to support advanced statistical analysis related to customer behavior and revenue performance. It emphasizes key revenue metrics and highlights significant customers based on the revenue they generate. The core objective is to deliver actionable insights into customer demographics and their influence on order patterns and overall revenue contribution.

By analyzing these trends, stakeholders can better understand which customers are driving business growth and identify potential areas for improvement or expansion. These insights not only support data-driven decision-making but also help shape strategic initiatives aimed at boosting product orders and maximizing revenue opportunities in the future.

  
![Power BI Report - Category View](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/Power-BI-report-C.jpg)


The **KPI Metrics** section provides a quick snapshot of the numbers related to customers and revenues. These include `Total Customer` and `Revenue per Customer`

The **Orders by Income Level** graph displays the overall distribution of number of orders based on the various income levels, This offers a high-level overview of affordability and popularity of the products across various income levels. Based on this data, future product decisions can be made to target selective customers with the right kind of product.

The **Orders by Occupation** section presents a distribution of number of orders based on the customer occupation. This can help in identifying a strong focus area for which new products can be made to target the respective customers.

The **Customers Orders and Revenue** table shows us our customers and how much revenue they are bringing to our brand. The number of orders per customer are also a highlight in this table. Combining everything, this can reveal some interesting patterns about customer purchasing preferences, average no. of orders, monthly and/or yearly revenues and many more. This gives a deep down view of customers purchasing choices.

Another small, yet key section is the **Outstanding Markers**, which includes the top and/or the highest indicators in three categories namely: `Top Customer`, `Largest Order`, and `Highest Revenue`.

# **Product Analysis**  

This particular dashboard showcases the target numbers in comparison with the actual business numbers. It highlights how near or far the key metrics are from the intended targets which ultimately helps determine if some critical decisions need to made to pivot strategically. The core objective is to deliver actionable insights in terms of profits, revenues, and monthly targets.

By analyzing these trends, stakeholders can better understand which customers are driving business growth and identify potential areas for improvement or expansion. These insights not only support data-driven decision-making but also help shape strategic initiatives aimed at boosting product orders and maximizing revenue opportunities in the future.

  ![Power BI Report - Product View](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/Power-BI-report-P.jpg)

The **Target Gauge Indicators** section offers a quick snapshot of three key gauges representing `Monthly orders`, `Monthly profit`, and `Monthly revenue`. Each gauge includes its respective target, allowing users to easily assess whether the set goals have been achieved.

The **Total Profit vs. Adjusted Profit** graph provides a time-based comparison of these two metrics. Users can modify the displayed timeframe, making it easier to observe profit fluctuations over a selected period.

The **Product Metric Selection** box features options such as Profit, Revenue, Return Rate, and Returns, enabling users to filter and view data based on these specific metrics for contextual analysis.

Additionally, the **Top Performer Product** section highlights the best-performing product based on the highest number of orders, highest revenue, and lowest return rate. This serves as a benchmark for other products to identify areas for improvement.


# Snapshot of Report (Power BI Service)

 ![Power BI Service - Full View](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/Power-Service-full-H.jpg)

# Report Snapshot (Power BI DESKTOP)

  ![Power BI Report - Full Home](https://github.com/taarikakanauji/sports-product-tracker-analysis/raw/main/images/Power-BI-report-full-H.jpg)


# **Project Resources: Sports Products Tracker Analysis**  

### **Detailed Report (PDF)**  
[Insights of Sports Products Tracker Analysis](https://github.com/taarikakanauji/sports-product-tracker-analysis/blob/main/Insights%20for%20Sports%20Product%20Tracker.pdf)  

### **Power BI Desktop Demo**  
[Power BI Demo (MKV)](https://github.com/taarikakanauji/sports-product-tracker-analysis/blob/main/Power-BI-Demo.mkv)  

### **Power BI Service Demo**  
[Power BI Service Demo (MKV)](https://github.com/taarikakanauji/sports-product-tracker-analysis/blob/main/Power-Service-Demo.mkv)  

### **PBIP Files**  
- **Report:** [Report Files](https://github.com/taarikakanauji/sports-product-tracker-analysis/tree/main/Sports%20Product%20Tracker.Report)  
- **Semantic Model:** [Semantic Model Files](https://github.com/taarikakanauji/sports-product-tracker-analysis/tree/main/Sports%20Product%20Tracker.SemanticModel)  
- **Project File:** [Sports Products Tracker Analysis PBIP](https://github.com/taarikakanauji/sports-product-tracker-analysis/blob/main/Sports%20Product%20Tracker.pbip)  
- **Gitignore:** [.gitignore](https://github.com/taarikakanauji/sports-product-tracker-analysis/blob/main/.gitignore)  

### **Project README (Setup Guide)**  
[README.md](https://github.com/taarikakanauji/sports-product-tracker-analysis/blob/main/README.md)  

# Conclusion

This Sports Products Analysis Dashboard empowers stakeholders to:

- Uncover key sales patterns and trends across various product categories, regions, and customers.

- Identify high- and low-performing sports products based on revenue, no. of orders, and use that information to prioritize and pivot, on future products.

- Monitor critical performance indicators in real time to ensure the business is catering to the right audience and supplying products for which there is a high demand.

- Leverage interactive slicers and filters for targeted insights by Time, Region, and Products

By leveraging these insights, marketing and sales efforts can be strategically directed toward top-performing products and regions, while underperforming areas can be addressed with data-informed strategies. The ability to reset filters and drill down into detailed metrics ensures an intuitive user experience and supports informed, agile decisions. Ultimately, this dashboard serves as a powerful tool for tracking performance, optimizing sales strategies, and driving the company's growth in the competitive sports products market.


