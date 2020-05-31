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
