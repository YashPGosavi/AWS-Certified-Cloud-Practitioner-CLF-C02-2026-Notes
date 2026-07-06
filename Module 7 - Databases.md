# Module 7: Databases

## Introduction to Databases

- AWS offers a wide range of database services for different application and data needs.
- These services are designed to be scalable, reliable, and easier to operate than traditional self-managed databases.
- AWS database offerings include:
  - relational databases
  - nonrelational databases
  - in-memory databases and caches
  - purpose-built databases for specialized use cases

- **Key takeaway**: AWS provides different database services because different workloads need different data models, performance profiles, and management levels.

---

## AWS Shared Responsibility for Databases

- AWS database services can be grouped by who is responsible for operational tasks.
- These categories are:
  1. fully managed
  2. managed
  3. unmanaged
- Most of the database services in this module are fully managed, with a few managed services and no core focus on unmanaged options.

1. **Fully managed services**
    - In fully managed database services, AWS handles most operational work.
    - AWS responsibilities typically include:
        - provisioning
        - scaling
        - patching
        - backups
        - routine maintenance
        - monitoring and metrics
        - much of the underlying availability and infrastructure management
    - Customer responsibilities mainly include:
        - designing the data model
        - managing access controls
        - using the service correctly for the workload

    ![alt text](Images/Storage_Fully_Managed_Service.png)


2. **Managed services**
    - In managed database services, AWS handles the underlying infrastructure and many routine tasks.
    - AWS responsibilities typically include:
        - hardware provisioning
        - automated backups
        - patching support
        - infrastructure maintenance
    - Customer responsibilities typically include:
        - database engine configuration
        - query optimization
        - schema design
        - performance tuning decisions

    ![alt text](Images/Storage_Managed_Service.png)


3. **Unmanaged services**
    - In unmanaged database deployments, the customer is responsible for nearly everything.
    - Customer responsibilities include:
        - installation
        - configuration
        - patching
        - maintenance
        - database security
        - backups
        - high availability setup
        - performance optimization
    - A common example is running a database such as MySQL directly on an **Amazon EC2** instance.

    ![alt text](Images/Storage_Unmanaged_Service.png)

---

## Relational Database Services

- Relational databases store structured data in tables made up of rows and columns.
- They use **SQL (Structured Query Language)** to create, manage, and query data.
- They are a good fit for applications that need:
  - structured data
  - consistent schemas
  - relationships between records
  - transactions and complex queries

- **Key takeaway**: relational databases are best when your data is structured and different pieces of data need to relate to each other reliably.

#### Simple relational database example

- A restaurant inventory database might store each product as one record.

| ID | Product Name | Size | Price |
| --- | --- | --- | --- |
| 1 | Medium roast ground coffee | 12 oz. | $13.95 |
| 2 | Single-origin whole bean coffee | 12 oz. | $21.95 |


---

## Amazon Relational Database Service (Amazon RDS)

- Amazon RDS is a managed relational database service that makes it easier to set up, operate, and scale relational databases in AWS.
- It handles many routine administrative tasks such as:
    - Automated patching
    - Backups
    - Redundancy
    - Failover
    - Disaster recovery
- Amazon RDS uses DB instance classes that can be optimized for general-purpose, memory-optimized, compute-optimized, or burstable workloads.

### Supported Amazon RDS database engines

- Amazon RDS supports these database engines:
  - MySQL
  - PostgreSQL
  - MariaDB
  - Microsoft SQL Server
  - Oracle Database
  - IBM Db2
- **Amazon Aurora** is also part of the Amazon RDS family, but it is usually studied as its own AWS-built relational engine.


### Key Amazon RDS features

1. **Automated backups and snapshots**
    - Amazon RDS can create automated backups for point-in-time recovery.
    - You can also create manual **DB snapshots** when you want a user-initiated backup.

2. **Multi-AZ deployments**
    - Amazon RDS can maintain a synchronous standby instance in another Availability Zone.
    - If the primary instance fails, Amazon RDS can automatically fail over to the standby instance.

3. **Read replicas**
    - Read replicas can help scale read-heavy workloads by offloading read traffic from the primary database.

4. **Security**
    - Amazon RDS supports VPC isolation, encryption at rest, and encryption in transit.

5. **Scalability**
    - You can scale compute and storage based on workload needs.


### Common use cases for Amazon RDS

- Web applications
- Enterprise applications
- E-commerce product catalogs and inventories
- Traditional relational workloads that need managed operations


### Benefits of Amazon RDS

1. **Reduced operational overhead**
   - AWS handles many repetitive administrative tasks so you can focus more on the application and schema design.

2. **High availability**
   - Multi-AZ deployments improve resilience and minimize downtime.

3. **Performance support**
   - Features such as read replicas and Performance Insights help with monitoring and read scaling.

4. **Cost optimization**
   - You avoid the upfront cost of buying and maintaining your own database hardware.


---


## Amazon Aurora

- Amazon Aurora is a **fully managed relational database engine** in the Amazon RDS family.
- It is compatible with **MySQL** and **PostgreSQL**.
- Aurora is designed for high performance, high availability, and automatic scaling.
- It uses distributed storage that grows automatically as needed.

- **Key takeaway**: choose Aurora when you want a cloud-native relational database with MySQL or PostgreSQL compatibility and stronger performance and availability than standard deployments.


### Key Amazon Aurora features

1. **High performance**
   - Aurora is designed to deliver up to **6x** the throughput of stock MySQL and up to **6x** the throughput of stock PostgreSQL on similar hardware.

2. **Automatic storage scaling**
   - Aurora storage grows automatically as your data grows.
   - An Aurora cluster volume can grow up to **256 TiB**.

3. **High availability and durability**
   - Aurora replicates data across **three Availability Zones** with **six copies of data**.
   - It is designed for strong fault tolerance and fast failover.

4. **Automated backups**
   - Aurora continuously backs up data and supports point-in-time recovery.


### Common use cases for Amazon Aurora

- Gaming applications
- Media and content platforms
- SaaS applications
- Enterprise applications
- Real-time or high-throughput relational workloads


### Common exam reminders

- Relational databases use **tables** and **SQL**.
- Amazon RDS is the default managed choice for many traditional relational workloads.
- **Multi-AZ** improves availability and failover readiness.
- **Read replicas** help with read scaling, not primary failover.
- Aurora is **MySQL- and PostgreSQL-compatible** and is designed for higher performance and availability.

---
