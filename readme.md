- [Introdution to AWS Web Services](#introdution-to-aws-web-services)
- [Compute in the cloud](#compute-in-the-cloud)
- [Global Infrastructure and Reliability](#global-infrastructure-and-reliability)
- [Networking](#networking)
- [Storage and Databases](#storage-and-databases)
- [Security](#security)
- [Monitoring and Analytics](#monitoring-and-analytics)
- [Pricing and supporting](#pricing-and-supporting)
- [Migration and Innovation](#migration-and-innovation)
- [The Cloud Journey](#the-cloud-journey)

# Introdution to AWS Web Services

## Cloud Computing
The on-demand delivery (resources that a customer needs) of IT resources over the Internet with pay as you go pricing (pay based on necessity)

## Advantages of cloud computing
Operating in the AWS Cloud offers many benefits over computing in on-premises or hybrid environments. 

Bellow six advantages of cloud computing:
- Trade upfront expense for variable expense.
- Benefit from massive economies of scale.
- Stop guessing capacity.
- Increase speed and agility.
- Stop spending money running and maintaining data centers.
- Go global in minutes.

## AWS Web Services
AWS (Amazon Web Services) is a cloud computing platform that offers a wide range of services including computing power, storage, database, machine learning, and more. It provides a secure, scalable, and cost-effective infrastructure for businesses to build and deploy applications.

> **Multitenancy**: Sharing underlying hardware between virtual machines. Hypervisor manager multi tenancies which is manage by AWS

## Amazon EC2:
- Handle: 
  - OS
  - Softwares
  - Databases
  - Network
- Each Amazon EC2 instance type is grouped under an instance family
- Type:
  - General purpose: General purpose instances provide a balance of computing, memory, and networking resources.
  - Memory-optimized: Memory-optimized instances are ideal for workloads that process large datasets in memory, such as high-performance databases
  - Compute optimized: Compute-optimized instances are better suited for batch processing workloads than general-purpose instances.
  - Storage optimized: Storage instances are designed for workloads requiring high, sequential read and write access to large datasets on local storage.
- Contract types:
  - Amazon EC2 Reserved instance: Amazon EC2 Reserved Instances (RI) provide a significant discount (up to 72%) compared to On-Demand pricing and a capacity reservation when used in a specific Availability Zone.
  - Amazon EC2 On-Demand: Let you pay for computing capacity by the hour or second with no long-term commitments.
  - Amazon EC2 Sopt Instance: Workload does not require a minimum contract length and can withstand interruptions.
  - Amazon EC2 Dedicated Instance: Run in a virtual private cloud (VPC) on hardware that is dedicated to a single customer.

## Elastic Load Balance
- Elastic Load Balancing is the AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances. Without it, the team needs install, manage, update, scale, handle failover, and availability.

## Auto Scaling
- Amazon EC2 Auto Scaling helps you maintain application availability and lets you automatically add or remove EC2 instances using scaling policies that you define.

## AWS Lambda
- It's a service that lets you run code without provisioning or managing servers.

## Amazon Simple Queue Service (Amazon SQS)
- Handle message as a queue

## Amazon Simple Notification Service (Amazon SNS)
- Handle messages as topic

## Amazon Elastic Container Service (ECS)
- It's a highly scalable, high-performance container (Docker) management system.

## Amazon Elastic Kubernetes Service (EKS)
- It's a fully managed service that you can use to run K8s on AWS.

## AWS Fargate
- Serverless compute engine for containers.

# Global Infrastructure and Reliability
High availability and fault tolerance

## Regions
A Region is a geographical area that contains AWS resources

- Constraints: Latency, Compliance (Governance regulation, legal requirements), feature availability, printing

##  Availability Zone
A single data center or group of data centers within a Region.

## AWS Edge Locations
An edge location is a site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery.

## CloudFront
Amazon CloudFront is a content delivery service. It uses a network of edge locations to cache content and deliver content to customers all over the world. When content is cached, it is stored locally as a copy

## AWS Outposts
Service that enables you to run infrastructure in a hybrid cloud approach.


## Provision AWS Resources
### AWS Management Console
 Is a web-based interface for accessing and managing AWS services.

### AWS CLI
Make API calls using a terminal to provision resources on AWS

### AWS SDKs
Interact with AWS resources through programming languages

### AWS Elastic Beanstalk
The user provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:

- Adjust capacity
- Load balancing
- Automatic scaling
- Application health monitoring

### AWS CloudFormation
Treat your infrastructure as code. This means that you can build an environment by writing lines of code instead of using the AWS Management Console to individually provision resources.

# Networking

## Amazon Virtual Private Cloud (VPC)
Amazon VPC enables you to provision an isolated section of the AWS Cloud. In this isolated section, you can launch resources in a virtual network that you define. Within a virtual private cloud (VPC), you can organize your resources into subnets. A subnet is a section of a VPC that can contain resources such as Amazon EC2 instances.

## Internet gateway (IGW)
To allow public traffic from the internet to access your VPC, you attach an internet gateway to the VPC.

## Virtual Private Gateway
Allow create a VPN between a on-premise or internal corporate network with a private network (VPC) to access private resources into the VPC.

- A virtual private gateway allows traffic into the VPC only if it is coming from an approved network.

## AWS Direct Connect
Establish a dedicated private connection between your data center and a VPC.  

- A corporate data center routes network traffic to an AWS Direct Connect location. That traffic is then routed to a VPC through a virtual private gateway. All network traffic between the corporate data center and VPC flows through this dedicated private connection.

## Subnets
A subnet is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private. 

- Public subnets: contain resources that need to be accessible by the public, such as an online store’s website.

- Private subnets: contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories. 

### Network access control list (ACL)
A network ACL is a virtual firewall that controls inbound and outbound traffic at the subnet level.
- Stateless packet filtering: Network ACLs perform stateless packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound.

### Security groups
The virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance.

- Stateful packet filtering: Security groups perform stateful packet filtering. They remember previous decisions made for incoming packets and deny all inbound traffic by default.
- Multiple Amazon EC2 instances within the same VPC, can be associated with the same security group or use different security groups for each instance. 

## Route 53
Suppose that AnyCompany has a website hosted in the AWS Cloud. Customers enter the web address into their browser, and they are able to access the website. This happens because of **Domain Name System (DNS)** resolution. DNS resolution involves a customer DNS resolver communicating with a company DNS server.

**Route 53** It's a DNS web service. It gives developers and businesses a reliable way to route end users to internet applications hosted in AWS. 

# Storage and Databases

## Storage

- Block
  - Used for high perfromance workloads
  - Attachek to the hard disk of the EC2 instance
  - It can be used by two type of services: Instance Store and EBS

- Object
  - It can be used by two type of services: S3

- File
  - Shared volume file storage across the services in the network
  - It can be used by two type of services: EFS, FSx(windows)

### Instance stores
Some Amazon EC2 instance types come with a form of directly attached, block-device storage known as an instance store. Use the instance store for temporary storage. Data that's stored in instance store volumes isn't persistent through instance stops, terminations, or hardware failures.

### Amazon Elastic Block Store (Amazon EBS)
It provides block-level storage volumes for Amazon EC2 instances. If a person stops or terminates an Amazon EC2 instance, all the data on the attached EBS volume remains available.

> Block Storage: In block storage, the object has a delta, which makes then in small pieces of blocks.

> EBS volumes store data within a single Availability Zone

### Amazon Elastic File system (Amazon EFS)
Is a scalable file system used with AWS Cloud services and on-premises resources. As you add and remove files, Amazon EFS grows and shrinks automatically. It can scale on demand to petabytes without disrupting applications. 

- Data in an Amazon EFS file system can be accessed concurrently from all the Availability Zones in the Region where the file system is located.

### Amazon Simple Storage Service (S3)
It's a service that provides object-level storage. Amazon S3 stores data as objects in buckets.

> Object Storage: In object storage, each object consists of data, metadata, and a key. The data might be an image, video, text document, or any other type of file.

#### Types
- S3 Standard
  - Designed for frequently accessed data
  - Stores data in a minimum of three Availability Zones

- S3 Standard Infrequent Access (S3 Standard IA)
  - Ideal for data that is infrequently accessed;
  - Ideal for data that requires high availability when needed
  - Both S3 Standard and S3 Standard-IA store data in a minimum of three Availability Zones. 
  - S3 Standard-IA provides the same level of availability as S3 Standard but at a lower storage price.

- S3 One Zone-IA
  - Stores data in a single Availability Zone
  - Has a lower storage price than Amazon S3 Standard-IA

- S3 Intelligent Tiering 
  - Ideal for data with unknown or changing access patterns
  - Requires a small monthly monitoring and automation fee per object
  - If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA. If you access an object in the infrequent access tier, S3 automatically moves it to the frequent access tier, S3 Standard.

- S3 Glacier Instant Retrieval
  - Works well for archived data that requires immediate access
  - Can retrieve objects within a few milliseconds

- S3 Glacier Flexible Retrieval
  - Low-cost storage designed for data archiving
  - Able to retrieve objects within a few minutes to hours

- S3 Glacier Deep Archive
  - Lowest-cost object storage class ideal for archiving
  - Able to retrieve objects within 12 hours

- S3 Outputs
  - Creates S3 buckets on Amazon S3 Outposts
  - Makes it easier to retrieve, store, and access data on AWS Outposts

## Database

### Types
- Relational
  - Traditional applications, enterprise resource planning (ERP), customer relationship management (CRM), e-commerce
  - Amazon Aurora, Amazon RDS, Amazon Redshift
- Key-value 
  - High-traffic web applications, e-commerce systems, gaming applications
  - Amazon DynamoDB
- In-memory 
  - Caching, session management, gaming leaderboards, geospatial applications
  - Amazon ElastiCache, Amazon MemoryDB for Redis
- Document
  - Content management, catalogs, user profiles
  - Amazon DocumentDB (with MongoDB compatibility)
- Wide column
  - High-scale industrial apps for equipment maintenance, fleet management, route optimization
  - Amazon Keyspaces
- Graph
  - Fraud detection, social networking, recommendation engines
  - Amazon Neptune
- Time series
  - Internet of Things (IoT) applications, DevOps, industrial telemetry
  - Amazon Timestream
- Ledger
  - Systems of record, supply chain, registrations, banking transactions
  - Amazon Ledger Database Services (QLDB)


### Relational database

- **Amazon Aurora**
MySQL and PostgreSQL-compatible relational database built in the cloud for the cloud. It can run the database with multi-Regional replicas.

- **Amazon Relational Database Service (Amazon RDS)**
It's a service that enables you to run relational databases in the AWS Cloud.

- **Amazon Redshift**
It's a data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data.

- **Amazon Database Migration Service (Amazon DMS)**
It enables you to migrate relational databases, nonrelational databases, and other types of data stores.
Key-value database

### Key-value database

- **Amazon DynamoDB**
It's a key-value database service. It delivers single-digit millisecond performance at any scale.
  > DynamoDB is serverless, which means that you do not have to provision, patch, or manage servers. 

### In-memory database

- **Amazon ElastiCache**
It is a service that adds caching layers on top of your databases to help improve the read times of common requests. 
- It supports two types of data stores: Redis and Memcached.

- **Amazon DynamoDB Accelerator**
Amazon DynamoDB Accelerator (DAX) is an in-memory cache for DynamoDB. 
- It helps improve response times from single-digit milliseconds to microseconds.

### Document database

- **Amazon DocumentDB**
Amazon DocumentDB is a document database service that supports MongoDB workloads. (MongoDB is a document database program.)

### Graph database

- **Amazon Neptune**
It is a graph database service. 

### Time Series database

- **Amazon Timestream**
Fast, Scalable, Store and analyze trillions of events per day

### Ledger database
- **Amazon Quantum Ledger Database (Amazon QLDB)**
It's a ledger database service. You can use Amazon QLDB to review a complete history of all the changes that have been made to your application data.

### Blockchain database
- **Amazon Managed Blockchain**
It is a service that you can use to create and manage blockchain networks with open-source frameworks. 

# Security

## The shared responsibility model
- AWS responsibility "Security of the Cloud": AWS is responsible for protecting the infrastructure that runs all of the services offered in the AWS Cloud. This infrastructure is composed of the hardware, software, networking, and all of the physical and environmental controls that run AWS Cloud services.

- Customer responsibility "Security in the Cloud": Customer responsibility will be determined by the AWS Cloud services that a customer selects, sush as:
  - Platform, applications, and identity and access management;
  - Operating system, network, and firewall configuration;
  - Client-side data encryption and data integrity authentication;
  - Server-side encryption (File system and data)
  - Network traffic protection (Encryption, integrity, and identity)

## AWS Identity and Access Management (IAM)
It enables you to manage access to AWS services and resources securely.

- **AWS account root user**
When you first create an AWS account, you begin with an identity known as the root user. It has complete access to all the AWS services and resources in the account.

- **IAM users**
An IAM user is an identity that you create in AWS. It represents the person or application that interacts with AWS services and resources. It consists of a name and credentials.
  > By default, when you create a new IAM user in AWS, it has no permissions associated with it. To allow the IAM user to perform specific actions in AWS, such as launching an Amazon EC2 instance or creating an Amazon S3 bucket, you must grant the IAM user the necessary permissions.

- **IAM policies**
An IAM policy is a document that allows or denies permissions to AWS services and resources.  
  > **Best practices**
Follow the security principle of least privilege when granting permissions. By following this principle, you help to prevent users or roles from having more permissions than needed to perform their tasks. 

- **IAM groups**
An IAM group is a collection of IAM users. When you assign an IAM policy to a group, all users in the group are granted permissions specified by the policy.

- **IAM roles**
An IAM role is an identity that you can assume to gain temporary access to permissions.  
  - Before an IAM user, application, or service can assume an IAM role, they must be granted permission to switch to the role. When someone assumes an IAM role, they abandon all previous permissions that they had under a previous role and assume the permissions of the new role. 

  > **Best practice**
  IAM roles are ideal for situations in which access to services or resources needs to be granted temporarily, instead of long-term.  

- **Multi-factor authentication**
You might have needed to provide your password and then a second form of authentication, such as a random code sent to your phone. This is an example of multi-factor authentication(opens in a new tab).

## AWS Organizations
Suppose that your company has multiple AWS accounts. You can use AWS Organizations to consolidate and manage multiple AWS accounts within a central location. When you create an organization, AWS Organizations automatically creates a root, which is the parent container for all the accounts in your organization. 

- Service Control Policies (SCP) 
In AWS Organizations, you can centrally control permissions for the accounts in your organization by using service control policies (SCPs). SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.

- Organizational units
In AWS Organizations, you can group accounts into organizational units (OUs) to make it easier to manage accounts with similar business or security requirements. When you apply a policy to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy.  

- It can apply service control policies (SCPs) to the organization's root, an individual member account, or an OU.

## Compliance
### AWS Artifact
AWS Artifact is a service that provides on-demand access to AWS security and compliance reports and select online agreements. AWS Artifact consists of two main sections: AWS Artifact Agreements and AWS Artifact Reports.
- AWS Artifact Agreements
Suppose that your company needs to sign an agreement with AWS regarding your use of certain types of information throughout AWS services
- AWS Artifact Reports
Suppose that a member of your company’s development team is building an application and needs more information about their responsibility for complying with certain regulatory standards. You can advise them to access this information in AWS Artifact Reports.
### Customer Compliance Center
In the Customer Compliance Center, you can read customer compliance stories to discover how companies in regulated industries have solved various compliance, governance, and audit challenges.

## DDoS
### Denial-of-service attacks
A denial-of-service (DoS) attack is a deliberate attempt to make a website or application unavailable to users.
- The attack originates from a single source.

### Distributed denial-of-service attacks
In a distributed denial-of-service (DDoS) attack, multiple sources are used to start an attack that aims to make a website or application unavailable

### AWS Shield
AWS Shield is a service that protects applications against DDoS attacks. AWS Shield provides two levels of protection: Standard and Advanced.

- AWS Shield Standard: Automatically protects all AWS customers at no cost.
- AWS Shield Advanced: Is a paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks. 

## AWS Key Management Service (AWS KMS)
Enables you to perform encryption operations through the use of cryptographic keys. A cryptographic key is a random string of digits used for locking (encrypting) and unlocking (decrypting) data. 

## AWS WAF
It is a web application firewall that lets you monitor network requests that come into your web applications. 

- AWS WAF works together with Amazon CloudFront and an Application Load Balancer. AWS WAF works in a similar way to block or allow traffic. However, it does this by using a web access control list (ACL) to protect your AWS resources.

- You configure the web ACL to allow all requests except those from the IP addresses that you have specified.

## Amazon Inspector
It checks applications for security vulnerabilities and deviations from security best practices, such as open access to Amazon EC2 instances and installations of vulnerable software versions. 

## Amazon GuardDuty
It is a service that provides intelligent threat detection for your AWS infrastructure and resources. It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.

# Monitoring and Analytics

## Amazon CloudWatch
It is a web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics.

CloudWatch uses metrics to represent the data points for your resources. AWS services send metrics to CloudWatch. CloudWatch then uses these metrics to create graphs automatically that show how performance has changed over time. 

- CloudWatch alarms: You can create alarms that automatically perform actions if the value of your metric has gone above or below a predefined threshold.

## CloudWatch dashboard
This feature enables you to access all the metrics for your resources from a single location.

## AWS CloudTrail
It records API calls for your account and automatically detects unusual account activity 

### CloudTrail Insights
This optional feature allows CloudTrail to automatically detect unusual API activities in your AWS account and filter logs to assist with operational analysis and troubleshooting

##  AWS Trusted Advisor
AWS Trusted Advisor is a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices. Trusted Advisor compares its findings to AWS best practices in five categories: cost optimization, performance, security, fault tolerance, and service limits

# Pricing and supporting

## AWS Free Tier
It enables you to begin using certain services without having to worry about incurring costs for the specified period
Three types of offers are available: 
- Always Free
- 12 Months Free
- Trials

## AWS Billing & Cost Management dashboard
Use it to pay your AWS bill, monitor your usage, and analyze and control your costs.

Compare your current month-to-date balance with the previous month, and get a forecast of the next month based on current usage.

## Consolidated billing
In an earlier module, you learned about AWS Organizations, a service that enables you to manage multiple AWS accounts from a central location. AWS Organizations also provides the option for consolidated billing.

The consolidated billing feature of AWS Organizations enables you to receive a single bill for all AWS accounts in your organization. By consolidating, you can easily track the combined costs of all the linked accounts in your organization. 

>The default maximum number of accounts allowed for an organization is 4, but you can contact AWS Support to increase your quota, if needed.

## AWS Budgets
Create budgets to plan your service usage, service costs, and instance reservations. The information in AWS Budgets updates three times a day. This helps you to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.

> In AWS Budgets, you can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.

## AWS Cost Explorer
It's a tool that lets you visualize, understand, and manage your AWS costs and usage over time.

## AWS Support
AWS offers four different Support plans to help you troubleshoot issues, lower costs, and efficiently use AWS services. 

- Basic
It's free for all AWS customers. It includes access to whitepapers, documentation, and support communities. With Basic Support, you can also contact AWS for billing questions and service limit increases.

- Developer
Customers in the Developer Support plan have access to features such as:
  - Best practice guidance
  - Client-side diagnostic tools
  - Building-block architecture support, which consists of guidance for how to use AWS offerings, features, and services together

- Business
Customers with a Business Support plan have access to additional features, including: 
  - Use-case guidance to identify AWS offerings, features, and services that can best support your specific needs
  - All AWS Trusted Advisor checks
  - Limited support for third-party software, such as common operating systems and application stack components

- Enterprise On-Ramp
  - A pool of Technical Account Managers to provide proactive guidance and coordinate access to programs and AWS experts
  - A Cost Optimization workshop (one per year)
  - A Concierge support team for billing and account assistance
  - Tools to monitor costs and performance through Trusted Advisor and Health API/Dashboard

- Enterprise
  - Consultative review and architecture guidance
  - Infrastructure Event Management support
  - Cost Optimization Workshop and tools
  - Support automation workflows
  - 15 minutes or less response time for business-critical issues

## Technical Account Manager (TAM)
The Enterprise On-Ramp and Enterprise Support plans include access to a Technical Account Manager (TAM).

> The TAM is your primary point of contact at AWS. If your company subscribes to Enterprise Support or Enterprise On-Ramp, your TAM educates, empowers, and evolves your cloud journey across the full range of AWS services.

## AWS Marketplace
It's a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS.

> AWS Marketplace offers products in several categories, such as Infrastructure Software, DevOps, Data Products, Professional Services, Business Applications, Machine Learning, Industries, and Internet of Things (IoT).

# Migration and Innovation
## AWS Cloud Adoption Framework
It organizes guidance into six areas of focus, called Perspectives. Each Perspective addresses distinct responsibilities. The planning process helps the right people across the organization prepare for the changes ahead.

In general, the **Business**, **People**, and **Governance Perspectives** focus on business capabilities, whereas the **Platform**, **Security**, and **Operations Perspectives** focus on technical capabilities.

- Business
Ensures that IT aligns with business needs and that IT investments link to key business results.
Common roles in the Business Perspective include: 
  - Business managers
  - Finance managers
  - Budget owners
  - Strategy stakeholders

- People
Supports development of an organization-wide change management strategy for successful cloud adoption.
Common roles in the People Perspective include: 
  - Human resources
  - Staffing
  - People managers

- Governance Perspective
Focuses on the skills and processes to align IT strategy with business strategy. This ensures that you maximize the business value and minimize risks.
Common roles in the Governance Perspective include: 
  - Chief Information Officer (CIO)
  - Program managers
  - Enterprise architects
  - Business analysts
  - Portfolio managers

- Platform
Includes principles and patterns for implementing new solutions on the cloud, and migrating on-premises workloads to the cloud.
Common roles in the Platform Perspective include: 
  - Chief Technology Officer (CTO)
  - IT managers
  - Solutions architects

- Security
Ensures that the organization meets security objectives for visibility, auditability, control, and agility. 
Common roles in the Security Perspective include: 
  - Chief Information Security Officer (CISO)
  - IT security managers
  - IT security analysts

- Operations
Helps you to enable, run, use, operate, and recover IT workloads to the level agreed upon with your business stakeholders.
Common roles in the Operations Perspective include: 
  - IT operations managers
  - IT support managers

## 6 R's of migration
When migrating applications to the cloud, six of the most common migration strategies that you can implement are:

- Rehosting
Also known as “lift-and-shift” involves moving applications without changes

- Replatforming
Also known as “lift, tinker, and shift,” involves making a few cloud optimizations to realize a tangible benefit. Optimization is achieved without changing the core architecture of the application.

- Refactoring/re-architecting
Involves reimagining how an application is architected and developed by using cloud-native features. Refactoring is driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.

- Repurchasing
Involves moving from a traditional license to a software-as-a-service model. 

- Retaining
Consists of keeping applications that are critical for the business in the source environment. This might include applications that require major refactoring before they can be migrated, or, work that can be postponed until a later time.

- Retiring
It's the process of removing applications that are no longer needed.

## AWS Snow Family
It's a collection of physical devices that help to physically transport up to exabytes of data into and out of AWS. 

# The Cloud Journey
## AWS Well-Architected Framework
Helps you understand how to design and operate reliable, secure, efficient, and cost-effective systems in the AWS Cloud. It provides a way for you to consistently measure your architecture against best practices and design principles and identify areas for improvement.

The Well-Architected Framework is based on six pillars: 

- Operational excellence
It is the ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures.  

- Security
The Security pillar is the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies. 

- Reliability
Reliability is the ability of a system to do the following:
  - Recover from infrastructure or service disruptions
  - Dynamically acquire computing resources to meet demand
  - Mitigate disruptions such as misconfigurations or transient network issues
Reliability includes testing recovery procedures, scaling horizontally to increase aggregate system availability, and automatically recovering from failure.

- Performance efficiency
It's the ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve. 

- Cost optimization
It is the ability to run systems to deliver business value at the lowest price point. 

- Sustainability
Sustainability is the ability to continually improve sustainability impacts by reducing energy consumption and increasing efficiency across all components of a workload by maximizing the benefits from the provisioned resources and minimizing the total resources required.