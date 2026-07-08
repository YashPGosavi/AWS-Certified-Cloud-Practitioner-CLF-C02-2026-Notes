# Module 13: Well-Architected Solutions

## Introduction to Well-Architected Solutions

AWS offers many specialized services for development, business applications, end-user computing, and
IoT. To build reliable systems, it is also important to follow the AWS Well-Architected Framework,
which helps ensure that solutions are secure, efficient, resilient, and cost-effective.

### Key takeaway / summary

- AWS provides purpose-built services for many different business and technical needs.
- The Well-Architected Framework helps you evaluate and improve cloud architecture.

---

## AWS Specialized Services

AWS offers specialized services for four common use case categories.

### Development services

**AWS CodeBuild**

- A fully managed build service that compiles code, runs tests, and produces deployable artifacts.
- Scales automatically and charges only for build time used.

**AWS CodePipeline**

- A fully managed CI/CD service that automates build, test, and deployment stages.
- Helps teams deliver updates quickly and reliably.

**AWS X-Ray**

- A tracing and debugging tool for analyzing application performance.
- Helps identify bottlenecks and troubleshoot issues.

**AWS AppSync**

- A managed GraphQL service for building APIs that connect frontend apps to backend data sources.
- Supports secure access and data combination across services.

**AWS Amplify**

- Helps developers build and deploy full-stack applications quickly.
- Simplifies features like authentication, APIs, storage, and hosting.

### Business application services

**Amazon Connect**

- A cloud contact center service for customer support and call routing.
- Supports recording, analytics, and integration with AWS services.

**Amazon SES**

- A cost-effective email service for transactional and marketing messages.
- Useful for high-volume automated email delivery.

### End-user computing services

**Amazon AppStream 2.0**

- Streams applications to users from the cloud without requiring high-end local devices.
- Useful for delivering software to remote users.

**Amazon WorkSpaces**

- Provides managed virtual desktop environments.
- Lets employees access their work environment securely from many devices.

**Amazon WorkSpaces Secure Browser**

- Provides a secure browser environment for private websites and SaaS apps.
- Reduces the need for VPNs and special client software.

### IoT services

**AWS IoT Core**

- Connects physical devices to cloud applications securely.
- Supports device data ingestion, processing, and control.

### Key takeaway / summary

- Development services support CI/CD and application monitoring.
- Business, end-user, and IoT services help solve specialized real-world use cases.

---

## AWS Well-Architected Framework

The AWS Well-Architected Framework provides a structured way to design cloud solutions that are
secure, reliable, efficient, and sustainable.

### The six pillars

- **Operational Excellence**: Focuses on monitoring, automation, and continuous improvement.
- **Security**: Protects systems and data using least privilege, encryption, and strong access controls.
- **Reliability**: Ensures systems can recover from failures and adapt to demand.
- **Performance Efficiency**: Uses the right resources and scales effectively.
- **Cost Optimization**: Helps reduce waste and control spending.
- **Sustainability**: Encourages energy-efficient and environmentally responsible design.

### AWS Well-Architected Tool

The AWS Well-Architected Tool is a free service that helps assess and improve workloads using the
six pillars. It supports reviews, milestone tracking, and custom lenses for specific business needs.

### Optimizing a cloud architecture example

An online florist business can improve its architecture by applying the framework across each
pillar:

1. **Operational Excellence**
   - Use EC2 Auto Scaling and infrastructure as code.
   - Improve resilience with self-healing mechanisms.

2. **Security**
   - Apply least-privilege IAM policies.
   - Use encryption for data at rest and in transit.

3. **Reliability**
   - Use Amazon CloudWatch and deploy across multiple Availability Zones.

4. **Performance Efficiency**
   - Rightsize resources with AWS Compute Optimizer.
   - Use Lambda and CloudFront for scalable delivery.

5. **Cost Optimization**
   - Use Savings Plans, Spot Instances, and AWS Budgets.

6. **Sustainability**
   - Reduce waste by right-sizing workloads and using elastic services.

### Key takeaway / summary

- The Well-Architected Framework helps you improve architecture across six important dimensions.
- AWS tools such as the Well-Architected Tool and Compute Optimizer support this process.

---

## Specialized Use Cases

AWS services can be combined to solve specific business problems.

### Serverless web backend monitored by X-Ray

1. **Receive traffic**
   - Amazon API Gateway receives and validates HTTP requests.

2. **Trigger Lambda function**
   - API Gateway invokes a Lambda function that interacts with Amazon DynamoDB.

3. **Monitor traffic**
   - AWS X-Ray traces requests across API Gateway, Lambda, and DynamoDB.

### Serverless static website with contact form

1. **Accept customer input**
   - Customers submit questions through a contact form hosted on an Amazon S3 static website.

2. **Receive request**
   - API Gateway validates the incoming form request.

3. **Send email**
   - Lambda sends an email to the business owner using Amazon SES.

### Customer support with callback option

1. **Initiate contact**
   - Customers call or text a support center, routed through Amazon Connect.

2. **Connect to agent**
   - Amazon Connect tries to connect the customer to a live agent.

3. **Provide options**
   - Customers can choose a callback or switch to text through Lambda.

### Key takeaway / summary

- Serverless and contact-center solutions can be built by combining multiple AWS services.
- These examples show how AWS services work together to solve business needs.
