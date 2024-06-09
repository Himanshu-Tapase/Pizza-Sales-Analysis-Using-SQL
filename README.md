# SQL-Projects-for-Data-Analysis

PIZZAHUT  SALES  ANALYSIS  USING  SQL  


Basics Questions 
1. Determine the overall count of orders made.

Query: SELECT COUNT(order_id) FROM orders;

Description: This query fetches the total count of orders made by counting the number of rows in the orders table.

Output: The total count of orders made.

2. Compute the total income derived from selling pizzas.
   
Query: SELECT ROUND(SUM(order_details.quantity * pizzas.price), 2) AS total_income FROM order_details INNER JOIN pizzas ON pizzas.pizza_id = order_details.pizza_id;

Description: This query calculates the total income by summing up the product of the quantity of each pizza and its price, and then rounding the result to two decimal places.

Output: The total income derived from selling pizzas.

3. Find out the pizza with the highest price tag.
   
Query: SELECT pizza_types.name, pizzas.price FROM pizza_types INNER JOIN pizzas ON pizza_types.pizza_type_id = pizzas.pizza_type_id ORDER BY pizzas.price DESC LIMIT 1;

Description: This query fetches the name and price of the pizza with the highest price tag by joining the pizza_types and pizzas tables and ordering the results by price in descending order.

Output: The name and price of the pizza with the highest price tag.

4. Determine the pizza size that is most frequently ordered.
   
Query: SELECT pizzas.size, COUNT(order_details.order_details_id) AS order_count FROM pizzas INNER JOIN order_details ON pizzas.pizza_id = order_details.pizza_id GROUP BY pizzas.size ORDER BY order_count DESC;

Description: This query determines the pizza size that is most frequently ordered by counting the number of orders for each pizza size and ordering the results in descending order.

Output: The pizza size that is most frequently ordered along with its order count.

5. Provide a list of the five most popular pizza varieties, accompanied by their order quantities.
   
Query: SELECT pizza_types.name, SUM(order_details.quantity) AS quantity FROM pizza_types JOIN pizzas ON pizza_types.pizza_type_id = pizzas.pizza_type_id JOIN order_details ON order_details.pizza_id = pizzas.pizza_id GROUP BY pizza_types.name ORDER BY quantity DESC LIMIT 5;

Description: This query fetches the names of the five most popular pizza varieties and their order quantities by joining the pizza_types, pizzas, and order_details tables and grouping the results by pizza variety.

Output: The names of the five most popular pizza varieties along with their order quantities.

