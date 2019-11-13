# Amazon Relational Database Services (RDS)
- MySQL
- Amazon Aurora
- SQL Server
- PostgreSQL
- MariaDB
- Oracle

No charge for backup storage of up to 100% of database storage

750 instance-hours of RDS is available in the free-tier in the 1st year as well as 20GB of SSD general purpose storage and 20 GB of backup storage free per month.

What does Amazon manage on my behalf for RDS?
- Provisioning Infrastructure Capacity, Installing Software, replication of db across multiple AZ's (multi-AZ deployment), backups, patching software, and failovers are managed on behalf of RDS users.

It takes away the time consuming tasks of hardware provisioning, setup, patching, and backups so you can focus on your applications.

When using Amazon RDS Multi-AZ, how can you offload read requests from the primary?
- Add a read replica DB instance, and configure the client's application logic to use a read-replica.
- Use [ElastiCache](https://aws.amazon.com/elasticache/) to cache frequently used data. Update the application logic to read/write from the cache.

Q. If there are multiple Read Replicas for a primary Amazon RDS DB instance and one of them is promoted, what happens to the rest of the Read Replicas?
- There is no change in their behavior

Q. Your team is building an order processing system that will span multiple Availability Zones. During testing, the team wants to test how the application will react to a database failover. How can you enable this type of test?
- Reboot the primary instance from the Amazon RDS console.

Question: What Amazon Relational Database Service (Amazon RDS) feature provides the high availability for your database?
- A. Regular maintenance windows
- B. Security groups
- C. Automated backups
- D. Multi-AZ deployment

Answer: D. Multi-AZ deployment uses synchronous replication to a different Availability Zone so that operations can continue on the replica if the master database stops responding forb any reason. Automated backups provide **disaster recovery**, not high availability. Security groups, while important, have no effect on availability. Maintenance windows are actually times when the database may not be available.

Question: What administrative tasks are handled by AWS for Amazon Relational Database Service (Amazon RDS) databases? (Choose 3 answers)
- A. Regular backups of the database
- B. Deploying virtual infrastructure
- C. Deploying the schema (for example, tables and stored procedures)
- D. Patching the operating system and database software
- E. Setting up non-admin database accounts and privileges

Answer: A, B, and D. Amazon RDS will launch Amazon Elastic Compute Cloud (Amazon EC2) instances, install the database software, handle all patching, and perform regular backups. Anything within the database software (schema, user accounts, and so on) is the responsibility of the customer.


