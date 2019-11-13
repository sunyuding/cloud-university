# Database
# SQL
## SQL Query
- A JOIN clause is used to combine rows from two or more tables, based on a related column between them.
- (INNER) JOIN: Returns records that have matching values in both tables
- LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
- RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
- FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table
Data mining 

## Schema 
Schema design


## 1NF, 2NF, 3NF and 4NF
Database Normal Forms

# NoSQL
## Wide column store
Google introduced [Bigtable](http://www.read.seas.harvard.edu/~kohler/class/cs239-w08/chang06bigtable.pdf) as the first wide column store, which influenced the open-source **HBase** often-used in the Hadoop ecosystem, and **Cassandra** from Facebook. 

## SQL vs NoSQL
|SQL                    |NoSQL                          |
|-----------------------|-------------------------------|
|RELATIONAL DATABASE MANAGEMENT SYSTEM (RDBMS)	|Non-relational or distributed database system.|
|These databases have fixed or static or predefined schema	|They have dynamic schema|
|These databases are not suited for hierarchical data storage.|These databases are best suited for hierarchical data storage.|
|These databases are best suited for complex queries|These databases are not so good for complex queries|
|Verticlly Scalable     |Horizontally scalable|

# Scalability
## SQL
- master-slave replication (read from slaves, write to master)
- upgrade your master server by adding RAM, RAM and more RAM
- Federation
- sharding
- denormalization
- SQL tuning

## NoSQL
- switch to a better and easier to scale NoSQL database like MongoDB
- dataset-joins
## cache

# Reference
- [ ] [w3schools SQL Tutorial](https://www.w3schools.com/sql/)
- [ ] [Top SQL Interview Questions You must Prepare For 2019 | Edureka
](https://www.edureka.co/blog/interview-questions/sql-interview-questions/)
- [x] [SQL and NoSQL Databases](https://github.com/UWCoffeeNCode/resources/wiki/SQL-and-NoSQL-Databases) 
- [ ] [Database Normalization - 1NF, 2NF, 3NF and 4NF (video)](https://www.youtube.com/watch?v=UrYLYV7WSHM)
- [x] [Difference between SQL and NoSQL](https://www.geeksforgeeks.org/difference-between-sql-and-nosql/)
- [x] [Database](http://www.lecloud.net/post/7994751381/scalability-for-dummies-part-2-database)
- [ ] [NoSQL Patterns](http://horicky.blogspot.com/2009/11/nosql-patterns.html)
- [x] [system-design-primer](https://github.com/donnemartin/system-design-primer#database)
- [ ] [A Quick-Start Tutorial on Relational Database Design](https://www.ntu.edu.sg/home/ehchua/programming/sql/Relational_Database_Design.html)