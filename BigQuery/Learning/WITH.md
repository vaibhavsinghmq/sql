## Table infoEDIT DETAILS

**Table** : liquorsalesmock.daily_sales
**Columns** : 
date : DATE
sale_id:INTEGER
product_name:STRING
brand:STRING
quantity_sold:INTEGER
price_per_unit:FLOAT
store_location:STRING

1.  **Total Quantity Sold**: Calculate the total quantity sold for each product.
```
WITH ProductTotals AS(
SELECT product_name, sum(quantity_sold) as total_quantity_sold
FROM `liquorsalesmock.daily_sales`
GROUP BY product_name)
SELECT product_name,total_quantity_sold
FROM ProductTotals
ORDER BY
```
2.  **Store Sales Value**: Determine the total sales value for each store location.
```
WITH TOTALSALES AS(
	SELECT store_location, sum(price_per_unit) AS total_sales
	FROM `liquorsalesmock.daily_sales`
	GROUP BY store_location)
SELECT store_location, total_sales
FROM TOTALSALES
ORDER BY total_sales DESC
```
3.  **Multiple Store Products**: Identify products that have been sold at more than one store location.
```
WITH  GLOBALPRODUCT  AS(
	SELECT  product_name
	FROM  `liquorsalesmock.daily_sales`
	WHERE  quantity_sold  >0
	GROUP  BY  product_name
	HAVING  COUNT(store_location)  >1
)
SELECT  product_name
FROM  GLOBALPRODUCT
ORDER  BY  product_name  ASC
```

4.  **Top Selling Brand**: Discover the brand with the highest sales in terms of value.
```

```

5.  **Average Price per Product**: Calculate the average price per unit for each product.
```

```

6.  **Most Sold Product per Store**: Determine the most sold product in each store location.

```

```
7.  **Brands in Multiple Stores**: Identify brands that are sold in multiple store locations.

```

```
8.  **Products with No Sales**: List products that had zero sales.

```

```
9.  **Stores with Highest Quantity of a Specific Product**: Determine which store sold the highest quantity of "Whiskey A."

```

```
10.  **Brands with Most Unique Products**: Identify which brand has the most unique products on sale.
