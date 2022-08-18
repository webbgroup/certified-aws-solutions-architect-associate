# AWS ElastiCache

- ElastiCache is a managed cache offering which supports Redis and Memcached
- Caches are in-memory databases with high performance and low latency
- The role of a cache is to reduce load from a database by caching query results
- It also can help make an application stateless by storing the application state in memory
- Provides:
    - Write scaling using sharding
    - Read scaling using Read Replicas
    - Multi AZ with Failover Capability
- Since it is a managed solution, AWS takes care of OS maintenance, patching, optimization, setup, 
monitoring, failure recovery and backups

## ElastiCache Solution Architecture 

### DB Cache

- Application queries the ElastiCache first. If no data is available for the query (cache miss), the application gets the data from RDS and stores it into the cache
- Caching helps relieve the load from the database
- Cache must have an invalidation strategy to make sure only the most current data is stored in the cache

### User Session Store

- Uses logs into the application
- The application writes the session data to the cache
- The session data can be reused by other instance of he back-end

## Redis vs Memcached

| Redis                                                   | Memcached                                   |
|---------------------------------------------------------|---------------------------------------------|
| Multi AZ with auto-failover                             | Multi-node for partitioning data (sharding) |
| Read replicas to scale reads and have high availability | Non persistent                              |
| Data durability and AOF persistance                     | No backup and restore                       |
| Backup and restore features                             | Multi-threaded architecture                 |

## ElastiCache Security

- All caches in ElastiCache:
    - Support SSL in flight encryption
    - **Do not support IAM authentication**
    - IAM policies on ElastiCache are only used for AWS API-level security
- Redis AUTH
    - We can set a password/token when we create a Redis cluster
    - This is an extra layer of security on top of the security groups
- Memcached
    - Supports SASL-based authentication

## Caching Patterns

- Lazy loading: all the reads are cached, data can become stale in cache
- Write Through: adds/updates of data are cached when written to the database
- Session Store: store temporary session data in cache using TTL features


##
Important ports:

 - FTP: 21

 - SSH: 22

 - SFTP: 22 (same as SSH)

 - HTTP: 80

 - HTTPS: 443

vs RDS Databases ports:

 - PostgreSQL: 5432

 - MySQL: 3306

 - Oracle RDS: 1521

 - MSSQL Server: 1433

 - MariaDB: 3306 (same as MySQL)

 - Aurora: 5432 (if PostgreSQL compatible) or 3306 (if MySQL compatible)


Don't stress out on remember those, just read that list once today and once before going into the exam and you should be all set :)

Remember, you should just be able to differentiate an "Important Port" vs an "RDS database Port".