## SQL injection UNION attacks 

- When an application is vulnerable to SQL injection and the results of the query are returned within the application's responses, the `UNION` keyword can be used to retrieve data from other tables within the database. 
- The `UNION` keyword lets you execute one or more additional `SELECT` queries and append the results to the original query 
- For example: `SELECT a, b FROM table1 UNION SELECT c, d FROM table2`
- For `UNION` attack 
