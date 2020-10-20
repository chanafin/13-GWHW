ETL into SalesForce

The goal of this project is to Extract Data from a MYSQL database, Transform the data as to ensure that it Lands correctly in SalesForce. In this MYSQL dataset, there are 3 primary keys, Class, Student and Staff, that must be linked to the corresponding foreign keys, so the process will be repeated 3 times.


After importing the dependencies, the first goal is to create an engine and connect to the MYSQL database. Then the data needed is extracted using read_sql. The data is then transformed into a list of dictionaries using to_dict. 

A SalesForce record is created by looping through the dictionary list and creating a new iterrated dictionary called 'record' that is landed into SalesForce using a try/except. 

Once the primary key is landed in SalesForce, an empty list is created. Then we run a sf.query_all_iter from the SalesForce table that has just been created. The crux of the exercise and the next step here is to re-extract the necessary columns, including the ID number given by SalesForce to each 'record' once it landed. With these columns identified, we then extract the Class Table from the MySQL database. Because Course and Class both have 'ID_Course' as column, they can now be left merged. The class table now has the unique SF ID and once the 'Start Date' and 'End Date' Columns are converted to dates. The modified Class Table  table will now land in SalesForce and will be successfully linked to the Primary Course Table. Repeat these steps 2 more times for Staff/Staff Assignment & Student / Class Participant.
