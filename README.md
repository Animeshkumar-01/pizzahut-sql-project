# PIZZA HUT Analysis SQL PROJECT
## PROJECT OVERVIEW

### PROJECT TITLE: PIZZA HUT Sales Analysis

Database:

This project is a SQL-based sales analysis project built using a PizzaHut sales dataset.
The main objective of this project is to demonstrate core SQL concepts such as database
creation, data insertion, joins, aggregations, and analytical querying on a real-world
business dataset.

## OBJECTIVES

1. Set up a PizzaHut sales database using multiple related tables.
2. Load data into SQL tables using CSV files and SQL INSERT statements.
3. Perform data analysis using SQL queries to answer business questions.
4. Analyze revenue, order trends, pizza categories, and popular pizza sizes.
5. Strengthen understanding of joins, aggregate functions, and grouping operations.

## Data Analysis & Findings

### Q1. Retrive the total number of order placed. 

```sql
   SELECT 
    COUNT(order_id)
  FROM
    orders;

 Q2. Calculate the total revenue generated from pizza sales. 


SELECT 
    SUM(quantity) AS total_pizza_sold
FROM
    order_details;

  Q3. Calculate the total revenue generated from pizza sales using pizza price and quantity sold. 


SELECT 
    ROUND(SUM(order_details.quantity * pizzas.price),
            2) AS total_revenue
FROM
    order_details
        JOIN
    pizzas ON pizzas.pizza_id = order_details.pizza_id;
