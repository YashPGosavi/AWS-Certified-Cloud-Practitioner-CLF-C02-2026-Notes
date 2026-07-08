# Module 3: Exploring Compute Services

## Introduction to Serverless Computing

- With serverless computing, you run applications without managing the underlying infrastructure. 
- With serverless services, customers can focus solely on writing and deploying code. AWS fully manages infrastructure, scaling, and availability, so customers do not have to worry about managing servers or capacity.

### Unmanaged and managed services

- **Unmanaged Services**
    - With unmanaged services like Amazon EC2, you set up and manage everything: the operating system, security updates, and network settings. 
    - AWS only takes care of the physical hardware.

- **Managed services** 
    - Managed services handle most of the infrastructure for you, but you still need to set up things like deployment options, scaling, and environment settings. 

- **Fully-managed services**
    - With fully managed services like AWS Lambda, you don’t manage any servers at all. 
    - You upload your code, and AWS takes care of the rest, including infrastructure, scaling, and availability 
    - Example :
        - Lambda is a serverless compute service where AWS handles the infrastructure, scaling, and availability, while you remain responsible for securing and managing your application code.

![alt text](<Images/module-3-unmanaged-and-managed-services.png>)


---


### AWS Lambda

1. Lambda is a serverless compute service where AWS handles the infrastructure, scaling, and availability, while you remain responsible for securing and managing your application code.

2. It also known as function as a service.

3. You are charged only for the compute time consumed, down to the millisecond. Lambda handles execution, scaling, and resource allocation. You can optimize performance by configuring the appropriate memory size for your function.

4. Run code automatically when an event occurs—without managing servers.

5. Supports different programming laguanges

6. perfect for event driven architecture



#### How Lambda works

    Lambda Function -> Triggers -> Runtime

1. Upload code to lambda
2. Set a code to trigger from event source
3. Run code when triggered
4. Pay only for compute time used

#### Lambda use cases

1. **Real-time image processing for a social media application**: It automatically scales based on uploads and charges only for the time spent processing each image.

2. **Personalized content delivery for a news aggregator**: It automatically scales with user traffic and reduces costs by running code only when users interact.

3. **Real-time event handling for an online game**: It handles thousands of events, in real-time, with no need to manage servers. Costs scale with usage, which is ideal for peak gaming times.

### Common Lambda Triggers

1. 📁 File uploaded to Amazon S3
2. 🌐 API request via Amazon API Gateway
3. 📨 Message from Amazon SQS
4. 📢 Notification from Amazon SNS
5. 📅 Scheduled event via Amazon EventBridge


---


## Containers and Orchestration on AWS

- Containers provide a reliable way to package your application’s code and dependencies into a single, portable unit, making them ideal for workflows that require high security, reliability, and scalability.
- Containers are faster and lighter than virtual machines (VMs) because they share the host computer’s operating system. 

Why Containers?

Without containers:

* Development, testing, and production environments may differ.
* Applications may work on one machine but fail on another.

With containers:

* Same environment everywhere.
* Easier deployment and troubleshooting.

### Container Orchastrastion : Auto manage container



As applications grow, you may have hundreds or thousands of containers.

Managing them manually becomes difficult.

Container orchestration automatically:

* Deploys containers
* Scales containers
* Monitors containers
* Restarts failed containers
* Manages networking

Easy memory trick:
Orchestration = Auto-manage containers



#### AWS container services

- AWS has a set of tools for managing containers that fits into three categories: orchestration, registry, and compute.


| Category      | Service                |
|---------------|------------------------|
| Registry      | Amazon ECR             |
| Orchestration | Amazon ECS, Amazon EKS |
| Compute       | AWS Fargate, Amazon EC2|


1. **Amazon Elastic Container Registry(ECR)**

    - Amazon Elastic Container Registry (Amazon ECR) is where you can store, manage, and deploy container images. 
    - Supports OCI (Open Container Initiative) images.
    - You can push, pull, and manage images in your Amazon ECR repositories using standard container tooling and command line interfaces (CLIs).


2. **AWS Fargate**
    - AWS Fargate is a serverless compute engine for containers. 
    - Works with: Amazon ECS, Amazon EKS
    - Fargate runs containers, while ECS and EKS manage (orchestrate) them.

    - When using Fargate, you do not need to provision or manage servers. Fargate manages your server infrastructure for you. You can focus more on innovating and developing your applications, and you pay only for the resources that are required to run your containers.


3. **Amazon Elastic Container Service (ECS)**
    - Amazon Elastic Container Service (Amazon ECS) is a scalable container orchestration service for running and managing containers on AWS, like Docker containers.

    - **Amazon ECS launch types**
        - **Amazon ECS with Amazon EC2** is ideal for small-to-medium businesses that need full control over infrastructure. Suitable for custom applications requiring specific hardware or networking configurations, with the flexibility of Amazon EC2 and the simplicity of Amazon ECS.
        - **Amazon ECS with AWS Fargate** is perfect for startups or small teams building web applications with variable traffic. It's a serverless option—no server management required—so teams can focus on development while Amazon ECS handles scaling and orchestration.



4. **Amazon Elastic Kubernetes Service (EKS)**
    - Amazon Elastic Kubernetes Service (Amazon EKS) is a fully managed service for running Kubernetes on AWS. 
    - It simplifies deploying, managing, and scaling containerized applications using open-source Kubernetes, with ongoing support and updates from the broader community.

    - **Amazon EKS launch types**
        - **Amazon EKS with Amazon EC2**: This is best for enterprises needing full control over infrastructure. It offers deep customization of EC2 instances alongside Kubernetes scalability—ideal for complex, large-scale workloads.
        - **Amazon EKS with AWS Fargate**: This is great for teams wanting Kubernetes flexibility without managing servers. It combines Kubernetes power with serverless simplicity, helping to scale applications quickly across various use cases.


#### Putting it together
- Start with uploading a container image to ECR
- Choose an orchestration service based on your needs: ECS or EKS
- Select which compute platform to run your container: EC2 or Fargate

        Build Container
            │
            ▼
        Store Image in Amazon ECR
            │
            ▼
        Choose Orchestrator
        ├── Amazon ECS
        └── Amazon EKS
            │
            ▼
        Choose Compute
        ├── Amazon EC2
        └── AWS Fargate
            │
            ▼
        Run Containers


### Summery 

1. Amazon ECS is a scalable service for orchestrating containers on AWS.
2. Amazon EKS helps simplify Kubernetes deployment. 
3. Amazon ECR stores and manages OCI-compliant container images, integrating with Amazon ECS, Amazon EKS, and Fargate. 
4. Fargate is a serverless compute engine for containers, removing the need to manage infrastructure and working with Amazon ECS and Amazon EKS.

---

## Additional Services

- AWS offers purpose-built services for specific needs, such as streamlining web application deployment, managing batch workloads, providing virtual servers, and extending cloud infrastructure to on-premises data centers.

1. **Elastic Beanstalk** : streamlining web application deployment
    - Elastic Beanstalk is a fully managed service that streamlines the deployment, management, and scaling of web applications. 
    - Developers can upload their code, and Elastic Beanstalk automatically handles the provisioning of infrastructure, scaling, load balancing, and application health monitoring. 
    - It supports various programming languages and frameworks, such as Java, .NET, Python, Node.js, Docker, and more. It provides full control over the underlying AWS resources while automating many operational tasks.
    - **Good for**: Deploying and managing web applications, RESTful APIs, mobile backend services, and microservices architectures, with automated scaling and simplified infrastructure management

2. **AWS Batch** : managing batch workloads
    - AWS Batch is a fully managed service that you can use to run batch computing workloads on AWS. 
    - It automatically schedules, manages, and scales compute resources for batch jobs, optimizing resource allocation based on job requirements.
    - **Good for**: Processing large-scale, parallel workloads in areas like scientific computing, financial risk analysis, media transcoding, big data processing, machine learning training, and genomics research

3. **Lightsail** : providing virtual private servers
    - Amazon Lightsail is a cloud service offering virtual private servers (VPSs), storage, databases, and networking at a predictable monthly price. 
    - It’s ideal for small businesses, basic workloads, and developers seeking a straightforward AWS experience without the complexity of the full AWS Management Console.
    - **Good for**: Basic web applications, low-traffic websites, development and testing environments, small business websites, blogs, and learning cloud services

4. **Outposts** : extending cloud infrastructure to on-premises data centers
    - AWS Outposts is a fully managed hybrid cloud solution that extends AWS infrastructure and services to on-premises data centers. 
    - It provides a consistent experience between on premises and the AWS Cloud, offering compute, storage, and networking components.
    - **Good for**: Low-latency applications, data processing in remote locations, migrating and modernizing legacy applications, and meeting regulatory compliance or data residency requirements


#### Summery

1. AWS Elastic Beanstalk is a managed service for deploying and scaling web applications. 
2. AWS Batch runs large-scale batch computing workloads. 
3. Amazon Lightsail offers simplified VPS, storage, and networking. 
4. AWS Outposts extends AWS services to on-premises environments.