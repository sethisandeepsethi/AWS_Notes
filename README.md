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
* **Amazon Transcribe** - Add speech (including recorded) to text capabilities to application
* **Amazon Translate** - Neural machine translation service that can localize some content like websites
* **Amazon Textract** - Automatically extract printed text, handwriting and data from any document like PDFs, images, forms, table etc
* **Amazon SageMaker** - Helps data scientists and developers to prepare, build, train and deploy high quality ML models
* **Amazon Comprehend** - A natural-language processing (NLP) service that uses ML to comprehend information from  unstructured data like detecting customer sentiment
* **Amazon Lex** -  A conversational AI for chatbots that can be used to build conversion interface into any application using voice and text
* **Amazon Devops Guru** - Cloud operations service for improving application operational performance and availability. 

# AWS PRICING
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

//To Do - formatting 

https://aws.amazon.com/premiumsupport/plans/

## Consolidated Billing
* Feature of AWS Organizations
* One bill for multiple accounts under an organization
* No extra fee for consolidated billing
* Combine the usage across all accounts to share volume pricing & Reserved instance discount

## AWS Pricing & Billing Tools
### AWS Pricing Calculator
* To estimate cost of your aws architecture solution
* Site: calculator.aws

### AWS Budgets
* Set custom usage and reservation budgets
* Configure alerts when you exceed or forecast to exceed some set thresholds

### AWS Cost Explorer
* Free tool to view chart of your costs
* View cost data of past 13 months and forecast for the next 3 months
* Can  be used to discover patterns of spending for various AWS resources and services

### AWS Cost & Usage report
* Publish AWS billing report to an Amazon S3 bucket	
* Report breaks down cost by - hour, day, month, product, resource, tag
* Can update report upto 3 times a day
* Uses AWS CUR API

### AWS Price List API
* Query the prices of AWS service
* Has 2 components; 
1. Price List Service API (aka Query API) - query with JSON
1. AWS Price List API (aka Bulk API) - query with HTML
* Alerts sent by SNS when prices change - can be used to build custom tool when prices of AWS change

//TODO

***


# DNS, ELB & Auto Scaling
## Amazon Route 53
* Its AWS Domain Name Service
* Performs 3 main functions:
1. * Domain Registration
1. * Domain Name Service: translates names to IP  addresses
1. * Health Checking: sends automated requests to applications to perform health checks

**Routing Policies**
* Simple -  IP addresses associated with domain name
* Failover - if primary is down, route to secondary
* Geolocation - route based on geographic location of request 
* Geoproximity - route to closet region within geo area
* Latency - use lowest latency route to resources
* Multivalue answer - returns several IP addresses
* Weighted -  relative weights e.g. 80%/20%


## Ec2 Auto scaling
* Launches and terminate instances on demand
* Creates collection of ec2 instances called Auto scaling grove L asg)
* Responds to ec2 status check and Cloud watch metrics
* Can scale based on demand on on a schedule
* Scaling polices date mine how to respond to changer in demand

### Scaling policies
1. **Target tracking** - attempts to keep the grout at or close to the metric
1. **Simple scaling** - adjust grout size based on a metric
1. **Step scaling** - adjust group size bared on a metric but adjustments vary based on the size of alarm breach
1. **Scheduled scaling** - adjust the group size at a specific time

## Elastic load balancer
* ELB automatically distributes incoming application traffic across multiple targets like Amazon EC2 instances, containers and IP addresses
* Can distribute load of application traffic in a single or multiple AZ

### Types of Load balancer
1. Application load balancer - layer 7 lb routes connections based on the content of request like domain name or path in the URL
1. Network load balancer - layer 4 lb routes connections based on IP protocol data
1. Classic load balancer
1. Gateway load balancer



