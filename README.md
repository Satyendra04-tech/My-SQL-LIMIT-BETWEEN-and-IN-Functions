# Hello all, I am sharing how to use LIMIT, BETWEEN and IN functions in SQL  

## LIMIT Operator
### a. LIMIT command allows us to limit the number of rows returned for a query.  
### b. It is useful when not wanting to return every single row in a table. 
### c. LIMIT also become useful in combination with ORDER BY.  
### d. Limit is the last command to be executed.  

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

## BETWEEN Operator 
### a. BETWEEN Operator can be used to match a value against a range of value.  
                value BETWEEN low and high
### b. BETWEEN operator is the same as :
               value >= low and value <= high  
               Value between low and high
### c. We can also combine BETWEEN and NOT operator.  
                Value NOT BETWEEN low and high  
### d. NOT BETWEEN operator is same as :
                value < low OR  value > high
                value NOT BETWEEN low and high

### e. BETWEEN can also be used with dates. But we need to format dates in ISO 8601 standard format which is 'YYYY-MM-DD'.

* Syntax of BETWEEN operator and NOT BETWEEN operator =
```
SELECT * FROM table1
WHERE column1 BETWEEN 8 AND 9;
```  
```
SELECT * FROM table1
WHERE column1 NOT BETWEEN 8 AND 9;
```
### Examples 

#### Suppose we have a table T2 which has columns named payment_date.  

1. Get all the payments made between '2007-02-01' and '2007-02-14'.  
``` 
SELECT * FROM t2
WHERE payment_date BETWEEN '2007-02-01' AND '2007-02-15';
```  
Note = SQL will only consider the dates till 00:00 hrs, so if we give end date as '2007-02-14' it will only consider payments done till 2007-02-14 00:00 hrs and payments done between 2007-02-14 00:01 hrs to 2007-02-14 23:59 hrs will not be considered. So to include the payments made till 2007-02-14 23:59 we will give end date as '2007-02-15'.  

## IN Operator
### a. In certain cases we want to check for multiple possible value options, for example if a user's name shows up IN a list of known users.  
### b. We can use IN operator that creates a condition that checks if a value is included in a list of multiple options.  

* Syntax =  
```
SELECT column1 FROM table1
WHERE color IN ('red', 'blue')
```  
This code will print any values which will have red or blue in color column.  

```
SELECT color FROM table1
WHERE color NOT IN ('red', 'blue')
``` 
This code will print any values which will not have red or blue in color column.  

```
SELECT COUNT (*) FROM table1
WHERE amount NOT IN (0.99, 1.98, 1.99)
```
This code will give count of rows whose amount is in 0.99 or 1.98 or 1.99.  

## That's it for the LIMIT, BETWEEN and IN functions, see you in the next chapter !!




