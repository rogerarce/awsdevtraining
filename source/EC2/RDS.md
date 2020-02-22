# RDS (Relational Database System)

### AWS Available RDS
- SQL Server
- Oracle
- MySQL Server
- PostgreSQL
- Aurora
- MariaDB

### Non Relational Database
- Database
    - Collection (Table)
    - Document (Row)
    - Key Value Pair (Fields)

### Data Warehousing
- Used for business intelligence
    - Cognos
    - Jaspersoft
    - SQL Server
    - Reporting Services
    - Oracle Hyperion
    - SAP NetWeaver
- Use to pull large comxplex data sets.

### OLTP VS OALP
- Online Transaction Processing (OLTP)
    - E.g: Order number
    - Simple transaction
    - Frequently happens
- Online Analytics Processing (OLAP)
    - Complex
    - Pull large number of records
    - Not Frequent

### Elasticache
- web service
- makes it easy to deploy, operate and scale in-memory cache in cloud.
- improves performance of web applications
- AWS ElastiCache supports
    - Memcached
    - Redis

### Multi-AZ Replicas

- Backups.
    - Automated Backups
        - allows any point recovery within retention period windows
        - enabled by default
        - free stored in s3
        - database size = s3 size
    - Snapshot Backups
        - snapshot of database
        - done manually
        - stored after db instance delete
    - Restore Backup
        - new rds instance
        - restore from snapshots
        - new endpoint
    - Encryption
        - supported by default
        - encryption done via KMS
        - underlying store is encrypted.
- Multi-AZ (Availability Zone)
    - `FOR DISASTER RECOVER ONLY!.`
    - not for improving performance (refer to read replicate for performance).
    - allows exact copy of production database in another AZ.
    - automatic synchronized to stand by database(s).
    - Database maintenance
        - db instance failure or az failure.
        - aws rds will failover to the standby database
        - automatic quick resume of operation (without administrative operation)
    - Multi-AZ Databases
        - SQL Server
        - Oracle
        - MySQL Server
        - PostgreSQL
        - MariaDB
- Read Replica
    - read from replicate
    - spread load to one or more replica
    - allows to read replica to another AZ.
    - allows to read replicate to another region.
    - allows read-only copy of your production database.
        - by using `asynchronous` replication from primary RDS instance.
    - use read replicas primarily for very read-heavy db workloads.
    - available in 
        - MySQL
        - PostgreSQL
        - MariaDB
        - Aurora
    - use for scaling, `not` for Disaster Recover.
    - must have automatic backup turn on to deploy read replica.
    - can have up to 5 read replica copies of any database.
    - can have read replicas of read replica (watch out for latency).
    - each read replica has its own DNS end point.
    - can have read replica that have multi-az
    - can create read replica of Multi-AZ source database.
    - read replica can be `promoted` to be their own database (breaks the replication).
        - `create copy before promoting`.
    - can have read replica in a second region.
    


### Notes
- EC2 Instances and RDS should be in same security group
    - Whitelisting security group
        - go to RDS section
        - select database instance you want to connect
        - select the security group under the selected database instance
        - once navigated to security group
        - select the `Inbound` from security group
        - edit the `Inbound` rules
        - add new type & select MYSQL for port 3306
        - from the source type the name of security group to want to while list
        - or the security group of the ec2 instance & click save
