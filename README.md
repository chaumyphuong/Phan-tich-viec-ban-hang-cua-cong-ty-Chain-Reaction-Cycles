# Chain Reaction Cycles – Sales Performance Analysis
**Author:** Chau My Phuong

**Date:** June 2024

**Project Description**

In today’s business landscape, data has become one of the most valuable assets any organization can possess. This project leverages the real-world-like AdventureWorks Sales dataset to deeply analyze the sales performance of Chain Reaction Cycles – once the world’s largest online bicycle retailer. The result is a production-grade analytics dashboard that reveals exactly where profit is made and lost across channels, regions, product lines, seasons, and resellers – turning raw numbers into clear business decisions.

The project covers the lifecycle including: data collection, cleansing, advanced DAX measurements, modeling, visualizations, exploratory analysis, and actionable strategic recommendations.

**Project Objectives**
- Evaluate the current sales performance of Chain Reaction Cycles Company
- Propose solutions to improve sales performance
- Propose marketing strategies to attract more potential customers
- Propose measures to increase conversion rates
- Propose pricing strategies to maximize profits
- Propose measures to improve customer experience
-----

# Background
## Overall
- **Company Name:** Chain Reaction Cycles (CRC)
- **Year Established:** 1985
- **Business Industry:** Bicycles, including bicycles, parts and accessories.
- **Business Size:** Small Retail
- **Market segment:** cycling enthusiasts, from beginners to professional riders.
- **Products:** mountain bikes, road bikes, city bikes, and accessories and spare parts.
- **Awards and achievements:** CRC's customer support team won the "Customer Service Team of the Year" award for the whole of Europe for their efficient workflow and ability to use customer feedback to improve service
- **Vision:** Chain Reaction Cycles aims to be the world's leading bicycle retailer, providing the best online cycling shopping experience for customers worldwide.
- **Mission:** Chain Reaction Cycles is committed to providing high-quality products and services, dedicated customer support, and always updating technology to improve the user experience.

## History:
 - Chain Reaction Cycles began as a small shop called Ballynure Cycles in Northern Ireland in 1985, founded by George and Janice Watson.
 - In 1998, the business moved to mail order
 - In 1999 launched ChainReactionCycles.com, serving customers in over 155 countries, ushering in a period of strong growth in e-commerce.
 - CRC rapidly expanded to become one of the world's leading online bicycle retailers, with sales peaking in 2013.
 - In 2016, Chain Reaction Cycles merged with Wiggle to form the WiggleCRC group.
 - The group then achieved an annual turnover of over £300 million and expanded further with the acquisition of German company Bike24 in 2017.

## Organizational chart
Chain Reaction Cycles operates under the management of an executive board consisting of senior managers from various departments. Departments include:
- **Sales and marketing department:** Responsible for promoting and selling products.
- **Customer service department:** Multilingual customer support team, answering questions and handling warranty-related issues.
- **Warehouse and shipping department:** Manages the storage and shipping of goods to customers worldwide.
- **Engineering department:** Ensures bicycle products and components are assembled and quality tested before shipping.

## Daily Operations
CRC's daily operations include warehouse management, online order processing, customer service, website management, and online marketing campaigns. CRC also invests in improving customer service and optimizing delivery times worldwide.
- **Order Processing:** Each week, Chain Reaction Cycles processes approximately 100,000 products and ships them to customers worldwide. CRC's state-of-the-art warehouse management system and staff ensure that orders are processed quickly and accurately, efficiently meeting the shopping needs of global customers.
- **Multilingual Customer Support:** CRC's customer support team of 82 people is fluent in 7 languages: English, French, Italian, Spanish, German, Russian, and Portuguese. The customer service team is available from 7am to 6pm, 7 days a week to support customers via phone, email, social media and online chat.
- **Inventory management and shipping process:** CRC's large inventory management system is optimized to track and maintain accurate inventory levels to ensure that products are always available to customers. CRC's shipping process is also designed to optimize delivery times and shipping costs for customers.

## Purpose and significance of data collection and data analysis
Data collection and analysis helps CRC better understand customer shopping behavior, market trends and consumer needs. This allows CRC to optimize marketing strategies, improve customer experience and manage inventory more effectively. Specifically:
- **Customer shopping behavior:** Helps identify customer trends and preferences, develop more accurate and effective marketing strategies.
- **Market trends:** Helps predict customer demand and adjust inventory levels appropriately, avoiding shortages or surpluses.
- **Customer experience:** Helps identify areas for improvement in the shopping process and customer service, improve service quality and increase customer satisfaction customer flow.
In addition, data analysis also helps CRC optimize internal processes such as inventory management, order processing and shipping. Monitoring and analyzing data helps detect problems and bottlenecks in the process, propose timely improvement measures, improve operational efficiency, minimize costs and enhance competitiveness in the market.

# Data introduction
The data used for this project is extracted from a single data file, providing a comprehensive view of sales activities.
- **Data file name:** 4-AdventureWorks Sales.xlsx
- **Source:** Data provided by lecturer Pham Thi Thanh Tam.

This data file includes 7 separate sheets/tables, linked together to describe the business process and related entities in detail. The combination of these tables allows the team to perform multidimensional analysis of business activities, thereby making effective assessments and strategic recommendations.

**16 data tables include:**
1. **SalesOrderLine:** Contains line items for sales orders, identifying each product in an order.
2. **SalesOrder:** Contains detailed information about orders that have been placed.
3. **Sales:** The main transaction data table, records sales events.
4. **Channel:** Dimension table for sales channels.
5. **Sales Territory:** Contains information about the geographical areas where sales activities take place.
6. **Country:** Countries involved in sales (United States, Canada, France, Germany, Australia, United Kingdom), grouped by regions.
7. **Group:** High-level geographic groups (North America, Europe, Pacific)
8. **City:** Cities with associated state/provinces.
9. **State-Province:** States or provinces linked to countries.
10. **Reseller:** Contains information about retail partners.
11. **Business Type:** Types of reseller businesses (Value Added Reseller, Specialty Bike Shop, Warehouse)
12. **Date:** Contains time-related data (often used for cyclical analysis).
13. **Product:** Contains descriptive information about the items sold.
14. **Subcategory:** Product subcategories
15. **Category:** High-level product categories
16. **Customer:** Contains detailed information about customers who purchased the product.

**Specific table data description:**

**1. SalesOrderLine** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | SalesOrderLineKey | Unique identifier for each order line | Number | Primary Key |
| 2 | Sales Order Line | Human-readable sales order + line number | Short Text | Display purpose |

**2. SalesOrder** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | Sales Order | Sales order number | Short Text |
| 2 | SalesOrderLineKey | Link to individual line item | Number | Foreign Key |
| 3 | Sales Order Line | Line identifier within the order | Short Text |
| 4 | ChannelKey | Sales channel (1 = Reseller, 2 = Internet) | Number | Foreign Key |

**3. Sales** (Fact Table) 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | SalesOrderLineKey | Link to order line | Number | Primary / Foreign Key |
| 2 | ResellerKey | Reseller ID | Number | Foreign Key |
| 3 | CustomerKey | Customer ID | Number | Foreign Key |
| 4 | ProductKey | Product sold | Number | Foreign Key |
| 5 | OrderDateKey | Date of order | Number | Foreign Key to Date |
| 6 | DueDateKey | Promised delivery date | Number | Foreign Key to Date |
| 7 | ShipDateKey | Actual shipping date | Number | Foreign Key to Date |
| 8 | SalesTerritoryKey | Sales territory/region | Number | Foreign Key |
| 9 | Order Quantity | Quantity ordered | Number |
| 10 | Unit Price | Selling price per unit (after discount) | Currency |
| 11 | Sale Amount | Line total (Quantity × Unit Price) | Currency |
| 12 | Product Standard Cost | Standard manufacturing cost per unit | Currency |
| 13 | Total Product Cost | Total cost (Quantity × Standard Cost) | Currency |

**4. Channel** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | ChannelKey | Unique key | Number | Primary Key |
| 2 | Channel | Channel name (Reseller / Internet) | Short Text |

**5. SalesTerritory** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | SalesTerritoryKey | Unique territory key | Number | Primary Key |
| 2 | Region | Region name (e.g., Northwest) | Short Text |
| 3 | CountryKey | Link to Country table | Number | Foreign Key |

**6. Country** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | CountryKey | Unique key | Number | Primary Key |
| 2 | Country | Country name | Short Text |
| 3 | GroupKey | Link to geographic group | Number | Foreign Key |

**7. Group** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | GroupKey | Unique key | Number | Primary Key |
| 2 | Group | Region group | Short Text |

**8. City** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | CityKey | Unique key | Number | Primary Key |
| 2 | City | City name | Short Text |
| 3 | StateProvinceKey | Link to State-Province table | Number | Foreign Key |

**9. State-Province** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | StateProvinceKey| Unique key | Number | Primary Key |
| 2 | State-Province | State or province name | Short Text |
| 3 | CountryID | Link to Country | Number | Foreign Key |

**10. Reseller** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | ResellerKey | Unique key | Number | Primary Key |
| 2 | Reseller ID | Business code | Short Text |
| 3 | TypeID | Link to Business Type | Number | Foreign Key |
| 4 | ResellerName | Reseller company name | Short Text |
| 5 | CityKey | Location of reseller | Number | Foreign Key |

**11. Business Type** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | TypeID | Unique key | Number | Primary Key |
| 2 | Business Type | Type of business | Short Text |

**12. Date** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | DateKey | YYYYMMDD format | Number | Primary Key |
| 2 | Full Date | Readable date | Short Text |
| 3 | Year | Calendar year | Number |
| 4 | Month | Month number | Number |

**13. Product** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | ProductKey | Unique product identifier | Number | Primary Key |
| 2 | SKU | Stock-keeping unit | Short Text |
| 3 | Product | Product name | Short Text |
| 4 | Standard Cost | Manufacturing standard cost | Currency |
| 5 | Color | Product color | Short Text |
| 6 | List Price | Original list price | Currency |
| 7 | Model | Model name | Short Text |
| 8 | SubcategoryKey | Link to Subcategory | Number | Foreign Key |

**14. Subcategory** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | SubcategoryKey | Unique key | Number | Primary Key |
| 2 | Subcategory | Subcategory name | Short Text |
| 3 | Categorykey | Link to Category | Number | Foreign Key |

**15. Category** 
| No. | Attribute Name | Description Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | CategoryKey | Unique key | Number | Primary Key |
| 2 | Category | Main category | Short Text |

**16. Customer** 
| No. | Attribute Name | Description | Data Type | Note |
|:---:|:---|:---|:---:|:---|
| 1 | CustomerKey | Unique key | Number | Primary Key |
| 2 | Customer ID | Business identification code | Short Text |
| 3 | Customer | Full name of the customer | Short Text |
| 4 | City | Customer city | Short Text |
| 5 | State-Province | State or province | Short Text |
| 6 | Country-Region | Country name | Short Text |
| 7 | Postal Code | Postal/ZIP code | Short Text |

# Data preparation & Pre-processing 
All preprocessing steps were performed in Power Query and Power Pivot (Excel/Power BI), resulting in a clean, well-structured, and analysis-ready data model.
## Data collection
After reviewing several datasets on Kaggle, I selected the AdventureWorks Sales dataset as the most suitable proxy for analyzing Chain Reaction Cycles (CRC) sales performance.

**Steps performed:**
- **Step 1:** Searched for relevant sales datasets on Kaggle
- **Step 2:** Downloaded the complete dataset
- **Step 3:** Extracted and chose the main file for analysis
  
→ **File used:** 4-AdventureWorks Sales.xlsx

## Data cleaning
The following cleaning actions were applied:
- **In the Date table:** 

![Raw data in Date table](./images/Date_raw.png)

Fiscal Year and Month columns were not in the desired format → reformatted using Excel formulas for consistency.
- **In the Sales fact table:**

![Raw data in Sales table](./images/Sales_data_raw.png)
  - Unit Price Discount Pct column contained only zeros across all rows → removed as redundant.
  - Because the Unit Price Discount Pct column is deleted data, it affects the Sales Amount column, so the Sales Amount column is also deleted.
  - Extended Amount was renamed to Sales Amount to correctly reflect line total revenue.

![Cleaned data in Sales table](./images/Sales_data_cleaned.png)

## Data transformation
To enable deeper and more flexible analysis, I transformed the flat structure into a proper Snowflake schema by normalizing dimension tables:
- Extracted Group and Country from SalesTerritory → created hierarchy: Group → Country → Territory
- Extracted Business Type from Reseller → created hierarchy: Business Type → Reseller
- Extracted Category and Subcategory from Product → created hierarchy: Category → Subcategory → Product
- Extracted Channel from Sales Order data → created hierarchy: Channel → SalesOrder

**Custom DAX Measures created:**
- **Profit:** Total Sales Amount - Total Cost
- **Profit Margin (%):** Profit divided by Total Sales Amount (formatted as a percentage)
- **Total Customers:** Count of the distinct values in the 'CustomerKey' column
- **Total Sale Orders:** Count of the distinct values in the 'Sales Order' column
- **Profit/Loss Flag:** "Profit" if Total Sale Amount - Total Product Cost is greater than zero, "Loss" if less than zero, and "Break Even" if equal to zero.
- **Total Loss Orders:** Count of distinct Sales Orders where the total Profit for that entire order is less than zero.
- **Total Profit Orders:** Count of distinct Sales Orders where the total Profit for that entire order is greater than zero.

![Add new measures to Sales table](./images/Sales_new_measures.png)

## Data Reduction
In the Date table, the Monthkey and Date columns are the columns whose data will be deleted because this is redundant data for the group. In addition, the Customer table data is also chosen by the group to be ignored, not analyzed and used much other than to calculate the total number of customers who have purchased because the table data is difficult to analyze and does not have a clear connection with other tables as well as the Sales table.

## Data Model
![Data Model](./images/Data_model.png)
- Model type: This is a Snowflake Schema data model
- Structure:
  - There is a central table called "Sales" (fact table).
  - Relationship between tables:
    - Sales → Date
    - Sales → SalesOrder → Channel 
    - Sales → Product → Subcategory → Category
    - Sales → SalesTerritory → Country → Group
    - Sales → Reseller → Business Type

# Analysis
## Overview dashboard
![Overview dashboard](./images/overview_dashboard.png)

The Overview dashboard provides an overview of CRC's sales performance.

Financial metrics that businesses are interested in can help businesses monitor and evaluate sales performance.
- Standard cost: 43.97 million
- Total cost: 97.26 million
- Number of products sold: 275 thousand
- Total orders: 31 thousand
- Total revenue: 110.34 million
- Profit: 13.08 million
- Total customers: 18.49 thousand
- Profit margin: 11.85%


