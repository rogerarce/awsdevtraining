# Exam Tips

## IAM
- Least Privilege
- Create Groups
    - assign users to groups
    -
- Secret Access Key
    - seen only once if not saved.
    - can be deleted and generated.
    - create one key per user/developer.
- CLI is available in personal PC
    - 
### Critical Terms for Exam
- Users
    - end users
- Groups
    - Collection of `Users`
- Role
    - Set to define
- Policy
    - defines the permission of a users, groups, role.

## EC2

### Pricing

- On Demand
    - allows to pay a fix rate by hour (or by second) with no commitment.
- Reserved
    - provides with capaticy reservation, and offer significant discount on hourly charges for instance
    - 1 Year or 3 Year Terms.
- Spot
    - enables to bid whatever price you want for instance capacity, providing
    - for even greater savings if your applications have flexible start and end times.
- Dedicated Hosts
    - Physical EC2 server dedicated for your use.
    - If terminated by AWS
        - no charge for partial hour of usage.
    - If self termination
        - charge for complete hours in which the instance ran.
- `FIGHT DR MC PX` Instance Types
- `EBS Volume Types`
    - `SSD`
        - General Purpose
        - Provisioned IOPS SSD
    - `Magnetic`
        - Throughput Optiomized HDD
            - Low cost HDD Volume
            - Designed for frequently accessed
            - Throughput-intensive workloads
        - Cold HDD
            - Lowest cost HDD Volume
            - Less frequently accessed workloads
        - Magnetic
            - Previous Generation
            - `Can be a boot volume`

## ELB
- 3 Types of Load Balancer
    - Application Load Balancer
    - Network Load Balancer
    - Classic Load Balancer
- 504 Error means gateway has timeout
    - The application is not responding within the idle timeout period.
    - Trouble shoot
        - Trouble shoot the application
        - Could be `web server` or `database server`.
- If IPv4 is needed of the application end user
    - look for `X-Forwaded-For` in the request header.

## ElastiCache
- Example scenario
    - A database is under a lot of stress/load
        - which service you should use to alleviate this?
    
    - answer:
        - `elasticache if`
            - database is read-heavy
            - not prone to frequent change.
        - `redshift if`
            - database is stress because management keep running OLAP transactions on it.
- Use `Memcached` if
    - primary goal is object caching
    - want to keep things simple
    - want to scale cache horizontally
- Use `Redis` if
    - advance data types
    - doing sorting & ranking
    - data persistence
    - multi-az
    - needs pub/sub
    - if doing leaderboard.


