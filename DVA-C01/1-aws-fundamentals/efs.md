# EFS - Elastic File System

- It is a managed NFS (network file system). It can be mounted on many EC2 instances
- EFS works with EC2 instances from multiple AZs
- Highly available, scalable
- It is expansive compared to EBS (3x gp2). It is pay per use, we only pay for what we use
- A security group should be attached to an EFS instance
- Multiple EC2 instances can access the files from an EFS instance in the same time
- Use cases for EFS: content management, web serving, data sharing
- Uses NFSv4.1 protocol
- **EFS is only compatible with Linux based AMIs!**
- EFS has a POSIX file system (because of Linux), that has a standard file API
- The EFS file system scales automatically, no capacity planning is required
- Encryption at rest for EFS is using KMS

## Performance & Storage Classes

- EFS Scale:
    - EFS is designed for thousands of NFS clients for reading and writing content at the same time
    - It provides 10+ GB/s throughput
    - It can grow to petabyte of storage
- Performance modes (should be set at the time of creation)
    - **General purpose** (default): used for latency-sensitive uses cases (web server, CMS)
    - **Max I/O** - higher latency, higher throughput, recommended for highly parallel workflows (big data, media processing)
- Storage Tiers
    - **Standard**: should be used for frequently accessed files
    - **Infrequent Access (EFS-IA)**: should be used for less frequently accessed files. Has lower price for storage, but imposes some additional costs if a file is accessed
- EFS provides a lifecycle management feature for the files (similar to S3)