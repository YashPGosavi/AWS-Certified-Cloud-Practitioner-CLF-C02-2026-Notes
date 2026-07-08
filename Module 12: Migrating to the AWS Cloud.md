# Module 12: Migrating to the AWS Cloud

## Introduction to Migration

Cloud migration is the process of moving an organization’s digital assets, applications, databases, and IT resources from on-premises infrastructure to the AWS Cloud. It usually involves planning, execution, and ongoing management rather than a single one-time move.

### Three phases of the migration process

AWS guides customers through migration in three main phases:

1. **Assess**
   - Build the business case for migration.
   - Evaluate readiness and current infrastructure.
   - Example service: **Migration Evaluator**.

2. **Mobilize**
   - Prepare the organization and gather the resources needed.
   - Identify dependencies and create a migration plan.
   - Example services: **AWS Application Discovery Service** and **AWS Migration Hub**.

3. **Migrate and modernize**
   - Move workloads and improve applications during the transition.
   - Example services: **AWS Application Migration Service** and **AWS Database Migration Service (AWS DMS)**.
   - Data transfer tools may include **AWS DataSync**, **AWS Transfer Family**, and the **AWS Snow Family**.

![alt text](<Images/three-phases-of-the-migration-process.png>)

### Key takeaway / summary
- Migration is usually done in stages rather than as a single event.
- AWS provides services for assessment, planning, migration, and modernization.

---

## AWS Cloud Adoption Framework (AWS CAF)

The AWS Cloud Adoption Framework helps organizations prepare for cloud adoption by providing best practices, guidance, and a structured approach to migration.

### Why AWS CAF matters
- Reduces business risk.
- Improves governance, transparency, and sustainability.
- Helps organizations optimize operations and improve customer experience.
- Supports migration of both technology and business processes.

### Key stakeholder perspectives

- **Business**: Aligns IT investments with business goals.
- **People**: Supports change management, staffing, and training.
- **Governance**: Ensures IT strategy aligns with business strategy and risk controls.
- **Platform**: Defines architecture patterns for cloud solutions and migrations.
- **Security**: Helps meet security, visibility, and compliance goals.
- **Operations**: Supports reliable day-to-day operations and recovery processes.

### Key takeaway / summary
- AWS CAF helps organizations plan migration in a structured and business-focused way.
- It brings together people, process, security, and platform concerns.

---

## Seven Migration Strategies (the 7 Rs)

Organizations can choose different migration strategies depending on application complexity, business goals, timeline, and available resources.

![alt text](<Images/seven-migration-strategies.png>)

1. **Relocate**
   - Move existing applications or workloads to the cloud without changing their hosting model.

2. **Rehost**
   - Also called “lift-and-shift.”
   - Move applications to AWS with minimal or no changes.

3. **Replatform**
   - Also called “lift, tinker, and shift.”
   - Make small optimizations to gain cloud benefits without redesigning the whole application.

4. **Refactor**
   - Re-architect applications to use cloud-native features.
   - Best when major scale, performance, or feature improvements are needed.

5. **Repurchase**
   - Replace traditional software with a SaaS solution.
   - Example: moving from a legacy CRM to a cloud-based CRM product.

6. **Retain**
   - Keep some applications in the source environment for now.
   - Useful when an application is too critical or too complex to migrate immediately.

7. **Retire**
   - Remove applications that are no longer needed.

### Key takeaway / summary
- The 7 Rs help organizations choose the best migration path for each workload.
- Different applications may use different strategies within the same migration plan.

---

## Migration Services and Tools

AWS provides several services that support migration at different stages.

### Assess phase

**AWS Migration Evaluator**
- Helps create a business case for migration.
- Uses data-driven analysis to estimate current and future cloud costs.
- Supports discovery, licensing review, and migration readiness planning.

### Mobilize phase

**AWS Application Discovery Service**
- Discovers on-premises servers, databases, and connections.
- Collects configuration, performance, and dependency information.
- Helps build a detailed migration plan.

**AWS Migration Hub**
- Centralizes migration tracking and planning.
- Helps teams coordinate discovery, assessment, execution, and modernization.
- Provides guidance and collaboration tools.

### Migrate and modernize phase

**AWS Application Migration Service**
- Helps migrate applications to AWS while minimizing disruption.
- Supports modernization during the migration journey.

### Additional migration support

- **AWS Migration and Modernization Competency Partners** can provide expertise and implementation support.

### Key takeaway / summary
- AWS offers tools for assessment, discovery, planning, migration, and modernization.
- Migration Hub is a central place to manage the overall migration journey.

---

## Database Migrations

Database migration can involve moving to a managed AWS database, changing database engines, or modernizing the architecture.

### Types of database migration

- **Homogeneous migration**: moving between the same database engine types.
- **Heterogeneous migration**: moving between different database engines.

### AWS Database Migration Service (AWS DMS)
- Helps migrate databases quickly and securely.
- Supports ongoing replication for live databases and data warehouses.
- Useful for both homogeneous and heterogeneous migrations.
- Helps reduce downtime and support high availability.

### AWS Schema Conversion Tool (AWS SCT)
- Converts database schemas and code objects from one database engine to another.
- Useful when moving from commercial databases to open-source databases.
- Saves time compared with manual conversion.

### Key takeaway / summary
- AWS DMS handles database migration and replication.
- AWS SCT helps convert schemas and database objects when engines differ.

---

## Transferring Data Online

Online data transfer is often used when there is sufficient bandwidth and internet connectivity.

### Common migration considerations
- Security
- Data validation
- Scheduling and tracking
- Bandwidth requirements

### AWS services for online transfer

**AWS DataSync**
- Automates and accelerates data movement between on-premises storage and AWS storage services such as Amazon S3.
- Helps with encryption, scheduling, throttling, and reporting.

**AWS Transfer Family**
- Provides managed file transfer support for protocols such as FTP, SFTP, and FTPS.
- Transfers files securely into and out of services like Amazon S3 and Amazon EFS.

**AWS Direct Connect**
- Provides a dedicated private connection between on-premises networks and AWS.
- Offers a fast, reliable, and secure way to transfer large amounts of data.

### Key takeaway / summary
- DataSync is commonly used for large-scale online data migration.
- Direct Connect is ideal when a dedicated private connection is needed.

---

## Transferring Data Offline

Offline migration is used when internet connectivity is limited, bandwidth is low, or large amounts of data need to be moved physically.

### AWS Snowball Edge Storage Optimized
- A physical device used to transfer large amounts of data offline.
- Useful when transferring multi-petabyte datasets or when internet-based transfer is impractical.
- Can also be used for edge computing in secure or rugged locations.

### Key takeaway / summary
- Snowball Edge is the main AWS option for offline data migration.
- It is especially useful when network constraints make online transfer impractical.

