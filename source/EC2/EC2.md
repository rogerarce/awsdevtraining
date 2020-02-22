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
- Throughput Optimized HDD (ST1) (Magnetic)
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

### EC2 with S3 Roles
- Apply s3 iam role to EC2 instance

### EC2 Encrypt and EBS Volume Attached to EC2 Instance
- encrypt volume.
- mounting volume
    - `lsblk` -> `xvdf` (new volume)
    - `file -s /dev/xvdf` -> (result) `/dev/xvdf: data`
    - `mkfs -t ext4 /dev/xvdf`
        - type of file systems
            - ext4
    - `mkdir filesystem`
    - `mount /dev/xvdf /filesystem` (mounting xvdf disk to filesystem)
- unmount volume
    - `unmount -d /dev/vxdf`
- create snapshot
    - select actions button
    - select create snapshot
- create volume from snapshot
    - select snapshot -> actions -> create volume
    - follow steps on `mounting volume`
    - exclude third step.
- create unencrypted snapshot to encrypted snapshot
    - create a copy of the unencrypted snapshot.
    - and select the encrypt snapshot option.

### EC2 Summary
- ON Demand
- Reserved
- Spot
- Dedicated Hosts