# 🗄️ SQL Data Analysis & Database Design

*A hands-on SQL project focused on relational database design, data querying, and analytical problem-solving using real-world datasets.*

---

## 🚀 Overview

This project showcases my SQL skills through practical exercises involving database creation, schema design, data querying, and analysis.

Working with both the **Northwind** and **World** databases, I explored how relational databases are structured, created table relationships, and wrote SQL queries to retrieve, filter, combine, and analyse data. The project strengthened my understanding of how SQL supports business reporting, operational analysis, and data-driven decision-making.

---

## 🛠️ Skills & Techniques Applied

### 🔗 Database Fundamentals

✅ Primary & Foreign Keys  
✅ Relational Database Concepts  
✅ One-to-One Relationships  
✅ One-to-Many Relationships  
✅ Many-to-Many Relationships  
✅ Structured vs Unstructured Data  

### 🏗️ Database Design

✅ Entity Relationship Design (ERD)  
✅ Table Creation & Schema Development  
✅ Fact & Dimension Tables  
✅ Snowflake Schema Concepts  
✅ Data Integrity & Relationships  

### 🔍 SQL Querying

✅ `SELECT`  
✅ `WHERE`  
✅ `ORDER BY`  
✅ `GROUP BY`  
✅ `HAVING`  
✅ `BETWEEN`  
✅ `LIKE`  
✅ Aggregate Functions (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`)  

### 🤝 Table Joins

✅ INNER JOIN  
✅ LEFT JOIN  
✅ RIGHT JOIN  
✅ FULL JOIN  
✅ CROSS JOIN  
✅ SELF JOIN  

---

## 💡 Project Highlights

### 🏪 Northwind Database Analysis

Using the Northwind dataset, I explored customer, product, supplier, employee, and order information to generate meaningful business insights.

Key activities included:

- Retrieving and filtering customer records
- Building detailed order reports using JOINs
- Combining customer and employee data with order information
- Analysing sales activity and operational data
- Generating business-focused reports from multiple related tables

### 🌍 World Database Analysis

Using the World database, I analysed geographic and demographic data to uncover trends and patterns.

Key activities included:

- Exploring city and country populations
- Identifying highly populated cities and regions
- Comparing population statistics across countries
- Investigating life expectancy and demographic indicators
- Producing ranked reports using sorting and aggregation techniques

### 📊 Business Query Development

Throughout the project, I developed SQL solutions to answer practical business questions by:

- Filtering and refining data
- Aggregating large datasets
- Creating summary reports
- Combining multiple tables through relational joins
- Transforming raw data into actionable insights

---

## 🎯 Key Deliverables

✅ Database Schema Design  
✅ SQL Query Development  
✅ Multi-Table Join Operations  
✅ Data Aggregation & Reporting  
✅ Geographic & Demographic Analysis  
✅ Business Insight Generation  

---

## 📖 Data Analysis with SQL

A key focus of this project was learning how SQL can be used to transform large datasets into meaningful information. Through querying, filtering, grouping, and joining data, I developed the ability to extract insights that support reporting, analysis, and informed decision-making.

---

## 🔧 Tools & Technologies

- SQL
- PostgreSQL / Supabase
- Northwind Database
- World Database
- Relational Database Design
- Entity Relationship Diagrams (ERD)

---

## 🏆 Skills Showcase

`SQL` • `PostgreSQL` • `Supabase` • `SELECT` • `WHERE` • `ORDER BY` • `GROUP BY` • `HAVING` • `JOINs` • `Database Design` • `ERD` • `Data Analysis` • `Data Modelling` • `Business Intelligence` • `Relational Databases`

---

⭐ This project demonstrates my ability to design relational databases, write efficient SQL queries, analyse complex datasets, and transform raw data into meaningful business insights.

---

## 📸 Northwind DB

-  📘 Sales Volume Breakdown
The sales department wants to analyze how much of each product was ordered and at what price.
➡️ Write a SQL query to retrieve all products with their prices and the quantity ordered for each product.
```
SELECT productname, price, SUM (quantity) AS TOTAL_QUANTITY
FROM products P
LEFT JOIN order_details OD
ON P.productid = OD.productid
GROUP BY 1,2
ORDER BY 3 DESC;
```

-  📘 International Customers Targeting (USA & UK)
The marketing team is preparing campaigns for customers in the USA and UK.
➡️ Write a SQL query to retrieve all columns from the Customers table where the Country is either 'USA' or 'UK'.
```
SELECT * 
FROM customers
WHERE country IN ('USA', 'UK');
```

-  📘 Supply Chain Overview Report
Your manager wants to see the product name, its category, and the name of its supplier all in one report.
➡️ Write a SQL query to retrieve the Product Name, Category Name, and Supplier Name for all products
```
SELECT DISTINCT productname, categoryname, suppliername 
FROM products P
LEFT JOIN categories C
ON P.categoryid = C.categoryid
LEFT JOIN suppliers S
ON P.supplierid = S.supplierid;
```

## 📸 World DB

- 📘 Capital Cities Population Comparison: Scenario: A statistical analysis firm is examining population distributions between capital cities worldwide. You're tasked with comparing the populations of capital cities from different countries to identify trends and patterns in urban demographics.
```
SELECT C.Name AS Capital_City, C.Population AS Population, CO.Name AS Country 
FROM city C 
INNER JOIN country CO ON C.CountryCode = CO.Code 
WHERE CO.Capital IN (SELECT DISTINCT capital FROM country) 
ORDER BY 3 DESC;
```

-  📘 New Year Promotion: Featuring Cities with 'New : Scenario: In anticipation of the upcoming New Year, your travel agency is gearing up for a special promotion featuring cities with names including the word 'New'. You're tasked with swiftly compiling a list of all cities from around the world. This curated selection will be essential in creating promotional materials and enticing travellers with exciting destinations to kick off the New Year in style.
```
SELECT name AS CITY_NAME
FROM city
WHERE name ILIKE '%New%';
```

-  📘 Display Columns with Limit (Rows 31-40): Scenario: A market research firm requires detailed information on cities beyond the top rankings for a comprehensive analysis. You're tasked with providing data on cities ranked between 31st and 40th by population to ensure a thorough understanding of urban demographics.
```
SELECT name AS COUNTRY_NAME, population 
FROM country 
ORDER BY population DESC 
LIMIT 10 OFFSET 30;
```
