# Pizza_sales_sql
# Pizza Sales Analysis Project
This project provides an analysis of pizza sales using SQL. The dataset includes information about orders, pizza types, and order details. The goal of the project is to explore sales performance, customer preferences, and revenue generation.
# Project Overview
The pizza_sales project focuses on answering key business questions about pizza sales using SQL queries. The project is divided into three levels: basic, intermediate, and advanced analyses.
# Dataset Description
The project uses four primary tables:
1. order_details: Contains detailed information about each order, including the quantity of pizzas ordered and the associated pizza type.
2. pizzas: Contains information about each pizza, including the pizza name, size, and price.
3. pizzas_type: Defines the categories for each pizza type, such as "Vegetarian", "Non-Vegetarian", etc.
4. order: Contains details about each order, including order ID, customer information, and order date.
# Analysis Breakdown
+ Basic Analysis
1. Total Number of Orders Placed: Retrieve the total count of orders placed from the order table.
2. Total Revenue Generated from Pizza Sales: Calculate the total revenue by summing the price of all pizzas sold, joined with order_details.
3. Highest-Priced Pizza: Identify the most expensive pizza from the pizzas table.
4. Most Common Pizza Size Ordered: Analyze the most frequently ordered pizza size using the pizzas table.
5. Top 5 Most Ordered Pizza Types: Retrieve the top 5 pizza types by quantity from the order_details table.
+ Intermediate Analysis
1. Total Quantity of Each Pizza Category Ordered: Join relevant tables to calculate the total quantity of pizzas ordered per category (e.g., vegetarian, non-vegetarian).
2. Distribution of Orders by Hour of the Day: Analyze the distribution of orders across different hours of the day using the order table.
3. Category-Wise Distribution of Pizzas: Join pizzas_type and order_details to get the distribution of pizzas across different categories.
4.Average Number of Pizzas Ordered per Day: Group orders by date and calculate the average number of pizzas ordered per day.
5. Top 3 Most Ordered Pizza Types Based on Revenue: Identify the top 3 pizza types that generated the most revenue.
+ Advanced Analysis
1. Percentage Contribution of Each Pizza Type to Total Revenue: Calculate the revenue contribution of each pizza type as a percentage of total revenue.
2. Cumulative Revenue Generated Over Time: Analyze how revenue accumulates over time by grouping sales data by date.
3. Top 3 Most Ordered Pizza Types by Revenue for Each Pizza Category: Determine the top 3 most ordered pizza types based on revenue for each category.
# Technologies Used
+ SQL: For querying and analyzing data.
+ Database: (Specify the database you're using, e.g., MySQL, PostgreSQL).
# Future Enhancements
+ Integrating the analysis with a visualization tool such as Power BI or Tableau.
+ Adding more advanced analysis, such as customer segmentation and trend forecasting.





















