# AWS Databases Summary

- RDS: relational database, great for OLTP (online transaction processing)
    - AWS Offerings: PostgreSQL, MySQL, Oracle, Aurora
    - No horizontal scaling
- DynamoDB: NoSQL database
    - Managed database, key value store, document database
    - Fully serverless
- ElasticCache: in memory database
    - Offering: Redis, Memcached
    - Used for caching
- Redshift: OLAP (online analytics processing)
    - Used for data warehousing, data lakes, analytics queries
    - Has to be provision in advanced (like most of the RDS databases)
- Neptune: graph database
- DMS (Database Migration Service): used to move data from one database to another
-DocumentDB: managed MongoDB database for AWS