ETL into SalesForce

The goal of this project is to Extract Data from a MYSQL database, Transform the data as to ensure that it Lands correctly in SalesForce. 
After importing the dependencies, the first goal is to create an engine and connect to the MYSQL database. We then Extract the data needed using read_sql. The data is then transformed into a list of dictionaries. A SalesForce record is created by looping through the list and creating a new dictionary that matches the 