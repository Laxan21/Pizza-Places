# PizzaPlaces

```
SELECT * 
FROM order_details
WHERE 
  order_details_id <= 10
```


```
SELECT * 
FROM pizzas
WHERE  
  size = "L"
ORDER BY price DESC 
```

```
SELECT *
FROM pizza_types
WHERE ingredients LIKE '%Peppers%' 
```

```
SELECT date, COUNT(*)
FROM orders
GROUP BY date
HAVING COUNT(*) > 100
```

```
SELECT *
FROM order_details
INNER JOIN pizzas
  ON order_details.pizza_id = pizzas.pizza_id
LIMIT 10
```

```
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
![Untitled picture1](https://user-images.githubusercontent.com/104281046/213899657-0c27bbd3-1c93-4ec3-beb5-2b2a4828644e.png)
