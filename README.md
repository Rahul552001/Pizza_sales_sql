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
``` SQL
select count(order_id) as Total_number from orders 
```
2. Total Revenue Generated from Pizza Sales: Calculate the total revenue by summing the price of all pizzas sold, joined with order_details.
``` SQL
select round(sum((order_details.quantity*pizzas.price)),2) as Total_revenue from order_details
join pizzas
on order_details.pizza_id = pizzas.pizza_id;
```
3. Highest-Priced Pizza: Identify the most expensive pizza from the pizzas table.
``` SQL
select pizza_types.name, pizzas.price 
from pizza_types 
join pizzas on pizza_types.pizza_type_id = pizzas.pizza_type_id
order by pizzas.price desc limit 1;
```
4. Most Common Pizza Size Ordered: Analyze the most frequently ordered pizza size using the pizzas table.
``` SQL
select  pizzas.size , count(order_details.order_details_id) as order_count
from pizzas  
join order_details on order_details.pizza_id = pizzas.pizza_id 
group by pizzas.size order by order_count  desc limit 1;
```
5. Top 5 Most Ordered Pizza Types: Retrieve the top 5 pizza types by quantity from the order_details table.
``` SQL
select  pizza_types.name, count(order_details.quantity) as total_count 
from pizzas  join pizza_types
on pizza_types.pizza_type_id = pizzas.pizza_type_id
join order_details 
on order_details.pizza_id = pizzas.pizza_id
group by pizza_types.name  order by total_count desc limit 5;
```
+ Intermediate Analysis
1. Total Quantity of Each Pizza Category Ordered: Join relevant tables to calculate the total quantity of pizzas ordered per category (e.g., vegetarian, non-vegetarian).
``` SQL
select pizza_types.category , count(order_details.quantity) as quantity
from pizzas join order_details
on pizzas.pizza_id = order_details.pizza_id
join pizza_types
on pizzas.pizza_type_id =pizza_types.pizza_type_id
group by pizza_types.category ;
```
2. Distribution of Orders by Hour of the Day: Analyze the distribution of orders across different hours of the day using the order table.
``` SQL
select hour(order_time) as Time  , count(orders.order_id) as Total
from orders
group by hour(order_time) ;
```
3. Category-Wise Distribution of Pizzas: Join pizzas_type and order_details to get the distribution of pizzas across different categories.
``` SQL
select category, count(name) as count  
from pizza_types
group by category order by count ;
```
4.Average Number of Pizzas Ordered per Day: Group orders by date and calculate the average number of pizzas ordered per day.
``` SQL
select round(avg(quantity),0) as avg_order  from 

(select orders.order_date, sum(order_details.quantity) as quantity
from orders join order_details
on orders.order_id = order_details.order_id
group by orders.order_date)  as order_quantity;
```
5. Top 3 Most Ordered Pizza Types Based on Revenue: Identify the top 3 pizza types that generated the most revenue.
``` SQL
select pizza_types.name, sum(order_details.quantity*pizzas.price) as revenue  from
pizzas join pizza_types
on pizza_types.pizza_type_id = pizzas.pizza_type_id
join order_details
on order_details.pizza_id=pizzas.pizza_id
group by  pizza_types.name order by revenue desc limit 3;
```
+ Advanced Analysis
1. Percentage Contribution of Each Pizza Type to Total Revenue: Calculate the revenue contribution of each pizza type as a percentage of total revenue.
``` SQL
select pizza_types.category, round (((sum(order_details.quantity*pizzas.price) /
 (select round(sum((order_details.quantity*pizzas.price)),2) as Total_revenue from order_details
join pizzas
on order_details.pizza_id = pizzas.pizza_id) ))*100,2) as revenue  from
pizzas join pizza_types
on pizza_types.pizza_type_id = pizzas.pizza_type_id
join order_details
on order_details.pizza_id=pizzas.pizza_id
group by  pizza_types.category order by revenue;
```
2. Cumulative Revenue Generated Over Time: Analyze how revenue accumulates over time by grouping sales data by date.
``` SQL

```
3. Top 3 Most Ordered Pizza Types by Revenue for Each Pizza Category: Determine the top 3 most ordered pizza types based on revenue for each category.
``` SQL

```
# Technologies Used
+ SQL: For querying and analyzing data.
+ Database: (Specify the database you're using, e.g., MySQL, PostgreSQL).
# Future Enhancements
+ Integrating the analysis with a visualization tool such as Power BI or Tableau.
+ Adding more advanced analysis, such as customer segmentation and trend forecasting.





















