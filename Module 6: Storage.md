# Module 6: Storage

- AWS provides many solutions for storing, accessing, managing, and backing up your data in the cloud. These virtual storage systems eliminate the need for physical hardware in your data center while offering the flexibility to scale as your needs change.
- AWS offers three distinct types of cloud storage to meet diverse requirements and application needs:
    1. block storage
    2. object storage
    3. file storage

1. **Block storage**
  - Block storage provides persistent, low-latency block-level storage volumes that attach to EC2 instances like physical hard drives.
  - Volumes can be encrypted, backed up via snapshots, and modified while in use without disrupting the instance.
  - AWS block storage services include:
    1. **Amazon EC2 instance store**
      - Unmanaged, non-persistent, high-performance block storage directly attached to EC2 instances.
      - Best for temporary data that does not need to persist after instance termination.
    2. **Amazon Elastic Block Store (EBS)**
      - Managed, persistent block storage volumes for EC2 instances.
      - Offers different volume types for varying workload performance and cost needs.


2. **Object storage**
  - Object storage manages data as objects in a flat address space.
  - It provides unlimited scalability so you can store vast amounts of unstructured data without worrying about capacity constraints.
  - Object storage offers rich metadata capabilities for better data management, search, and analytics across large datasets.
  - Primary AWS object storage service:
    - **Amazon Simple Storage Service (S3)**: Fully managed, scalable object storage for storing and retrieving any amount of data from anywhere.

3. **File storage**
  - AWS file storage services provide shared file systems accessible over networks, allowing multiple users and applications to access the same data simultaneously.
  - They offer scalability and flexibility so capacity can expand without managing physical infrastructure.
  - AWS file storage services include:
    1. **Amazon Elastic File System (EFS)**
      - Fully managed, scalable NFS file system for AWS Cloud services and on-premises resources.
    2. **Amazon FSx**
      - Fully managed file storage for popular file systems such as Windows, Lustre, and NetApp ONTAP.


### Additional storage services

- These AWS storage services do not fit neatly into the block, object, or file categories but are important to know:
  1. **AWS Storage Gateway**
    - Fully managed hybrid-cloud storage service providing on-premises access to virtually unlimited cloud storage.
  2. **AWS Elastic Disaster Recovery**
    - Fully managed service that streamlines recovery of physical, virtual, and cloud-based servers into AWS.

### AWS shared responsibility for storage

- AWS storage services are grouped into three categories based on who owns administrative tasks:
  - Fully managed
  - Managed
  - Unmanaged

1. **Fully managed services**
  - AWS is responsible for hardware, infrastructure, durability, availability, encryption at rest, and replication.
  - Customers are responsible only for data management, access controls, and proper configuration.
  - Customer responsibility is lower than with managed services.

  ![alt text](<Images/Storage_Fully_Managed_Service.png>)


2. **Managed services**
  - AWS handles underlying storage infrastructure, hardware redundancy, and volume replication.
  - Customers are responsible for data backup strategies, encryption configuration, performance optimization, and capacity planning.
  - Customer responsibility increases compared to fully managed services.

  ![alt text](Images/Storage_Managed_Service.png)


3. **Unmanaged services**
  - Customers take full responsibility for data management, backup/recovery, encryption, performance optimization, and durability.
  - AWS maintains only the physical hardware and network infrastructure.
  - Unmanaged services place the greatest responsibility on the customer.

  ![alt text](Images/Storage_Unmanaged_Service.png)


---


## EC2 Instance Store and Amazon Elastic Block Store (Amazon EBS)

### Amazon EC2 instance store

- Amazon EC2 instance store is not a stand-alone AWS block storage service. Instead, it refers to the block-level storage that is physically attached to the EC2 instance host computer. Depending on the instance type, EC2 instance store may come attached as the default storage.
- EC2 instance store is directly attached to the host, offering extremely low latency and high I/O performance for applications that need temporary storage with fast access.
- Because the data is lost when an instance is stopped or terminated, EC2 instance store is best for temporary, memory-based storage needs such as buffers, caches, and scratch data. It is not recommended for applications that require data retention.

- **Key takeaway**: no data persistence
  - An Amazon EC2 instance store provides temporary block-level storage for an Amazon EC2 instance. If you stop or terminate the instance, all data written to the attached instance store is deleted.


#### How data is handled

  1. **Step 1**: An EC2 instance is running with data stored in an EC2 instance store.
  2. **Step 2**: The EC2 instance is stopped.
  3. **Step 3**: After the EC2 instance is stopped or terminated, all data in the EC2 instance store is lost.


#### Benefits Of EC2 Instance Storage

1. **Automatically available storage**
    - Instance store volumes are automatically attached to many EC2 instance types, providing temporary block-level storage at no additional cost. Because the storage is physically connected to the host computer, it offers high I/O performance for data that disappears when the instance stops.

2. **Cost effective**
    - Because EC2 instance store is included in the EC2 instance price, you do not pay an additional storage fee. It is ideal for temporary storage needs such as buffers, caches, or scratch data, which can reduce costs for applications that do not require persistent storage.

3. **High performance**
    - EC2 instance store offers extremely low-latency storage directly attached to the host server of your EC2 instance. This proximity provides excellent I/O performance, making it ideal for temporary data that requires fast processing.

---

### Amazon Elastic Block Store (EBS)

Amazon EBS provides persistent block-level storage volumes for use with Amazon EC2 instances. EBS volumes act like external hard drives and provide consistent, low-latency performance for workloads such as databases and file systems.

EBS volumes can be backed up, resized, and attached to different EC2 instances. To create an EBS volume, you define its size and type. After the volume is created, it can be attached to an Amazon EC2 instance. Because EBS volumes are intended for data that must persist, it is important to back up the data. It is recommended to take incremental backups by creating Amazon EBS snapshots.

### Key takeaway: data persistence

Amazon EBS provides block-level storage volumes that you can use with Amazon EC2 instances. If you stop or terminate an Amazon EC2 instance, the data on the attached EBS volume remains available.

### How data is handled

- Step 1: An EC2 instance is running with data stored in an attached EBS volume.
- Step 2: The EC2 instance is stopped.
- Step 3: After the EC2 instance is stopped or terminated, all data stored in the EBS volume is retained.

### Use cases

Some common use cases for Amazon EBS include database hosting, backup storage for applications, and rapid deployment of development environments using volume snapshots.

### Benefits

  1. Data portability
    - EBS volumes can be detached and reattached to instances as needed, making it easier to manage workloads and move data between instances.

  2. Data migration
    - EBS volumes can be migrated between Availability Zones using snapshots. Snapshots provide a simple way to move data across regions or create copies.

  3. Instance type changes
    - Because EBS volumes remain independent of EC2 instances, they can be attached to different instance types. This flexibility allows you to upgrade or downgrade instances without losing data.

  4. Disaster recovery
    - EBS snapshots provide reliable backup solutions that can be restored in different regions during emergencies. Regular automated snapshots help protect your data and support fast recovery.

  5. Cost optimization
    - EBS volumes can be modified to different types and sizes to match actual usage patterns. You can switch between storage types or adjust capacity without downtime.

  6. Performance tuning
    - Amazon EBS offers various volume types to match different workload requirements and IOPS needs. You can adjust volume performance characteristics as application demands change.

