# Brazilian E-Commerce Public Dataset by Olist

This is a Brazilian ecommerce public dataset of orders made at Olist Store. The dataset has information of 100k orders from 2016 to 2018 made at multiple marketplaces in Brazil. Its features allows viewing an order from multiple dimensions: from order status, price, payment and freight performance to customer location, product attributes and finally reviews written by customers. It has also been included a geolocation dataset that relates Brazilian zip codes to Lat/Lng coordinates.

After a customer purchases the product from Olist Store a seller gets notified to fulfill that order. Once the customer receives the product, or the estimated delivery date is due, the customer gets a satisfaction survey by email where he can give a note for the purchase experience and write down some comments.
### AIMS
Model data with Postgres Database.

Build an ETL pipeline using Python.

## DATA SCHEMA
This data is divided in multiple datasets.
The aim of this project is to create tables in python and model data using postgres.

## Code Errors faced and solutions

### 1. When loading the orders table data into postgres I got the error below
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
~\AppData\Local\Temp/ipykernel_6532/3623735665.py in <module>
      1 for i, row in order_items.iterrows():
      2     #print(list(row))
----> 3     cur.execute(orderitems_table_insert, list(row))
      4 
      5 #conn.commit()

TypeError: not all arguments converted during string formatting

### 2. When loading the orders table data into postgres I got the error below.
---------------------------------------------------------------------------
DatatypeMismatch                          Traceback (most recent call last)
~\AppData\Local\Temp/ipykernel_6532/2693653344.py in <module>
      1 for i, row in orders.iterrows():
      2     #print(list(row))
----> 3     cur.execute(orders_table_insert, list(row))
      4 
      5 #conn.commit()

DatatypeMismatch: column "order_delivered_carrier_date" is of type timestamp without time zone but expression is of type double precision
LINE 10: ...d', '2017-04-11 12:22:08', '2017-04-13 13:25:17', 'NaN'::flo...
                                                              ^
HINT:  You will need to rewrite or cast the expression.
