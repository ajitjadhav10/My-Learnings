#### We can create a dataframe from a table using either SQL or DATAFRAME API in spark

example:
1. Creating a dataframe using SQL from a table called 'products'

SELECT name, price
FROM products
WHERE prics>200
ORDER BY price

This will return a data frame

<img src="Apache%20Spark/image_1.png">
