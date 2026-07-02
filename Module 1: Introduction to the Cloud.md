# Module 1: Introduction to the Cloud

## What is Cloud Computing

Cloud computing is the **on-demand delivery of computing resources** such as servers, storage, databases, networking, and applications over the internet with **pay-as-you-go pricing**.

### Key Ideas
- On-demand delivery
- Pay only for what you use
- Scalable resources
- No need to manage physical infrastructure


### Server

A **server** is a computer that provides services to other computers.
- **Server Components**
    1. CPU
    2. RAM
    3. Database
    4. Networking devices  
        - Routers  
        - Switches  
        - DNS Server  

- **Problems with Traditional IT Approach**
    1. Power supply requirements
    2. Cooling and maintenance
    3. Scaling infrastructure
    4. Required monitoring
    5. External factors (hardware failures, disasters)


### Cloud Computing Benefits

1. On-demand delivery
2. Pay-as-you-go pricing
3. Highly scalable
4. Instant resource provisioning
5. Simple access to servers, databases, and CPU power


### Cloud Deployment Models

1. Private Cloud (On-Premises Cloud)
    -   Infrastructure dedicated to a single organization.

2. Public Cloud
    -   Cloud services provided over the internet by third-party providers.
    - Examples:
        - Google Cloud
        - Microsoft Azure
        - AWS

3. Hybrid Cloud
    - Combination of **private cloud and public cloud**.
    - In a hybrid deployment, cloud-based resources and on-premises infrastructure work together. This approach is ideal for situations where legacy applications must remain on premises due to maintenance preferences or regulatory requirements.


### Characteristics of Cloud Computing

1. On-demand self-service
2. Broad network access
3. Resource pooling (multi-tenancy)
4. Rapid elasticity and scalability
5. Measured service


### Types of Cloud Computing

1. **IaaS** – Infrastructure as a Service
2. **PaaS** – Platform as a Service
3. **SaaS** – Software as a Service


### Key benefits of the AWS Cloud

1. Trade fixed expense for variable expense
2. Benefit from massive economies of scale
3. Increase speed and agility
4. Stop spending money to run and maintain data centers
5. Go global in minutes


### AWS Pricing – 3 Fundamental Drivers

1. **Compute**
2. **Storage**
3. **Data transfer out of the cloud**

---

### AWS Global Infrastructure

- **AWS Regions**
    - A **region** is a geographic area containing multiple data centers.

    - AWS Regions are physical locations around the world that contain groups of data centers. These groups of data centers are called Availability Zones. Each AWS Region consists of a minimum of three physically separate Availability Zones within a geographic area.

    - A Region is a geographical location that contains three or more Availability Zones. An Availability Zone is a distinct location within a Region that contains one or more discrete data centers.

- **Availability Zones (AZ)**
    - Availability Zones are **isolated data centers within a region** with:
        - Redundant power
        - Networking
        - Connectivity

    -  Used to deploy **highly available infrastructure**.

    - Regions and Availability Zones are designed to provide low-latency and fault-tolerant access to services for users within a given area.
       
- **NOTE** : It's recommended to distribute your resources across multiple AZs. That way, if one AZ encounters an outage, your business applications will continue to operate without interruption. With this approach of redundancy and resource isolation, AWS customers can achieve the benefits of high availability and fault tolerance.

- **Benifits**
    - High Availability
    - Fault tolerance

---

### Shared Responsibility Model

Used to define **security responsibilities between AWS and the customer**.

1. **AWS Responsibilities (Security OF the Cloud)**
    - AWS is responsible for protecting the infrastructure that runs all of the services offered in the AWS Cloud. 
    - Infrastructure
    - Global network security
    - Hardware
    - Compliance validation

2. **Customer Responsibilities (Security IN the Cloud)**
    - Customers are responsible for managing security requirements for their data, including which data they store on AWS and who has access to that data.
    - Users
    - Groups
    - Roles
    - Policies
    - Monitoring
    - MFA configuration
    - Key rotation

3. **Customer or AWS responsibility (Varies by service)**
    - Depending on the service used, responsibilities might shift between the customer and AWS. 
    - Components such as server-side encryption, network traffic protection, platform and application management, and OS, network, and firewall configuration vary by service in terms of who is responsible for these items. 


![alt text](<Images/Shared Responsibility Model.png>)

---

