# Pizza Places

```
-- first 10 order details id's
SELECT * 
FROM order_details
WHERE 
  order_details_id <= 10
```
![SQL Query 1](https://user-images.githubusercontent.com/104281046/213899813-8754fbfd-7b70-4017-9140-ad1ab0e14751.png)

```
-- selecting large pizza options ordered by the most expensive
SELECT * 
FROM pizzas
WHERE  
  size = "L"
ORDER BY price DESC 
```
![SQL Query 2](https://user-images.githubusercontent.com/104281046/213899980-7f48b5b8-fd49-4f2c-84d1-15a1abb85e3b.png)
```
-- chose pizzas whose ingredients have chicken
SELECT *
FROM pizza_types
WHERE ingredients LIKE '%Chicken%' 
```
![SQL Query 3](https://user-images.githubusercontent.com/104281046/213900118-ef7cbdb0-11de-40d4-ab16-5c02c2b0d289.png)
```
-- dates that had more than 100 pizzas ordered
SELECT date, COUNT(*)
FROM orders
GROUP BY date
HAVING COUNT(*) > 100
```
![SQL Query 4](https://user-images.githubusercontent.com/104281046/213899922-921399c3-ffa7-4537-bbed-c7dfccceff4b.png)
```
-- inner joined the order_details and pizzas tables
SELECT *
FROM order_details
INNER JOIN pizzas
  ON order_details.pizza_id = pizzas.pizza_id
LIMIT 10
```
![SQL Query 5](https://user-images.githubusercontent.com/104281046/213899927-eb941789-485e-4bef-a472-df23c5a80b61.png)
```
-- determined the top 5 pizzas with the highest sales
SELECT order_details.pizza_id, 
  pizzas.price, 
  SUM(order_details.quantity) AS total_ordered, 
  ROUND(SUM(pizzas.price*order_details.quantity),2) as Sales
FROM order_details
LEFT JOIN pizzas
  ON order_details.pizza_id = pizzas.pizza_id 
GROUP BY 
  order_details.pizza_id
ORDER BY Sales DESC
LIMIT 5
```




![SQL Query 6](https://user-images.githubusercontent.com/104281046/213899929-783ab1f4-b8ad-4bef-9e3f-c43279e7d3e2.png)
