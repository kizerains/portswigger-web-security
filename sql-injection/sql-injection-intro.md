## SQL injection Introduction 

- SQL injection is a web security vulnerability that allows an attakcer to interfere with the queries that an applicayion makes to its database.
- Allows an attacker to view data that they are not normally able to retrieve
- An attack can modify or delete this data, causing persistent changes to the application's content or behaviour 
- An attack can escalte an SQL injection attack to compromise the underlying server or other back-end infeastructure
</br>

### Impact of a successfult SQLi attack? 
- A successful attack can result in unauthorised access to sensitive data, such as passwords, credit card details or personal user information 
</br>

### SQL injection examples
- **Retrieving hidden data**: modify an SQL query to return additional results  
- **Subverting application logic**: change a quert to interfere with the application's logic 
- **UNION attacks**: retrieve data from different database tables 
- **Examining the database**: extract information about the version and structure of the database 
- **Blind SQL injection**: the results of a query you control are not returned in the application's reponse 
</br>

### Retrieving hidden data 
- An example of an SQL query is: `SELECT * FROM products WHERE category = 'Gifts' AND released = 1`
- This SQL uery asks the database to return: 
  - all details (*) 
  - from the products table
  - where the category is 'gifts'
  - and released is '1'
- The 'released = 1' is being used to hide products that are not released. For unreleased products, presumably released = 0.  
- If we were to use this attacks: `https://insecure-website.com/products?category=Gifts'--`
- The SQL query would now look like this: `SELECT * FROM products WHERE category = 'Gifts'--' AND released = 1`
- The double dash is a comment indicator in SQL there removes the reaminder of the query so it no longer includes `AND released = 1`
</br>
