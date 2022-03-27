
EFS
Amazon EFS is a fully managed service for hosting Network File System (NFS) filesystems in the cloud.
It is an implementation of a NFS file share and is accessed using the NFS protocol.
It provides elastic storage capacity and pay for what you use (in contrast to Amazon EBS with which you pay for what you provision).


Features
EFS is elastic is moves up and down based on usage
It offers 99.99(11)% SLA
it can support about 10k connections from containers,ec2,EKS,fargate,lambda
500k IOPS,single digit latency and Gigabytes of throughput
 
 
 ROW: Right is not acked until the data is durably written across all 3 availability zones
 

Connectivity
------------------------------

You can mount an AWS EFS filesystem from on-premises systems ONLY if you are using AWS Direct Connect or a VPN connection
You can concurrently connect up to thousands of Amazon EC2 instances, from multiple AZs

size and charges
---------------
Uses a pay for what you use model with no pre-provisioning required
AWS EFS can scale up to petabyte,AWS EFS is elastic and grows and shrinks as you add and remove data

Data is stored across multiple AZs within a region.
Amazon EFS is compatible with all Linux-based AMIs for Amazon EC2
Using the EFS-to-EFS Backup solution, you can schedule automatic incremental backups of your Amazon EFS file system

Backups
--------
Automatic backups are enabled by default and use AWS Backup.
Lifecycle management moves files that have not been accessed for a period of time to the EFS Infrequent Access Storage class.

Performance Mode
    “General Purpose” performance mode is appropriate for most file systems.
     usecase:- Latency sensitive applications and GP workloads
     35k read abd 7k write operations/s
    
    Max I/O performance mode
     optimized for applications where tens, hundreds, or thousands of EC2 instances are accessing the file system.
    Usecase:- Large Scal and data heavy applications
    

Monitoring and Reporting
-----------------------
Amazon EFS reports metrics for Amazon CloudWatch.  A few useful metrics are:
    TotalIOBytes – use the daily Sum statistic to determine throughput.
    ClientConnections – use the daily Sum statistic to track the number of connections from EC2 instances.
    BurstCreditBalance – monitor the burst credit balance.

Logging and Auditing
----------------------
Amazon EFS is integrated with AWS CloudTrail.
CloudTrail captures all API calls for Amazon EFS as events, including calls from the Amazon EFS console and from code calls to Amazon EFS API operations.
