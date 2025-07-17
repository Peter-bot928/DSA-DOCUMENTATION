# MY DSA-DOCUMENTATION
My DSA Data Analysis Capstone Portfolio showcasing Excel, Power BI, and SQL skills




## CASE STUDY 1

## Project Topic: SQL-Based Inventory Analysis for Kultra Mega Stores (KMS) Abuja Division

## Project Overview: 
To analyze order data from 2009 to 2012 for KMS’s Abuja division, 
using SQL to extract insights on sales, customer segments, shipping methods,
and order priorities, enabling data-driven decisions to optimize revenue and operations.

## Data Sources
### Primary Data Source: 
KMS_Case_Study.csv

## Tools Used:
- Ms Excel for preliminary data exploration and validation of the KMS_Case_Study.csv file [Download Here](https://drive.google.com/file/d/1MjF1hQxMRZTLfUy0naUpClMT4OOOcMCX/view?usp=sharing)
- SQL Server (for Querying and Analysis) [Download Here](https://drive.google.com/file/d/1tiYijUsNSowXJ-Gz9Sjr9VdZFSmYK0yr/view?usp=drive_link)
- SQL Server Management Studio (SSMS): Utilized for writing and executing SQL queries to analyze the data.
- GitHub: Used for version control and hosting the project documentation, queries, and dataset.

##  Data Analysis:
This is where i include some basic lines of code or Queries used during my Analysis. 
Below are the Questions and Solutions to my Queries;


-----Question 1-----

---Which product category had the highest sales?---

``` SQL
SELECT TOP 1 Product_Category, SUM(Sales) AS total_sales
FROM KMS_Case_Study
GROUP BY Product_Category
ORDER BY total_sales DESC;
```


-----Question 2-----

---What are the Top 3 and Bottom 3 regions in terms of sales?---

``` SQL
SELECT TOP 3 Region, SUM(Sales) AS total_sales
FROM KMS_Case_Study
GROUP BY Region
ORDER BY total_sales DESC;
```

SELECT TOP 3 Region, SUM(Sales) AS total_sales

``` SQL
FROM KMS_Case_Study
GROUP BY Region
ORDER BY total_sales ASC;
```

-----Question 3-----

---What were the total sales of appliances in Ontario?---

``` SQL
SELECT SUM(Sales) AS total_appliance_sales
FROM KMS_Case_Study
WHERE Product_Category = 'Appliances' AND Region = 'Ontario';
```

-----Question 4-----

---Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers.---

``` SQL
SELECT TOP 10 Customer_Name, SUM(Sales) AS total_sales
FROM KMS_Case_Study
GROUP BY Customer_Name
ORDER BY total_sales ASC;
```

-----Question 5-----

---KMS incurred the most shipping cost using which shipping method?---

``` SQL
SELECT TOP 1 Ship_Mode, SUM(Shipping_Cost) AS total_shipping_cost
FROM KMS_Case_Study
GROUP BY Ship_Mode
ORDER BY total_shipping_cost DESC;
```


----Case Scenario II----

-----Question 6-----

---Who are the most valuable customers, and what products or services do they typically purchase?---


``` SQL
SELECT TOP 5 Customer_Name, SUM(Sales) AS total_sales, Product_Category
FROM KMS_Case_Study
GROUP BY Customer_Name, Product_Category
ORDER BY total_sales DESC;
```


-----Question 7-----

---Which small business customer had the highest sales?---


``` SQL
SELECT TOP 1 Customer_Name, SUM(Sales) AS total_sales
FROM KMS_Case_Study
WHERE Customer_Segment = 'Small Business'
GROUP BY Customer_Name
ORDER BY total_sales DESC;
```

-----Question 8-----

---Which Corporate Customer placed the most number of orders in 2009–2012?---

``` SQL
SELECT TOP 1 Customer_Name, COUNT(Order_ID) AS order_count
FROM KMS_Case_Study
WHERE Customer_Segment = 'Corporate' 
  AND Order_Date BETWEEN '2009-01-01' AND '2012-12-31'
GROUP BY Customer_Name
ORDER BY order_count DESC;
```


-----Question 9-----

---Which consumer customer was the most profitable one?---

``` SQL
SELECT TOP 1 Customer_Name, SUM(Profit) AS total_profit
FROM KMS_Case_Study
WHERE Customer_Segment = 'Consumer'
GROUP BY Customer_Name
ORDER BY total_profit DESC;
```

-----Question 10-----

---Which customer returned items, and what segment do they belong to?---

``` SQL
SELECT Customer_Name, Customer_Segment
FROM KMS_Case_Study
WHERE Profit < 0
GROUP BY Customer_Name, Customer_Segment;
```

-----Question 11-----

---If the delivery truck is the most economical but the slowest shipping method and Express Air--- 

---is the fastest but the most expensive one, do you think the company appropriately spent--- 

---shipping costs based on the Order Priority? Explain your answer.---

``` SQL
SELECT Ship_Mode, Order_Priority, AVG(Shipping_Cost) AS avg_shipping_cost
FROM KMS_Case_Study
GROUP BY Ship_Mode, Order_Priority
ORDER BY Ship_Mode, Order_Priority;
```







## CASE STUDY 2



## Project Topic: Human Resources Data Analysis for Gender Equality and Employee Performance Evaluation

## Project Overview: 
This project analyzes employee data for the Palmoria Group to address HR challenges, focusing on gender equality, salary structures, and employee performance.
The analysis explores gender distribution, salary disparities, employee ratings, bonus allocations, and compliance with minimum salary standards across departments and regions. 
The goal is to provide data-driven insights to improve HR policies, promote equitable compensation, and enhance workforce management strategies.

## Data Sources
### Primary Data Source: 
- File: Palmoria_HR_Data.csv (or equivalent, provided as CSV)
- Description: A dataset with approximately 946 rows, detailing employee information.
- Key Columns: Name, Gender, Department, Salary, Region, Ratings, Department Ratings, Bonus Rates, Annual Bonuses, Salary Bands
- Source Context: The dataset contains employee records from the Palmoria Group, used to investigate gender-related issues, salary gaps, and performance metrics.

## Tools Used:
- Ms Excel: For data import, exploration, and preliminary analysis of the Palmoria_HR_Data.csv file. [Download Here](https://drive.google.com/drive/folders/1KYOhVybechdWS2bgbYSLI6qT82RFF-Ot?usp=sharing)
- Power BI: For Data Cleaning [Download Here](https://drive.google.com/file/d/1D-gbYOQ5X2K1_HSs43yErS5nryzF-i1A/view?usp=sharing)
- For Creating a report
- For creating visualizations.

## Data Cleaning and Preparation:

In the initial phase of the Data Cleaning and preparations, we perform the following action;
- Data Loading and Inspection
- Handling Missing Values
- Data Validation
- Data Transformations
- Preparation for Visualization

## Explainatory Data Analysis:
EDA involved the exploring of the Data to answer some Questions about the Data such as;
- What is the gender distrubtion in the Organization
- Show insight on ratings based on Gender
- Analyze the Company Salary Structure

##  Data Analysis:


