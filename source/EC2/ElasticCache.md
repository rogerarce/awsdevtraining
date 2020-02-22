# ElastiCache (in-memory cache)

- A web server that makes it easy to.
    - Deploy
    - Scale
    - Operate
    - Scare
- Usage:
    - improve latency & throughput for read-heavy apps.
    - improve compute workloads.
    - improves app performance by storing critical pieces
    - low-latency
    - cache information may include results of
        - I/O-intensive db queries.
        - computationally-intensive calculations.
## Types of ElastiCache
 
- ### Memcached
    - widely adopted memory object caching system.
    - elastiCache is protocol compliant with memcached.
    - `does not` support `AZ redundancy`.
- ### Redis
    - popular open-source in-memory
    - key-value store
    - supported structures
        - sets
        - lists.
    - elasticache supports mater/slave replication & multi-az
      which can be used to achieve `cross AZ redundancy`.
- ### Difference in Practice:
    - Redis
        - replication and persistence features of redis.
        - elasticache manage redis more as 
            - relational database
        - redis elasticache clusters are manage as
            - stateful entities
                - includes failover (similar to rds failover).
        - use cases
            - more advance data types
            - does sorting & ranking
            - if persistence of key store is important.
            - multiple aws az
    - Memcached
        - designed as pure caching solution (no persistence)
        - elasticache manage nodes as pool that can grow and shrink
            - similar to ec2 auto scaling group.
        - individual nodes are expendable
        - elastic cache provides additional capabilities such as
            - automatic node replacement
            - auto discover.
        - use cases
            - object caching
            - simple caching
            - running large cache nodes
            - horizontal scale.
    
