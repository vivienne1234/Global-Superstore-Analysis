# Global-Superstore-Analysis

![Image](https://github.com/user-attachments/assets/4a6496ea-234b-4d27-9158-2323cc997d27)

## Table of Content

- Introduction
- Data cleaning and Transformation
- Data exploration
- Business Questions
- Analysis and Findings
- Dashboard
- Recommendations

## Introduction

Global Superstore is a global online retailer based in New York, boasting a broad product catalog and aiming to be a one-stop-shop for its customers. Global The superstore’s clientele, hailing from 147 different countries, can browse through an endless offering with more than 10,000 products. This large selection comprises three main categories: office supplies (e.g., staples), furniture (e.g., chairs), and technology (e.g., smartphones). 

## Data Cleaning and Transformation

The Global Superstore dataset was relatively clean upon acquisition, requiring minimal preprocessing. However, some transformation steps were performed to ensure consistency and readiness for analysis:

- File Review & Structure Check – Verified column headers, data types, and overall structure for each table (Orders, Returns, People, etc.).
- Table Merging – Used Excel’s VLOOKUP function to join related tables (e.g., appending Regional Manager data from the People table to Orders based on the Region field).
- Field Standardization – Ensured date formats were consistent and currency values were properly recognized as numeric for aggregation.
- Null/Outlier Review – Checked for missing values and extreme figures in Sales, Quantity, and Profit fields, confirming they were either intentional (e.g., returns) or within realistic ranges.
  
These steps streamlined the dataset for loading into Power BI, allowing for smooth measure creation, filtering, and dashboard visualization.

## Data Exploration

The Global Superstore dataset was explored using SQL within SQL Server Management Studio (SSMS) to uncover actionable business insights.
SQL queries were used to filter, group, and aggregate the data in order to answer specific strategic questions about sales, profitability, product performance, and market opportunities.

Key exploration tasks included:

- Profitability Analysis – Identified top-performing and underperforming countries, regions, and subcategories.
- Product Performance – Determined high-profit and low-profit products in specific markets.
- Cost Analysis – Evaluated the impact of shipping costs and discounts on overall profitability.
- Geographic Insights – Assessed country, and city-level performance to spot market opportunities and threats.
- Customer Value Assessment – Pinpointed the most valuable customers and analyzed their purchase patterns.
- The SQL exploration directly addressed some business questions which will be discussed subsequently.

## Business Questions

Question 1. a) What are the three countries that generated the highest total profit for Global Superstore in 2014? b) For each of these three countries, find the three products with the highest total profit. Specifically, what are the products’ names and the total profit for each product?

Question 2. a) Identify the 3 subcategories with the highest average shipping cost in the United States. 

Question 3. a) Assess Nigeria’s profitability (i.e., total profit) for 2014. How does it compare to other African countries? b) What factors might be responsible for Nigeria’s poor performance? You might want to investigate shipping costs and the average discount as potential root causes. 

Question 4. a) Identify the product subcategory that is the least profitable in Southeast Asia. Note: For this question, assume that Southeast Asia comprises Cambodia, Indonesia, Malaysia, Myanmar (Burma), the Philippines, Singapore, Thailand, and Vietnam. b) Is there a specific country i n Southeast Asia where Global Superstore should stop offering the subcategory identified in 4a? 

Question 5. a) Which city is the least profitable (in terms of average profit) in the United States? For this analysis, discard the cities with less than 10 Orders. b) Why is this city’s average profit so low? 

Question 6. a) Which product subcategory has the highest average profit in Australia? 

Question 7. a)Who are the most valuable customers and what do they purchase?

All SQL queries can be found in [queries.sql](https://github.com/vivienne1234/Global-Superstore-Analysis/blob/main/Global%20superstore%20SQL%20queries.txt)

## Analysis and Findings

### Question 1

##### a) What are the three countries that generated the highest total profit for Global Superstore in 2014? 

From the query results, analysis of the 2014 sales data revealed that the United States generated the highest total profit for Global Superstore, amounting to $93,507.55. Following at a distant second was India, with total profits of $48,807.67, while China ranked third with $46,793.99. The United States’ performance was particularly notable, delivering almost twice the profit of India and significantly outperforming China, indicating a dominant contribution to the company’s global profitability in that year

##### b) For each of these three countries, find the three products with the highest total profit. Specifically, what are the products’ names and the total profit for each product? 

Further analysis of the top-performing countries in 2014 reveals distinct product drivers behind their profitability.
China’s leading profit contributors were the Sauder Classic Bookcase (Metal) generating $1,463.07, the Bush Classic Bookcase (Mobile) with $1,220.52, and the HP Copy Machine (Color) earning $1,196.13 in total profit.
In India, the most profitable items were the Sauder Classic Bookcase ($2,419.65), Cisco Smart Phone with Caller ID ($1,609.38), and the Hamilton Beach Refrigerator ($1,440.24).
For the United States, the top profit-generating products were the Canon imageCLASS 2200 Advanced Copier ($15,679.96), the Hewlett Packard LaserJet 3310 Printer ($3,623.94), and the GBC DocuBind TL300 Electric Binding Machine ($1,910.58).
These findings highlight that while China and India’s top profits came from a mix of office furniture and electronics, the United States’ profits were heavily driven by high-value office technology products.


### Question 2

##### a) Identify the 3 subcategories with the highest average shipping cost in the United States. 

In 2014, shipping cost analysis for the United States revealed that certain product subcategories incur significantly higher logistics expenses. The three subcategories with the highest average shipping cost were:

Copiers – averaging $165.29 per shipment

Machines – averaging $132.25 per shipment

Tables – averaging $69.95 per shipment

The substantial shipping cost for Copiers and Machines likely reflects their weight, bulk, and need for specialized handling, while Tables also incur elevated costs due to size and packaging requirements


### Question 3

##### a) Assess Nigeria’s profitability (i.e., total profit) for 2014. How does it compare to other African countries? 

In 2014, Nigeria recorded a total profit of -$23,285.25, making it one of the poorest-performing markets for Global Superstore in Africa. This was a stark contrast to several neighboring countries that achieved positive results.

For example:

Ghana generated $2,775.06, outperforming Nigeria by over $26,000.

Mozambique earned $2,440.80, exceeding Nigeria’s performance by roughly $25,700.

Even smaller markets such as Mauritania ($1,033.62) and Côte d’Ivoire ($2,537.67) outperformed Nigeria by significant margins.

The data highlights a serious profitability gap, indicating that Nigeria’s operations not only underperformed relative to its peers but also contributed a substantial loss to the region’s overall results.

##### b) What factors might be responsible for Nigeria’s poor performance? You might want to investigate shipping costs and the average discount as potential root causes. 

An analysis of Nigeria’s 2014 operational metrics reveals two key red flags:

High Average Shipping Cost – At $5.50 per order, Nigeria’s shipping cost is considerably higher than the average for many African markets. This increases operational expenses and directly erodes profit margins.

Significant Average Discount – Nigeria recorded an average discount rate of 70% (0.7), which is extremely high compared to normal promotional practices. Such deep price cuts severely undermine revenue potential.

Negative Profit Margin – The combination of high shipping costs and aggressive discounting led to a profit margin of -1.51, confirming that sales were being made at a loss.
This suggests that Nigeria’s poor performance is less about market demand and more about inefficient cost control and unsustainable discount strategies.


### Question 4

##### a) Identify the product subcategory that is the least profitable in Southeast Asia. Note: For this question, assume that Southeast Asia comprises Cambodia, Indonesia, Malaysia, Myanmar (Burma), the Philippines, Singapore, Thailand, and Vietnam. 

From the analysis, the Tables subcategory recorded the lowest profitability in Southeast Asia, with a total loss of $18,618.32.
This negative performance suggests either high-cost structures, excessive discounting, or poor market demand for this product category in the region.
Given the extent of the loss, it warrants a deeper investigation into pricing strategies, supply chain efficiency, and customer preferences in Southeast Asian markets.

##### b) Is there a specific country in Southeast Asia where Global Superstore should stop offering the subcategory identified in 4a? 

The analysis shows that within Southeast Asia, Indonesia records the highest loss for the Tables sub-category, with a negative profit of -$10,680.28. This indicates that selling Tables in this market is significantly unprofitable.


### Question 5

##### a) Which city is the least profitable (in terms of average profit) in the United States? For this analysis, discard the cities with less than 10 Orders. 

The city of Lancaster emerged as the least profitable city in the United States, with an average profit of –$157.37 across 46 orders. This consistently negative profit per order may indicate a combination of high shipping costs, aggressive discounting, or low-margin product sales specific to this location. Addressing this issue could involve revisiting pricing, optimizing fulfillment options, or shifting the sales mix toward higher-margin items in Lancaster.

##### b) Why is this city’s average profit so low? 

In Lancaster, the low average profit of –$157.37 appears to be driven by a combination of operational and pricing factors:

- High shipping costs: The average shipping cost per order is $23.99, which likely erodes margins, especially on lower-priced items.
Significant discounting: The average discount rate is 32%, which is substantially higher than typical promotional levels and directly reduces profitability.

- Negative profit margin: The city records a –73.19% profit margin, meaning costs (including discounts and shipping) consistently outweigh revenues.
  
- Sales mix issue: Despite generating $9,891.46 in total sales from 46 orders, the combination of heavy discounting and high fulfillment expenses results in persistent losses.


### Question 6

##### a) Which product subcategory has the highest average profit in Australia? 

The Appliances subcategory records the highest average profit in Australia, with an average profit of $139.02 per transaction. This suggests that appliances not only sell at a healthy margin but also face lower cost pressures compared to other categories in the Australian market.

Implication: Australia’s sales strategy could prioritize appliances through targeted marketing and inventory allocation to maximize profitability.


### Question 7

##### a) Who are the most valuable customers and what do they purchase? 

The top three most valuable customers, based on total profit contribution, are:

- Tamara Chand – $8,672.90 in total profit
- Raymond Buch – $8,453.04 in total profit
- Sanjit Chand – $8,205.36 in total profit
  
These customers purchased products across all three main categories; Furniture, Technology, and Office Supplies, demonstrating a broad and diversified buying pattern. While their exact product lists are extensive, the data indicates consistent purchases of high-margin items, suggesting a strong propensity for premium and business-oriented goods.

Implication: These high-value customers are prime candidates for loyalty programs, targeted promotions, and exclusive offers to encourage retention and increase lifetime value.


## Dashboard

![Image](https://github.com/vivienne1234/Global-Superstore-Analysis/blob/main/Global%20dashboard.png?raw=true)

Click [HERE](https://app.powerbi.com/links/xttpePhFeZ?ctid=c470f255-2be6-4283-868b-c8acfb65ec7b&pbi_source=linkShare&bookmarkGuid=5a1047da-442c-4d24-bbd0-d99ccda74866) to view the Interactive dashboard


## Recommendation

The analysis reveals several key insights into profitability, product performance, and customer value:

- Product-Level Actions
  
Tables stand out as a consistently underperforming sub-category, with significant losses in multiple regions, especially Indonesia in Southeast Asia.
Immediate review of the pricing, supplier agreements, and logistics for this sub-category is necessary. If improvement measures fail, phasing out Tables in unprofitable markets should be prioritized.

- Regional Optimization
  
Regions and cities with negative profit margins (e.g., Lancaster in 5b) should be closely examined for causes such as excessive discounts, high shipping costs, or poor demand.
Marketing efforts and product mix should be tailored to high-performing areas while scaling back in loss-making ones.

- Customer Retention & Upselling
  
The top customers; Tamara Chand, Raymond Buch, and Sanjit Chand, generate substantial profits across categories.
A loyalty program, personalized offers, or priority services for these high-value customers could further strengthen their retention and increase lifetime value.

- Sub-Category Growth

High-profit sub-categories like Appliances (139.02 average profit) should receive increased promotional and stocking priority in both physical and online channels.

- Strategic Direction:

Focus on profitable sub-categories and top customers, aggressively cut or optimize loss-making products in specific regions, and leverage data-driven targeting to allocate marketing spend where it delivers the highest ROI. This approach will not only reduce waste but also improve the overall profit margin.












