![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.
Query:{"name": "Babelgum"}
Project: {name1: _id:0}


### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.

Query:{"number_of_employees":{$gt:5000}}

Sort:{"number_of_employees":1}

Limit: 20

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.

Sort:
{name:1, founded_year:1,_id:0}
Query:
{"founded_year":{$gte2000,$lte2005}}

### 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

Query:{"ipo.valuation_amount": {$gte:100000000},"founded_year":{$lt:2010}}
sort: {name:1, ipo:1,_id:0}

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.
Query:{"number_of_employees":{$lt:1000},"founded_year":{$lt:2005}}
sort:{"number_of_employess":1}
limit 10


### 6. All the companies that don't include the `partners` field.

Query:{partners: {$exists: false}}

### 7. All the companies that have a null type of value on the `category_code` field.

Query:{category_code:null}

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

Query:{"number_of_employees":{$lte:100, $lt:1000}}
project:{name:1, number_of_employees:1,_id:0}

### 9. Order all the companies by their IPO price in a descending order.

<!-- Your Code Goes Here -->
sort:{"ipo.valuation_amount":-1}

### 10. Retrieve the 10 companies with most employees, order by the `number of employees`

<!-- Your Code Goes Here -->
sort:{number_of_employees:1}
limit 10

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.

<!-- second semester is jan to june right? -->
query:{"founded_month":{$in:[1,2,3,4,5,6]}} 
limit 1000




### 12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000


query:{"acquisitions.price_amount":{$gt:10000000},"founded_year":{$lt:2000}}

### 13. All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.


query:{"acquisition.acquired_year":{$gt:2010}}
project:{name:1,acquisition:1,_id:0}
sort:{"acquisition.price_amount":1}


### 14. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.

sort:{name:1,founded_year:1, _id:0}

### 15. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.


query:{"founded_day":{$in:[1,2,3,4,5,6,7]}}
sort:{"acquisition.price_amount":-1}}
limit 10


### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.

<!-- Your Code Goes Here -->
query: {"category_code":"web", "number_of_employees":{$gt:4000}}
sort: {"nuber_of_employees":1}

### 17. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.

<!-- Your Code Goes Here -->
query:{"acquisitions.price_currency_code":"EUR","acquisitions.price_amount":{$gt:10000000}

### 18. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

<!-- Your Code Goes Here -->
query:{"founded_month":{$in:[1,2,3,4]}} 
project:{name:1,acquisition:1,_id:0}
limit 19

### 19. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

{"acquisition.acquired_year":{$gte:2011},"founded_year":{$gte:2000},"founded_year":{$lte:2010}}