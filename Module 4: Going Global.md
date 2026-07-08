# Module 4: Going Global

### Going global with AWS infrastructure

1. **How to choose a Region or set of Regions**
    - If we were to expand our coffee shop by opening new locations, there would be multiple things to consider, like customer demand and development cost. Similarly, you have several factors to consider when selecting a Region or set of Regions for your real-life resources.

2. **AWS edge locations**
    - Like our coffee franchise could expand with smaller versions of the shop such as mobile coffee carts, AWS has smaller footprint facilities called edge locations. Edge locations cache items like images, videos, and other resources, so that users can access the content they need with lower latency.

3. **Infrastructure as code and CloudFormation**
    - Another important consideration of a coffee shop expansion would be to maintain a consistent product from location to location. 
    - AWS has services, such as CloudFormation, that you can use to help automate the deployment of your cloud resources. These services use infrastructure as code, or IaC, helping you achieve a consistent, reliable set up each time your business grows.

---

### Choosing AWS Region

- Key considerations when choosing Regions

    1. **Compliance** : Meet legal and regulatory requirements.

    2. **Proximity** : Reduce latency and improve performance.

    3. **Feature Availability** : Ensure required AWS services are available.

    4. **Pricing** : Optimize infrastructure costs.


---


### Diving Deeper into AWS Global Infrastructure

#### Designing highly available architectures

##### Deploying multi-Region and multi-AZ resources

- To build highly available and reliable applications, AWS recommends deploying resources across multiple Availability Zones (AZs) and, when needed, multiple Regions.
- This minimizes downtime and keeps applications available even if part of the infrastructure fails.
- In addition to high availability, the AWS Global Infrastructure also helps you achieve agility and elasticity for your business. Let's discuss the difference between these advantages:
    - **High availability**: High availability refers to the capability of a system to operate continuously without failing. In the context of AWS infrastructure, it means that your applications can handle the failure of individual components without significant downtime.
    - **Agility**: Agility refers to the ability to quickly adapt to changing requirements or market conditions. With AWS infrastructure in place, you can modify and deploy services rapidly.
    - **Elasticity**: Elasticity refers to the ability of a system to scale resources up or down automatically in response to changes in demand. AWS infrastructure is set up for you to scale resources up and down on demand.


#### Edge locations

- In addition to AWS Regions that contain Availability Zones, AWS has a global edge network that provides quicker content access to users outside of standard Regions. 
- These edge locations are strategically placed in areas like Atlanta, Georgia, USA or Shanghai, China to provide low-latency access to AWS services and content delivery.
- Edge locations offer multiple services to run closer to end users, including AWS networking services like Amazon CloudFront. CloudFront is a content delivery network (CDN) and caching system that you learn more about later in this training.

- Edge Locations are sites that cache content closer to end users.
- Used primarily by services such as Amazon CloudFront.
- Help deliver content with:
    * Lower latency.
    * Faster data transfer speeds.
    * Improved user experience.
- Reduce the distance data must travel between users and AWS resources.


#### Key elements of AWS Global Infrastructure
To review the relationship between Regions, Availability Zones, and edge locations, choose each of the three numbered markers.

1. **AWS Regions**
    - Regions are geographical areas around the world that are made up of multiple data centers. These data centers provide scalable and redundant infrastructure for hosting cloud services. 
    - Each Region consists of multiple, isolated locations known as Availability Zones. Each Region has three or more Availability Zones.

2. **Availability Zones**
    - Availability Zones are distinct locations within a Region, each designed as an independent zone with its own power, networking, and connectivity.
    - Availability Zones maintain high availability and fault tolerance for applications. Each Availability Zones consists of one or more data centers.

3. **Edge locations**
    - Edge locations are strategically placed sites around the world that cache content to deliver data, video, and applications with lower latency and higher transfer speeds. 
    - Edge locations are considered a vital part of the AWS content delivery network (CDN) and use services like CloudFront to efficiently distribute data to end users.


#### Amazon cloudfromt 

- It is content delevary network, uses edge locations.
- Uses
    - Images
    - Videos
    - Websites
    - Static files
    - APIs


#### Amazon Root53 

- AWS DNS (Domain Name System) service.


#### Summery 

1. Regions are physical locations around the world that contain multiple data centers. 
2. Each Region contains at least three Availability Zones. 
3. Each Availability Zone contains one or more data centers. 
4. Edge locations are devices in areas outside of Regions. These devices provide user access to frequently accessed data with low latency.

---

### Infrastructure and Automation / IaC(Infrastructure as Code)

#### CloudFormation

- CloudFormation is a service that helps you model and set up your AWS resources so that you can spend less time managing those resources and more time focusing on your applications that run in AWS. 
    
- With CloudFormation, you can define your infrastructure as code. You create a template that describes all the AWS resources that you want (like Amazon Elastic Compute Cloud (Amazon EC2) instances), and CloudFormation takes care of provisioning and configuring those resources for you.

- CloudFormation is designed to handle complex infrastructure setups. It defines infrastructure as code to help make sure that deployments are consistent across different environments such as development, testing, and production.

- With CloudFormation, users can model and set up their AWS resources using code to automate provisioning and the management of infrastructure. This method can help to reduce errors and maintain consistency across environments.


#### Interacting with AWS resources

- To interact with AWS resources, you must invoke AWS APIs. 
- To interact with these APIs, you can use the AWS SDKs, the AWS Command Line Interface (AWS CLI), the AWS Management Console, or IaC tools such as CloudFormation. 

1. **Programmatic access**
    - Programmatic access includes options like the AWS CLI and AWS SDKs. 
    - **AWS CLI**: Automate routine tasks. For example, you might write a script to provide routine backups for a service such as Amazon Elastic Block Store (Amazon EBS).
    - **SDKs**: Invoke APIs for one part of an application process. For example, you might use an SDK to store user data in an AWS storage service such as Amazon Simple Storage Service (Amazon S3).


2. **AWS Management Console**
    - The AWS Management Console is a web interface that you use for managing AWS services, offering quick access to services, search functionality, and simplified workflows. 
    - The console is a great option for those new to the cloud or users with minimal or no development experience.
    - Use Cases:
        * Billing and Cost Management dashboards.
        * Monitoring AWS resources.
        * Services requiring graphical interfaces, such as:
            * Amazon QuickSight
            * Amazon Neptune


3. **Infrastructure as Code**

    - With IaC tools such as CloudFormation, you can automate resource management across your organization with AWS service integrations offering efficient and repeatable resource creation and management.
    - Use cases for CloudFormation include the following:
        * Continuous Integration/Continuous Delivery (CI/CD) pipelines.
        * Deploying identical infrastructure across multiple Regions.
        * Scaling Amazon EC2 instances consistently.
        * Managing complex AWS environments.


---
