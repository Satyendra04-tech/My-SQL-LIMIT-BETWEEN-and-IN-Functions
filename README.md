# Hello all, I am sharing how to use LIMIT, BETWEEN and IN functions in SQL  

## LIMIT  
### LIMIT command allows us to limit the number of rows returned for a query.  
### It is useful when not wanting to return every single row in a table. 
### LIMIT also become useful in combination with ORDER BY.  
### Limit is the last command to be executed.  

* Syntax =  
```
SELECT * FROM table1
ORDER BY column1 ASC
LIMIT 5
```  
This code will show only top 5 rows after sorting the column1 in ascending order of table1.  

### Examples  

#### Suppose we have a table T1 which has columns named customer_id, amount and payment_date. 

1. Select only those customer_id which has done any payment and show recent 5 transactions.
```
SELECT * FROM t2
WHERE amount != 0.00
ORDER BY payment_date
LIMIT 5;
```  

2. We want to reward our 1st 10 paying customers. What are the customer IDs of the 1st 10 customers who created a payment.   
```
SELECT * FROM t2
ORDER BY payment_date
LIMIT 10;
```  
