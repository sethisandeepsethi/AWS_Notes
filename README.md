# Cloud Computing Basics
## Six Advantages of Cloud Computing
1. Trade fixed expense for variable expense 
1. Benefit from massive economies of scale 
1. Stop guessing capacity
1. Increase speed and agility
1. Stop spending money running and maintaining data centers
1. Go global in minutes 


## IAM
* Identity & Access Management
* Has Users and Groups
* Policy is assigned to them
* Policy contains permissions in the form of JSON
* IAM Roles
* IAM security Tools:
> * **IAM Credentials Report** : List of users and theirs credentials status in an AWS account
> * **IAM Access Advisor** : Shows permissions granted to an user and when those permissions were last accessed
* Access Keys: Used to access AWS using CLI or SDK

## EC2
* Elastic Cloud Compute
* Security Groups:
> * act as a firewall 
> * contains only **ALLOW** rules
* EC2 Instance Connect:
> * Connects to an EC2 instance within your browser
> * Works out-of-box only with Amazon Linux 2

### LightSail
* Amazon LightSail is great for users who do not have deep AWS technical expertise as it make it very easy to provision compute services

## Global, Regional or a Zonal service
* An AWS resource can be a Global, Regional or a Zonal service. 
* A Global service means that it covers all of the AWS Regions across the globe
* A regional service means that a resource is only applicable to one specific region at a time. 
* A regional service may or may not have the ability to replicate the same resource to another region. 
* A Zonal service can only exist in one Availability Zone.
* Services that are considered as **global** services are **IAM**, **STS**, **Route 53**, **CloudFront** and **WAF**. 
* For Zonal services, the examples are EC2 Instance and EBS Volumes where they are tied to the Availability Zone where they were launched. 
* Note that although EBS Volumes are considered as a zonal service, the EBS snapshots are considered as a regional since it is not tied to a specific Availability Zone. 
* The rest of the services are regional in scope.
* AWS charges you for data transferred between two different Regions. 
* This is similar to the costs incurred from the data transfer between the AWS network and the public internet.

# AWS Migration and Transfer Services
## AWS Migration Hub
Transfer happens via VPN  or AWS Direct Connect

Collectively migration tools are called AWS Migration Hub. It consists of following:
* **AWS Server Migration Service** - from local servers (where AWS SMS Connector is installed ) to AMI. Then this AMI is used to create EC2 instances
* **AWS Database Migration Service** - from local DB (or Other DB hosted in EC2, RDS etc) to Amazon RDS / RedShift / Aurora / DynamoDB / Document DB etc
* **AWS DataSync** - from NAS / File server (where DataSync software agent is installed) to Amazon S3 or EFS or Amazon FSx for Windows

## AWS Snowball Family
* AWS Snowball ( 50 - 80 TB - petabyte scale) and Snowmobile (100 PB - exabyte scale) migrate large volume of data to AWS
* Snowcone small device
* Snowball Client needs to be installed in local computer

# AWS Machine Learning Services
* **AWS Rekognition** - Identify objects, people, text, scenes and activities in images and videos
* **Amazon Transcribe** - Add speech to text (including recorded) capabilities to application
* **Amazon Polly** - turns text into lifelike speech thereby allowing you to create applications that talk.
* **Amazon Translate** - Neural machine translation service that can localize some content like websites. Amazon Translate does not provide automatic translation of third-party website interfaces.
* **Amazon Textract** - Automatically extract printed text, handwriting and data from any document like PDFs, images, forms, table etc
* **Amazon SageMaker** - Helps data scientists and developers to prepare, build, train and deploy high quality ML models
* **Amazon Comprehend** - A natural-language processing (NLP) service that uses ML to comprehend information from  unstructured data like detecting customer sentiment
* **Amazon Lex** -  A conversational AI for chatbots that can be used to build conversion interface into any application using voice and text
* **Amazon Devops Guru** - Cloud operations service for improving application operational performance and availability. 

# AWS Pricing
## Pricing Fundamentals
* Pay as you go
* Save when you reserve
* Pay less by using more

## Amazon EC2 Pricing Options
1. **On-Demand**: No discount-no commitments, dev/test, short term, unpredictable workloads
1. **Reserved**: 1 or 3 yrs commitment, upto 75% discount, predictable workloads
1. **Spot Instances**: Upto 90% discount for unused AWS capacity, can be terminated any time
1. **Dedicated Instances**: Pay per Instance
1. **Dedicated host**: Dedicated physical server, Socket/core visibility, pay per host
1. **Savings Plan**: Consistent amount of compute usage (EC2, Fargate, Lambda) for 1 or 3 yrs

## AWS Support Plans
There are four AWS support plans available:
1. **Basic** – billing and account support only (access to forums only).
1. **Developer** – business hours support via email.
1. **Business** – 24×7 email, chat, and phone support.
1. **Enterprise** – 24×7 email, chat, and phone support.

**Basic Support** is included for all AWS customers and includes:
* Customer Service and Communities - 24x7 access to customer service, documentation, whitepapers, and AWS re:Post.
* AWS Trusted Advisor - Access to core Trusted Advisor checks and guidance to provision your resources following best practices to increase performance and improve security.
* AWS Personal Health Dashboard - A personalized view of the health of AWS services, and alerts when your resources are impacted.


https://aws.amazon.com/premiumsupport/plans/
| Feature | Developer | Business | Enterprise On-Ramp | Enterprise |
|---------|---------|---------|---------|---------|
|| Recommended if you are experimenting or testing in AWS | Minimum recommended tier if you have production workloads in AWS | Recommended if you have production and/or business critical workloads in AWS.| Recommended if you have business and/or mission critical workloads in AWS. |
| AWS Trusted Advisor Best Practice Check | Service Quota and basic Security checks | Full set of checks | Full set of checks | Full set of checks |
| Technical Support | Business hours email access to Cloud Support  Associates | 24x7 phone, email, and chat access to Cloud Support Engineers | 24x7 phone, email, and chat access to Cloud Support Engineers | 24x7 phone, email, and chat access to Cloud Support Engineers |
| Third-Party Software Support || Interoperability and configuration guidance and troubleshooting | Interoperability and configuration guidance and troubleshooting | Interoperability and configuration guidance and troubleshooting |
| Infrastructure Event Management (support during the preparation and execution of planned events, such as shopping holidays, product launches, and migrations)|| for additional fee | one per year | included |
| Technical Account Management |||A pool of Technical Account Managers | Designated Technical Account Manager (TAM) |
| Account Assistance ||| Concierge Support Team | Concierge Support Team |

## Consolidated Billing
* Feature of AWS Organizations
* One bill for multiple accounts under an organization
* No extra fee for consolidated billing
* Combine the usage across all accounts to share volume pricing & Reserved instance discount
* Automatically terminate AWS resources if budget thresholds are exceeded

## AWS Pricing & Billing Tools
### AWS Pricing Calculator
* To estimate cost of your aws architecture solution
* Site: calculator.aws

### AWS Budgets
* Set custom usage and reservation budgets
* Configure alerts when you exceed or forecast to exceed some set thresholds

### AWS Compute Optimizer
* Recommends optimal AWS resources for your workloads to reduce costs and improve performance
* Uses machine learning to analyze historical utilization metrics
* Helps you choose optimal configurations for EC2 instances, EBS volumes and Lambda functions, based on your utilization data.
* Delivers all recommendations regardless of the cost implications.

### AWS Cost Explorer
* Free tool to view chart of your costs
* View cost data of past 13 months and forecast for the next 3 months
* Can  be used to discover patterns of spending for various AWS resources and services
* It CANNOT check resource utilization. For that we can use AWS Trusted Adviser.

### AWS Cost & Usage report
* Lists AWS usage for each service category used by an account and its IAM users
* Track your Amazon EC2 Reserved Instance (RI) usage
* Report breaks down cost by - hour, day, month, product, resource, tag
* Publish AWS billing report to an Amazon S3 bucket	
* Can update report upto 3 times a day
* You can also load your cost and usage information into Amazon Athena, Amazon Redshift, AWS QuickSight, or a tool of your choice.
* Uses AWS CUR API

### AWS Price List API
* Query the prices of AWS service
* Has 2 components; 
1. Price List Service API (aka Query API) - query with JSON
1. AWS Price List API (aka Bulk API) - query with HTML
* Alerts sent by SNS when prices change - can be used to build custom tool when prices of AWS change

### AWS Credit
* Note that it is not a tool 
* Credits are applied in the following order:
> Soonest expiring <br>
> Least number of applicable products <br>
> Oldest credit <br>

# AWS Well-Architected Framework
## AWS Well-Architected
Consists of:
* AWS Well-Architected **Guidance**: Documentation
* AWS Well-Architected **Tool**: Takes input about how we are setting up our environment and it will then provide guidance in terms of best practices for architecture
* AWS Well-Architected **Lenses**: Deep dive on industry verticals
* AWS Well-Architected **Center**: provides reference architecture diagrams, vetted architecture solutions, Well-Architected best practices, patterns, icons etc.

## Six Pillars of Well Architected Framework
//TO DO - Best practices associated with each of these pillars
1. Operational Excellence - _Use CloudFormation to deploy infrastructure_
1. Security - _Attach a WebACL to a CloudFront distribution_
1. Reliability - _Amazon RDS Multi-AZ deployment_
1. Performance Efficiency - _Amazon EBS provisioned IOPS volume_
1. Cost Optimization
1. Sustainability 

## Design Principles of Six Pillars of Well Architected Framework
| Pillar | Design Principles |
| ------ | ----------------- |
| Operational Excellence | Perform operations as code<br>Make frequent, small, reversible changes<br>Refine operations procedures frequently<br>Anticipate failure<br>Learn from all operational failures |
| Security | Implement a strong identity foundation<br>Enable traceability<br>Apply security at all layers<br>Automate security best practices<br>Protect data in transit and at rest<br>Keep people away from data<br>Prepare for security events |
| Reliability| Automatically recover from failure<br>Test recovery procedures<br>Scale horizontally to increase aggregate workload availability<br>Stop guessing capacity<br>Manage change in automation |
| Performance Efficiency | Democratize advanced technologies<br>Go global in minutes<br>Use serverless architectures<br>Experiment more often<br>Consider mechanical sympathy |
| Cost Optimization | Implement cloud financial management<br>Adopt a consumption model<br>Measure overall efficiency<br>Stop spending money on undifferentiated heavy lifting<br>Analyze and attribute expenditure |
| Sustainability | Understand your impact<br>Establish sustainability goals<br>Maximize utilization<br>Anticipate and adopt new, more efficient hardware and software offerings<br>Use managed services<br>Reduce the downstream impact of your cloud workloads |

# Protecting Secrets
## Systems Manager Parameter Store
* Secure, hierarchical storage for configuration data and secrets
* Can store data such as passwords, database strings, license codes as parameter values
* Can store values as plaintext or ciphertext

## AWS Secrets Manager
* Similar to Parameter Store
* Might be costly as compared to parameter store but provides extra features
* Allows native and automatic key rotation
* Central auditing for secrets rotations
* Fine-grained permission

# Encryption
## AWS Certificate Manager - (ACM)
* Create, store and renew SSL/TLS X.509 certificates
* Supports single domains and multiple domains (using wild cards)

## AWS Key Management Service (KMS)
* Create and manage symmetric and asymmetric encryption keys
* Provides 2 types of keys - Customer Managed Keys: created by developer and AWS Managed Keys

## CloudHSM
* Cloud based hardware security module (HSM)
* Runs in your VPC
* Single tenant solution

# Logging &  Auditing
## Amazon CloudWatch Logs
* Collects applications and system logs from EC2 Instances, AWS CloudTrail, Route 53 and other sources
* CloudWatch logs does not record AWS Management Console actions and API calls. This is done by CloudTrail.
* Log data is encrypted while in transit and while it is at rest.
* By default, logs are kept indefinitely and never expire. 
* You can adjust the retention policy for each log group - indefinite or between 1 day and 10 years. This service is not entirely free
* The CloudWatch Logs agent makes it easy to quickly send both rotated and non-rotated log data off of a host and into the log service  
* **CloudWatch Alarms** can be used to create alarms that automatically stop, terminate, reboot, or recover your EC2 instances

## AWS CloudTrail
* Logs API activity for auditing
* By default, management events are logged and retained for 90 days
* A CloudTrail Trail can log events to S3 for indefinite retention
* By default, the log files delivered by CloudTrail to your S3 bucket are encrypted using server-side encryption with Amazon S3–managed encryption keys (SSE-S3).

## VPC Flow Logs
* Captures info about the IP traffic going to and from network interface in a VPC
* Logging data is stored using Amazon CloudWatch logs
* Flow logs can be created at the level of - VPC, Subnet and Network Interface

## Access Logs
* ELB Access Logs: logs info about requests sent to the LB, can optionally be stored in S3
* S3 Access Logs:  logs info about requests made to a bucket in another target bucket. Disabled by default

## AWS Artifact 
* It is not a service, it's a no-cost, self-service portal for on-demand access to AWS’ compliance reports.
* Allows you to download AWS security and compliance documents such as ISO certifications and SOC reports.

# Detect & Respond
## Amazon Detective
* Analyze, investigate and identify root cause of potential security issues and activities
* Collects data from various sources like VPC Flow Logs, CloudTrail and GuardDuty

## Amazon Inspector
* Monitors network accessibility of your EC2 instances and the security state of your applications that run on those instances.

## AWS GuardDuty
* Threat detection service
* Detects account compromise, instance compromise, malicious reconnaissance, bucket compromise
* Continuous monitoring of events across: AWS CloudTRail, VPC Flow logs, DNS logs

## Amazon Macie	
* Helps to protect sensitive data on S3
* Enables compliance and preventive security
* Can identify a variety of data types like Personally Identifiable Information (PII), Protected Health Info (PHI), regulatory documents, API Keys and secret keys

TODO: https://aws.amazon.com/products/security/?nc=sn&loc=2

# Firewalls & DDoS Protection
## AWS Web Application Firewall (WAF)
* Firewall especially for web applications
* Offers protection from common web exploits at layer 7 (Application layer)
* Lets you monitor the HTTP and HTTPS requests that are forwarded to an Amazon API Gateway API, Amazon CloudFront or an Application Load Balancer
* Can filter web traffic based on conditions that include IP addresses, HTTP headers & body, and custom URIs
* Create rules to block common web exploits like SQL Injection , cross-site scripting etc 
* Can be used in front of Amazon CloudFront, ALB before EC2, API Gateway, AWS AppSync
* AWS WAF charges based on the number of web access control lists (web ACLs) that you create, the number of rules that you add per web ACL, and the number of web requests that you receive

## AWS Shield
* Managed DDoS protection service thus minimize app downtime and latency	
* Standard tier - no cost - integrated with CloudFront
* Advanced tier - ~3k USD per month
### AWS Shield Standard
* Defends against most common, frequently occurring network (layer 3) and transport layer (layer 4) DDoS attacks
* Helps protect all AWS customers at no charge
* You get better protection if you are using Amazon CloudFront and Amazon Route 53
### AWS Shield Advanced
* Includes intelligent DDoS attack detection and mitigation for network layer (layer 3), transport layer (layer 4) and application layer (layer 7) attacks.
* Provides expanded DDoS attack protection for web applications running on the following resources: Amazon Elastic Compute Cloud, Elastic Load Balancing (ELB), Amazon CloudFront, Amazon Route 53, AWS Global Accelerator.

# Management & Configuration
## AWS Organizations
* Allows you to centrally manage multiple AWS accounts into an organization
* Available in 2 feature set:
1. * Consolidated Billing - single bill across all aws accounts 
1. * All features ( including Service Control Policies )

## AWS Control Tower
* Simplifies the process of creating multi-account environments ( AWS Organizations can help to manage the multi-account environment) 
* Sets up governance, compliance and security guardrails
* Integrates with other services to set up the environment like - AWS Organizations, AWS Config, CloudTrail, S3, SNS, CloudFormation, AWS SSO etc
* Examples of guardrails that Control Tower can set up:
1. * Disallowing public write access to S3 buckets
1. * Disallowing access to root user without MFA
1. * Enable encryption of EBS volumes

## AWS Systems Manager
* Use AWS Systems Manager to organize, monitor, and automate management tasks on your AWS resources
* Manages many AWS resources like EC2, S3, RDS etc
* _Usecase_ - to automate database patching (DB deployed in EC2) according to a schedule.
* Components:
1. * Automation
1. * Run Command
1. * Inventory
1. * Patch Manager
1. * Sessions Manager
1. * Parameter Store

## AWS Service Catalog
* Enables users to quickly deploy only the approved IT  services they need
* The IT services can include machine images, servers, softwares, databases and multi-tier application architecture 
* Uses CloudFormation templates behind the scene

## AWS Config
* A service that can be used to audit AWS resources by validating if resources are configured in a certain way or not
* AWS Config can record info into S3 bucket
* Can sent changes in Config as SNS alerts or CloudWatch events

## AWS Trusted Advisor
* Provides best practice recommendations 
* You can't receive technical assistance from this service
* Trusted Advisor analyze your AWS environment based on certain checks and recommend actions to follow best practices
* Provides advise after performing checks on following categories:(Category Name / Example checks ) 
1. * Cost optimization - low utilization Amazon EC2 instances, Unassociated Elastic IP Addresses
1. * Performance - High Utilization Amazon EC2 Instances, Large Number of Rules in an EC2 Security Group
1. * Security - Security Groups – Unrestricted Access, MFA on Root Account
1. * Fault tolerance - Amazon RDS Multi-AZ, Load Balancer Optimization i.e. running equal no of instances across multiple AZs in a Region
1. * Service quotas - Checks for usage that is more than 80% for any service
* AWS Basic Support and Developer Support customers can access core security checks and all checks for service quotas
* AWS Business Support and Enterprise Support customers can access all checks

## AWS Personal Health Dashboard
* Provides alerts and remediation guidance when AWS is experiencing events that may impact you
* Gives personalized view of performance and availability of AWS services that you are using
* Provides notifications to help you plan for scheduled activities  

## Service Health Dashboard                                                                                                                                                                                                 
* Shows current status of AWD services
* Not personalized 

# Databases & Analytics
## Amazon Relational Database Service ( RDS )
* RDS is relational and OLTP type of DB
* Runs on EC2 instance so you must have to choose and instance type
* Supports following databases:
1. * SQL Server
1. * Oracle
1. * MySQL Server
1. * PostgreSQL
1. * MariaDB
1. * Aurora
* If you want to use other DBs then u cannot use RDS. You have to install it on EC2
* Cannot SSH into RDS instances
* Scales up by increasing instance size (compute and storage) -  You cannot adjust CPU and RAM dynamically, you must change the instance type and reboot the database instance.
* Scales out for read/queries only - Read replicas can be used for read heavy workloads
* Disaster recovery with Multi-AZ option
* Amazon RDS does not enable encryption by default. Encryption is an option, but the user must select it.

### Read Replicas
* Are for read scalability (horizontal scalability)
* Up to 5 read replicas per DB
* Within AZ, Cross AZ, Cross Region
* Used only for SELECT statements

### RDS Multi - AZ
* Used for disaster recovery
* Has SYNC replication
* Not to be used for scaling
* No manual intervention required in case infra failure in one AZ since the DB instance Endpoint remains same so application can resume DB operations

### Differences between Multi-AZ, Multi-Region and Read Replica deployments for RDS
| Feature | Multi-AZ Deployments | Multi-Region Deployments | Read Replica |
|---------|----------------------|--------------------|-----------------|
| Purpose | - High Availability | Purpose - Disaster recovery & local performance | Purpose Scalability |
| Replication | Aurora - Asynchronous <br> Non Aurora - Synchronous| Asynchronous | Asynchronous |
| Deployment | At least 2 AZ in a region | Each region can have Multi-AZ deployment | Within AZ, Cross AZ, Cross Region |

## Amazon Aurora
* AWS proprietary database in RDS family
* A distributed, fault tolerant, self healing storage system that auto-scales upto 64 TB per database instance 
* Can have 15 replicas
* Supports cross-region replication
* Compatible with MySQL and PostgreSQL
* 5 times faster than MySQL
* 3 times faster than PostgreSQL

## Amazon DynamoDB
* Fully managed, highly available, serverless NoSQL DB service
* Key-value store and document store
* Fully serverless service
* Push button scaling i.e. you can scale the application without any downtime
* Consists of Tables, Items (row of a table) and Attributes (values)
* **DynamoDB Accelerator (DAX)** : Fully managed in-memory cache for DynamoDB that increases performance (microsecond latency)
* Backup: on-demand backup and restore with Point-in-time recovery down to the second in last 35 days
* **Global Tables**: Fully managed multi-region, multi-master solution	

## Amazon RedShift
* Fast fully- managed **data warehouse** used to perform data analysis using SQL and existing BI tools
* Its a OLAP ( Online Analytics Processing ) relational database
* Uses EC2 so you must choose instance family/type
* Always keeps 3 copies of your data
* Provides continuous / incremental backups
* Amazon Redshift does not enable encryption by default. Encryption is an option, but the user must select it.

## Amazon ElastiCache
* Fully managed implementation of **Redis** and **Memcached**
* ElastiCache is key-value store
* In memory database offering high performance and low latency
* Used to reduce the READ workload
* Can be put in front of databases such as RDS and DyanamoDB
* Runs on EC2 so you must choose instance family/type

| REDIS | MEMCACHED |
|------ | ----------- |
| Multi AZ | Multinode with sharding |
| Read replicas | No replication or HA |
| Has data persistence | No persistence |
| Backup and restore | No backup and restore |
|  | Multi-threaded architecture |

* Use cases:
> 1. _Web session store_: Redis : in load-balanced webservers store session info in Redis so if a server is lost, session info kept saved in Redis for another server to pick it up
> 1. _Database caching_: Memcached: Use Memcached in front of RDS to cache popular queries
> 1. _Leaderboards_: Redis: Use Redis for a live leaderboard for million of users

### Lazy Loading / Cache- Aside
* Only requested data is cached

### Write Through
* Add or update cache whenever data is updated

## Amazon EMR
* Amazon Elastic MapReduce
* It is a managed cluster platform that simplifies running big data frameworks like Apache Hadoop and Apache Spark on AWS
* Used to process data for analytic purposes and business intelligence workloads

## Amazon Athena
* An interactive query service to analyze data in S3 using SQL
* Serverless
* You pay only for the queries that you run
* Note: Although also run analytics using SQL but it cannot run directly on data stored in S3

## AWS Glue 
* Fully managed extract, transform, and load (ETL) service 
* that makes it easy for customers to prepare and load their data for analytics.

# Deployment & Automation
## Amazon CloudFront
* CloudFront is a Content Delivery Network (CDN) that allows you to store (cache) your content at the “edge locations”
* Reduces latency for global users
* Can be used for data, videos, applications and APIs
* Also provides protection against DDoS attack
* _Usecases_:
> * Static asset caching
> * Live & on-demand video streaming
> * Security - integrates seamlessly with AWS Shield for Layer 3/4 DDoS mitigation and AWS WAF for Layer 7 protection.
> * Customizable content delivery with Lambda@Edge 
> * Dynamic content & API acceleration - secure and accelerate your WebSocket traffic as well as API calls.
> * Software distribution

## AWS Global Accelerator
* Uses AWS global network and edge locations (like CloudFront)
* It provides you with static Anycast IP addresses.
* This enables traffic to ingress onto the AWS global network as close to your users as possible.
* CloudFront uses Edge Locations to cache content while Global Accelerator uses Edge Locations to find an optimal pathway to the nearest regional endpoint.
* CF improves performance for cacheable content for HTTP/S while GA improves performance for a wide range of applications over TCP and UDP
* GA proxies connection to application in one or more AWS region
* Provides failover between regions
* CloudFront is not capable of providing static Anycast IP addresses.

**NOTE:** _Amazon ElastiCache_ cannot route user traffic to the optimal endpoint. ElastiCache is primarily used to improve web applications' performance by retrieving information from a fast, managed, in-memory system.
_Amazon Route 53_ also doesn't use a static Anycast IP address to minimize the latency for end-users. It is mainly used to translate specific domain names into their corresponding IP addresses.

## AWS CloudFormation
* Uses YAML or JSON template to describe end state of the infrastructure we are either provisioning or changing.
* Deploys infrastructure using code
* Can be used to deploy almost any AWS service	
* Creates a Stack based on template
* Can easily rollback or delete the entire stack
> * There is no off-the-shelf solution or service that the company can use to move its IT resources from an AWS Region to another.
> * CloudFormation cannot help with moving data and applications into another Region.
> * Therefore, The company should just start creating new resources in the destination AWS Region and then migrate the relevant data and applications into this new AWS Region

## Elastic Beanstalk
* Platform as a Service - PaaS solution for web application
* Managed all the underlying infrastructure like VPC, subnets, LBs, AutoScaling, Database etc
* Developer need to focus only on the coding
* Deploys web apps based on Java, .Net, php, node.js, python, ruby, go and docker 
* EB behind the scenes uses CloudFormation

## Developer Tools - Code*
//TODO

## AWS X-Ray
* X-Ray helps developers to analyze and debug serverless and distributed applications especially those built using microservices architecture
* Supports applications running on EC2, ECS, Lambda, Elastic Beanstalk
* Need to integrate X-Ray SDK with your application and install the X-Ray agent

## AWS Quick Starts 
* These help you to quickly deploy popular technologies on AWS, based on AWS best practices for security and high availability. 
* These accelerators reduce hundreds of manual procedures into just a few steps, so you can build your production environment quickly and start using it immediately.
* Each Quick Start includes AWS CloudFormation templates that automate the deployment and a guide that discusses the architecture and provides step-by-step deployment instructions

# Networking
## Virtual Private Cloud - VPC
* A VPC is a logically isolated portion of AWS Cloud within a region
* A VPC cannot span across different regions
* A VPC can have one or more AZ. Each AZ has at least one Subnet which might be public or private
* Each VPC has a set of IP address space known as CIDR blocks. And each component within the VPC has a unique IP address that falls into the CIDR block
* A Router is component within VPC that is responsible to route network traffic via routing table
* If the destination IP address falls within CIDR block range then Router routes the traffic within VPC across AZ or Subnets
* For all other IP addresses Router routes the network traffic to Internet Gateway 
* Internet Gateway is attached to the VPC and is used to connect to the internet 
* When you create a VPC, you must specify a range of IPv4 addresses in the form of a Classless Inter - Domain Routing (CIDR) block
* By default you can create upto 5 VPC per region
* A default VPC is created within the Region selected with a subnet in each AZ

_Common terms:_

* **Subnet**: A segment of VPC’s IP address range where you can place groups of isolated resources
* **Internet Gateway (Egress only Internet gateway)**: The Amazon VPC side of connection to the public Internet
* **Router**: Routers interconnect subnets and direct traffic between internet gateways, virtual private gateways, NAT gateways and subnets
* **VPC EndPoints**: private connection to public AWS service
* **NAT Instance**: Enables internet access for EC2 instances in private subnets (managed by you)
* **NAT Gateway**: Enables internet access for EC2 instances in private subnets (managed by AWS)
* **Virtual Private Gateway**: The Amazon VPC side of a Virtual Private Network - VPN connection
* **Customer Gateway**: Customer side of a VPN connection
* **Security Groups**: Instance level firewall
* **Network ACL**: Subnet level firewall

## Security Groups
* Firewalls for EC2 instances
* Operates at Instance level
* Supports allow rules only
* Stateful -  For example, if you send a request from an instance, its response is allowed to the instance regardless of the inbound security group rules. Responses to allowed inbound traffic are allowed to leave the instance, regardless of the outbound rules.
* When you first create a security group, it has no inbound rules. Therefore, no inbound traffic is allowed by default
* When you first create a security group, it has an outbound rule that allows all outbound traffic from the resource. You can remove the rule and add outbound rules that allow specific outbound traffic only
* Evaluates all rules
* Applies to an instance only if associated to a group

## NACL - Network Access Control List
* Optional layer of security for your VPC 
* Firewall at the Subnet level
* Operates at the Subnet level
* Supports allow and deny rules
* A network ACL has separate inbound and outbound rules, and each rule can either allow or deny traffic
* Each VPC comes with a default NACL that allows all inbound and outbound traffic
* If we create a custom NACL then by default it denies all inbound and outbound traffic until rules are added
* You can associate a network ACL with multiple subnets. However, a subnet can be associated with only one network ACL at a time 
* Stateless - responses to allowed inbound traffic are subject to the rules for outbound traffic (and vice versa).
* Processes rules in order
* Automatically applies to all Instances in the subnet it is associated with (therefore, it provides an additional layer of defense if the security group rules are too permissive)

## IP Addresses
* Public IP is dynamic and is lost when instance is stopped
* Public IPs cannot move between instances
* Private IPs are attached to all instances
* Private IPs are retained when instance is stopped
* Elastic IPs are static public addresses
* Elastic IPs are retained when an instance is stopped
* Elastic IPs can be moved between instances
* Elastic IPs are chargeable when not in use
* While your instance is running, you are not charged for one Elastic IP address associated with the instance, but you are charged for any additional Elastic IP addresses associated with the instance.
* EIPs are assigned within your specific region and cannot be used in a different region

## NAT Instances & Gateways
* NAT - Network Address Translation
* Used for accessing internet from private subnets as its EC2 instances have private IP addresses only and private route table does not have entry for the Internet gateway 
* Deployed in public subnets and have an Elastic IP which is used by Internet gateway and private IP for network within VPC
* Route tables for private subnets must have entry for NAT gateway or instances for the IP addresses that are outside of the range of VPC CIDR block
* NAT instances are managed by you are the older way of doing connection
* NAT gateways are managed by AWS and is newer approach
* NAT gateways provides elastic scalability upto 45 GBps but NAT instances scale up manually by instance type
* NAT gateways provides automatic high availability within an AZ but for NAT instance HA is possible by using scripting for multiple NAT Instances 
* You cannot associate security groups with NAT gateways. You can associate them with the resources behind the NAT gateway to control inbound and outbound traffic.
* You can associate your NAT instance and the resources behind your NAT instance to control inbound and outbound traffic.
* Only NAT Instances can be used as bastion server.

## VPC EndPoints
* A VPC endpoint enables you to privately connect your VPC to supported AWS services
* Powered by AWS PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. 
* Instances in your VPC do not require public IP addresses to communicate with resources in the service. 
* Traffic between your VPC and the other service does not leave the Amazon network.
* There are two types of VPC endpoints: interface endpoints and gateway endpoints.

### VPC Interface Endpoint
* An interface endpoint is an elastic network interface with a private IP address
* The private IP address is from IP address range of your subnet that serves as an entry point for traffic destined to a supported service. 
* Interface endpoints are powered by AWS PrivateLink, a technology that enables you to privately access services by using private IP addresses.

### VPC Gateway Endpoint
* A gateway endpoint is a gateway that you specify as a target for a route in your route table for traffic destined to a supported AWS service. 
* Only 2 services supports VPC Endpoint Gateway - 1. Amazon S3  2. DynamoDB
* All other services that support VPC Endpoints use a VPC Endpoint Interface.

## VPC Peering
* VPC Peering enables routing using private IP addresses among VPCs privately
* VPCs can be in different accounts and Regions
* Each VPC’s CIDR block must not overlap
* VPC Peering connections are NOT transitive - full mesh required
* With growing VPCs, this gets difficult to manage.

## AWS Transit Gateway
* AWS Transit Gateway connects VPCs and on-premises networks through a central hub. 
* This simplifies your network and puts an end to complex peering relationships. It acts as a cloud router – each new connection is only made once. 
* As you expand globally, inter-Region peering connects AWS Transit Gateways using the AWS global network. 
* Your data is automatically encrypted and never travels over the public internet.


## AWS Managed VPN
* Virtual Private Network (VPN) connection between on-premises sites and AWS
* Uses public internet

## AWS Outposts
* Deploys AWS infra on-premises and connect AWS Services
* Can extend a VPC into the on-premises environment
* Supports services like EC2, EBS, S3, VPC, ECS/EKS, RDS, EMR

## Direct Connect
* Low latency Private connection between on-premise data centre and AWS
* Avoids the public internet
* Consistent network
* Cannot be used to extend VPC like Outposts
* This private connection takes at least one month for completion.

# Application Services
Serverless services include:
* Lambda - Lambda charges are dependent on the amount of time it takes to run the code and the number of requests for your Lambda functions.
* Fargate
* EventBridge
* Step Functions
* SQS
* SNS
* API Gateway
* S3
* DynamoDB

| Service  | What it does | Use case |
| --------  | ------------------- | --------------------- |
| Simple Queue Service | Messaging queue, store and forward pattern      | Building distributed decoupled application | 
| Simple Notification Service| Send notifications | Send email notification when CloudWatch alarm is triggered        | 
| Step Functions | out-of-the-box coordination of AWS service components with visual workflow | Order Processing Workflow |
| Simple Workflow Service | Need to support external processes or specialized execution logic | Human-enabled workflows, AWS recommends Step Functions over SWS |
| Amazon MQ | Message broker service for Apache MQ and RabbitMQ | Need a MQ that support industry standards or migrate queues to AWS |
| EventBridge |a server-less event bus that makes it easier to build event-driven applications at scale using events generated from your applications, integrated Software-as-a-Service (SaaS) applications, and AWS services.|
| API Gateway | a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale | Using API Gateway, you can create RESTful APIs and WebSocket APIs.  API Gateway supports containerized and serverless workloads, as well as web applications.|

TODO: https://aws.amazon.com/serverless/

# Amazon Route 53
* Its AWS Domain Name Service
* Performs 3 main functions:
1. * Domain Registration
1. * Domain Name Service: translates names to IP  addresses
1. * Health Checking: sends automated requests to applications to perform health checks

* Major type of records supported by Route 53
> 1. A  	-	Address records
> 1. AAAA	-	IPv6 Address records
> 1. CNAME	-	Canonical Name records
> 1. Alias	-	Route 53 specific record


## Routing Policies
> 1. Simple -  IP addresses associated with domain name
> 1. Failover - if primary is down, route to secondary
> 1. Geolocation - route based on geographic location of request 
> 1. Geoproximity - route to closet region within geo area
> 1. Latency - use lowest latency route to resources
> 1. Multivalue answer - returns several IP addresses
> 1. Weighted -  relative weights e.g. 80%/20%


# EC2 Auto scaling
* Launches and terminate instances on demand
* Creates collection of EC2 instances called Auto Scaling Groups
* Responds to EC2 status check and CloudWatch metrics
* Can scale based on demand on on a schedule
* Scaling polices determine how to respond to change in demand
* A launch configuration is the template used by Amazon EC2 Auto Scaling to create new EC2 instances and includes parameters such as instance family, instance type, AMI, key pair and security groups

## ASG
* Auto Scaling Group
* ASG has following templates:
> * Launch Template ( AMI, EC2 type, EBS Volume, SG, EC2 user data, SSH Key pair )
> * Min size / Max size / Desired capacity 
> * Network / Subnet info
> * LB info
> * Scaling Policies

## Predictive Scaling Policy
* ML based load forecasting and scale ahead

## Dynamic Scaling Policy
1. **Target tracking** - A metric is selected, CloudWatch alarm in created automatically. Attempts to keep the group at or close to the metric
1. **Simple scaling** - Scaling based on one or more CloudWatch alarm, adjust group size based on a metric
1. **Step scaling** - Scaling based on one or more CloudWatch alarm, adjust group size based on a metric but adjustments vary based on the size of alarm breach
1. **Scheduled scaling** - adjust the group size at a specific time

# Elastic load balancer
* ELB automatically distributes incoming application traffic across multiple targets like Amazon EC2 instances, containers and IP addresses
* Can distribute load of application traffic in a single or multiple AZ
* ELB cannot distribute connections across regions, only availability zones. To direct traffic across regions use Amazon Route 53
* Types of Load balancer - CLB, ALB, NLB, Gateway LB. Details are as follows.

## CLB
* Classic load balancer
* Supports HTTP, HTTPS, TCP
* Fixed hostname - xxx.region.elb.amazonaws.com
* Cross zone LB is enabled using console and is free

## ALB
* Application Load Balancer
* Supports HTTP, HTTPS, WebSockets
* Uses Target Groups to pass traffic
* Uses Routing Table to select Target Groups
* Fixed hostname: xxx.region.elb.amazonaws.com
* Cross-Zone LB is always enabled and free
* The application server dont see IP of client directly
* The true client’s IP is inserted in header `X-Forwarded-For` and port in `X-Forwarded-Port`

### Target Group
* Can contain following:
> * EC2 Instances
> * ECS Tasks 
> * Lambda Functions
> * IP address

### Server Name Indication (SNI)
* It solves the problem of loading multiple SSL Certificates onto one webserver to serve multiple websites
* Works for ALB and NLB but not for CLB

## NLB
* Network load balancer
* Supports TCP, UDP
* Can handle millions of requests per second
* Less latency
* Has one static IP per AZ
* Supports Elastic IP
> NOTE: NLB expose a public static IP whereas CLB and ALB exposes a static DNS 

### Sticky Sessions
* Works for CLB and ALB
* Achieved using a cookie which can either be custom (generated by user) or generated by LB
* Application based cookie generated by LB has name `AWSALBAPP`
* Duration based cookie generated by LB has name `AWSALB ` (ALB) or `AWSELB ` (CLB)


# AWS storage Services
## Elastic Block store (EBS)
* Used by EC2 instances 
* You can add multiple volumes to an instance
* Typically one EBS volume can be mounted to only one instance at a time - possible by EBS multi-attach
* EBS volumes are replicated within an AZ
* EC2 instances must be in the same AZ as the EBS volumes
* EBS volume data persists independently of the life of the instance
* EBS volumes need not to be attached to an instance
* Root EBS volumes are deleted on termination by default
* Extra non-boot volumes are not deleted on termination by default
* EBS Volume Types:
> * gp2 / gp3 - General purpose SSD
> * io1 / io2 - High Performance SSD
> * st1 - Low cost HDD volume for frequently accessed throughput intensive workload
> * sc1 - Low cost HDD volume for less frequent workload
* Only gp2 / gp3 and io1 / io2 can be boot volume


### EBS Snapshots
* Snapshots are taken to capture a point-in-time state of an instance
* Snapshots are stored in S3 and are incremental copies of previous snapshot i.e. Only the delta is updated
* You can create an EBS volume in another AZ from a snapshot
* A snapshot can also be used to create an EBS backed AMI
* Amazon Data Lifecycle Manager (DLM) automates the creation, retention and deletion of EBS snapshots and AMI

### EC2 Instance Store volumes
* Instance Store volumes are physically attached to the host hence are quite fast
* EBS volumes are attached over the network
* Instance Stores are ephemeral - data gets lost when the instances are terminated
* Good for buffer / cache / temp data


## Amazon Elastic File System (EFS)
* Uses NFS (Network File System) protocol
* Can simultaneously connect with thousand of instances
* Only available for Linux instances
* It is a regional service
* EC2 instances can access files on an EFS file system across many Availability Zones, Regions and VPCs
* You can also connect from another VPC using peering 
* You can also connect EFS to on - premise data center using VPN or direct connect
* Expansive ( 3 x gp2 ) , pay per use
* Does not enable encryption by default. 
* EFS supports two forms of encryption for file systems: encryption of _data in transit_ and encryption of _data at rest_. 
* You can enable encryption of data at rest when you create an Amazon EFS file system. 
* You can enable encryption of data in transit when you mount the file system.


> * NOTE: Root volumes are where the operating system is installed and can be either EBS volumes or instance store volumes.
> * EFS volumes cannot be used for the root storage volume but can be mounted to store data.

## Amazon Simple Storage Service (S3)
* _Please refer to next section_

## AWS Storage Gateway
* A hybrid cloud storage service
* Connects your existing on-premises environments with the AWS Cloud
* Gives you on-premises access to virtually unlimited cloud storage
* All data transferred between the gateway and AWS storage is encrypted using SSL (for all three types of gateways - File, Volume and Tape Gateways).

# Amazon Simple Storage Service (S3)
* Object based storage
* Uses HTTP protocol
* A bucket is a container for objects (files)
* Files can be between 0 bytes to 5 TB
* Following URL patterns are used to access buckets
> * http://bucket.s3.region.amazonaws.com
> * http://s3.region.amazonaws.com/bucket
* Since S3 follows URL pattern which is a universal namespace so bucket names must be unique globally
* However buckets are created within a REGION
* You can set your Amazon S3 bucket as the origin of your CloudFront web distribution
* An object consists of:
> * Key (name of objects)
> * Version ID
> * Value (actual data)
> * Metadata
> * Subresources
> * Access Control Information

## S3 - Additional Features
| S3 Capability | What is does |
|--------------|----------------|
| Transfer Acceleration | Speed up data uploads using CloudFront in reverse |
| Requester Pays | The requester rather than the bucket owner pays for requests and data transfer |
| Events | Trigger notification  to SNS, SQS, or Lambda when certain events happens |
| Static Web Hosting | Static website hosting |
| Versioning | Retain object versions. Deleted objects are represented with _Delete Markers_ |
| Replication (requires Versioning in source and destination bucket) | Replicate Objects within AWS Region (SRR) or across AWS Regions (CRR-Cross Region Replication)|
| Lifecycle Rules | Different rules like -  Transition current or previous versions of objects between storage classes, Expire current version of objects, permanently delete previous versions of objects |
 

## S3 Storage Classes
* There are following 6 storage classes in S3
1. Standard -
1. Intelligent Tiering - Moves data among storage classes automatically 
1. Standard-IA - Infrequent Access, retrieval fee
1. One Zone IA - Infrequent Access, only in one AZ, retrieval fee
1. Glacier 
1. Glacier Deep Archive
* The storage class is set at the Object level i.e.  while adding objects into a bucket 
* S3 Glacier enables encryption by default.















