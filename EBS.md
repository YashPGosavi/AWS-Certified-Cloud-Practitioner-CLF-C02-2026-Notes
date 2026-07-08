
### EBS volume basics

- An EBS volume is a network drive you can attach to an instance while it is running.
- It allows your instance to persist data even after termination.
- It can be attached to only one instance at a time at the CCP level.
- It is bound to a specific Availability Zone.
- Analogy: think of it as a network USB stick.


### EBS volume characteristics

- It is a network drive, not a physical drive.
- It uses the network to communicate with the instance, so there may be some latency.
- It can be detached from one EC2 instance and attached to another quickly.
- It is locked to an Availability Zone; an EBS volume in one AZ cannot be attached to another AZ.
- To move it across AZs, you first need to create a snapshot.
- It has provisioned capacity in GBs and IOPS.
- You are billed for all the provisioned capacity.
- You can increase its capacity over time.

### EBS – Delete on Termination attribute

- Controls the behavior of an EBS volume when an EC2 instance terminates.
- By default, the root EBS volume is deleted.
- By default, any other attached EBS volume is not deleted.
- This can be controlled through the AWS Console or AWS CLI.
- Useful when you want to preserve the root volume after instance termination.

### EBS snapshots

- A snapshot is a backup of an EBS volume at a point in time.
- You do not need to detach the volume to take a snapshot, although it is recommended.
- Snapshots can be copied across Availability Zones or Regions.

### EBS snapshot features

- EBS Snapshot Archive: move a snapshot to an archive tier that is about 75% cheaper, but restoring it can take 24 to 72 hours.
- Recycle Bin for EBS Snapshots: set rules to retain deleted snapshots so they can be recovered after accidental deletion.
- Retention can be configured from 1 day up to 1 year.

---

## AMI overview

- AMI stands for Amazon Machine Image.
- An AMI is a customization of an EC2 instance.
- You can add your own software, configuration, operating system, monitoring, and more.
- It helps reduce boot and configuration time because your software is pre-packaged.
- AMIs are built for a specific region and can be copied across regions.

### AMI types

- Public AMI: provided by AWS.
- Your own AMI: created and maintained by you.
- AWS Marketplace AMI: created by someone else and may be sold.

### AMI process from an EC2 instance

1. Start an EC2 instance and customize it.
2. Stop the instance for data integrity.
3. Create an AMI; this also creates EBS snapshots.
4. Launch instances from the new AMI.

## EC2 Image Builder

- Used to automate the creation of virtual machines or container images.
- Automates the creation, maintenance, validation, and testing of EC2 AMIs.
- Can be run on a schedule such as weekly or whenever packages are updated.
- It is a free service; you only pay for the underlying resources.

### Build components

- Customize software on the instance.
- Run a test suite to verify that the AMI is working and secure.

## EC2 instance store

- EBS volumes are network drives with good but limited performance.
- If you need a high-performance hardware disk, use EC2 instance store.
- It offers better I/O performance.
- EC2 instance store is ephemeral; data is lost if the instance is stopped.
- It is good for buffers, caches, scratch data, and temporary content.
- There is a risk of data loss if hardware fails.
- Backups and replication are your responsibility.

