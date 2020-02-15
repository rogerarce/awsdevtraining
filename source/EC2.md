# EC2 Elastic Compute Cloud

## Pricing

- On Demand
    - pay fixed rate by hour
- Reserve
    - capacity reservation
    - by terms
- Spot
    - bid whatever price you want for instance capacity
- Dedicated Hosts
    - physical ec2 server dedicated
    - `reduce costs`

### Pricing Use Cases

- On Demand
    - low cost and flexibility without up-front payment
    - shorterm, spiky
    - apps for development or tested
- Reserved Instances
    - steady state or predictable usage
    - apps that require `reserved capacity`
    - available up-front payment
        - standar RI's (up to 75% off on-demand)
        - convertible RI's (up to 54% off on-demand)
        - scheduled RI's
- Spot Instances
    - apps with flexible start and end times
    - apps are feasible at very low compute prices
- Dedicated Hosts
    - regulatory requirements, multitenant virtualization
    - great for licensing
    - purchase On-Demand
    - purchase on RI'S

### EC2 Instance Types

- F I G H T D R M C P X
- `Fight Dr.McPx`

| Family | Specialty | Use case |
|--------|-----------|----------|
| F1     | Field Programmable Gate Array | geonomics research, finance analytics |
| I3 | High Speed Storage
| G3 | Graphics Intensive
| H1 | High Disk Throughput
| T2 | Lowest Cost General Purpose
| D2 | Dense Storage
| R4 | Memory Optimized
| M5 | Main choice for general purpose apps
| C5 | Compute
| P3 | Graphics (think pics)
| X1 | Extreme Memory


## EBS Elastic Block Storage
- virtual disk
- create storage volumes & attach to ec2
- placed in specific AZ
- disk in cloud attached to ec2
- `root device volume`


### EBS Types
- General Purpose (SSD GP2)
    - balance both price and performance
    - ratio of 3 IOPS per gb
- Provisioned IOPS SSD (IO1)
    - use for >= 10,000 IOPS
    - designed for I/O intensive applications such as large SQL or NoSQL database
    - can provision 20,000 IOPS
- Throughput Optimized HDD (ST1)
    - Big Data
    - Data warehouse
    - Log processing
    - Cannot be a boot volume
- Cold HDD (SC1)
    - low cost storage
    - file server
    - can't boot volumne
- Magnetic (Standard)
    - low cost per gb of all ebs
    - bootable
    - ideal fork workloads

## Exam Tips

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