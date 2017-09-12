# AWS Solutions Architect Certification

* AWS Concepts 
* AWS Essentials
* AWS Solutions Architect
* Linux Essentials

**Certified Solutions Architect (CSA) Domains:**
1. Design highly available, cost-efficient, fault-tolerant, scalable systems
2. Implementation / Deployment
3. Data Security
4. Troubleshooting


******************************************************************************
## AWS Concepts

### INTRODUCTION

**High Availability** – files in the cloud are available from anywhere
**Fault Tolerant** – having multiple backups for file in case of system fault

**Enterprise Use of Cloud:**
1. Put servers (storage) off-site in cloud
2. Scaling upwards is easier because you only use servers in cloud that you need
3. Don’t have to estimate future server needs

**Scalability** – ability to quickly/easily add more servers
**Elasticity** – ability to shrink on-demand as needed


### UNDERSTANDING VPCs

**Virtual Private Cloud:**
1. Your private section of AWS
2. Can allow/restrict access to your VPC
3. Can put EC2 and RDS on your VPC


### UNDERSTANDING EC2

**Elastic Cloud Compute (EC2):**
1. Virtual server computer
2. EC2 acts as a web server for Netflix
3. Common use – Web Hosting, encoding, transcoding
4. Good for any type of processing activity
Instance – many times an EC2 computer is referred to as an “EC2 Instance”

### UNDERSTANDING RDS

**Relational Database Service (RDS):**
1. Place to store customer account info, inventory catalog
2. As user traffic increases, demands on DB increase therefore additional EC2 Instances are created


### UNDERSTANDING S3

**Simple Storage Service (S3):**
1. Unlimited storage bucket for files, photos, documents
2. Mass storage container, long-term storage
3. As user traffic increases, demands on DB increase therefore additional EC2 Instances are created


### AWS Global Infrastructure (Physical Setup)

**Multiple Regions**
1. Each region has “availability zones”, which are geographically separated, physical data centers
2. As user traffic increases, demands on DB increase therefore additional EC2 Instances are created


******************************************************************************
## AWS Essentials

### PROJECT OMEGA
https://www.lucidchart.com/documents/view/703f6119-4838-4bbb-bc7e-be2fb75e89e5/0

## IAM (IDENTITY & ACCESS MGMT)
1. manage users and their access to AWS accounts and services
2. Root user – user created when AWS account is created

**AWS Best Practices:**
1. When new AWS account is created, complete task listed in IAM under “Security Status”
2. MFA (Multi-Factor Authentication) should always be set on your “root” account
3. NEVER use your root account for day-to-day use

## VPC (VIRTUAL PRIVATE CLOUD)

**VPC Basics**
1. By default, a VPC is made for you when you create an AWS account.
2. VPC is conceptually similar to a home network
	a. Home Network: Internet -> Modem -> Router/Switch -> Firewall -> Devices
	b. VPC: Internet -> Internet Gateway -> Route Table -> NACL -? EC2 Instances

**Internet Gateways (IGW)**

continue VPC here ........


-------
## S3 - SIMPLE STORAGE SERVICE

##### S3 BASICS
1. Online, storage service accessible from almost any device  
2. Can store any type of file  
3. Buckets are root folders  
4. Folders are subfolders  
5. Select region to store data in that region  
6. **Best Practice**: select region closest to you reduct transfer latency or create bucket in region closest to customers  
7. Charged by CG of storage and number of requests (PUT, GET, POST ..)  

##### S3 BUCKETS AND FOLDERS
1. Bucket name must be unique across all AWS  
2. 3-63 characters, lowercase, numbers, hyphens  
3. Cannot be an IP address  
4. Import objects (files) and create folders in the bucket  
5. Bucket have the most properties
6. Cannot set permissions on folders, but buckets and objects yet  

##### S3 STORAGE CLASSES
1. Object classification in S3  
2. Classes = Standard, RRS (Reduced Redundancy Storage), S3-IA (Infreq Access), Glacier  
3. Vary by cost, availablity, durability, access freq.  
4. STANDARD:  
  a. all-purporse storage  
  b. default option  
  c. most expensive, most durable (99.999999999%) and available (99.99%)  
5. RRS:  
  a. non-critical, reproducible objects  
  b. 99.99% object durability and availability  
  c. less expensive than Standard  
6. S3-IA:  
  a. for infrequent access, but needed immediatedly  
  b. Durability = 99.999999999%  
  c. Availablity = 99.90%  
  d. less expensive than Standard & RRS  
7. GLACIER:  
  a. long-term archival storage  
  b. takes several hours to retrieve  
  c. Durablity = 99.999999999%  
  d. very low cost  

##### S3 OBJECT LIFECYCLES
1. Rules that automate migration of object's storage class to a different class  
2. Change classes based on future usage  
  a. Update Lifecyle to match every day object (file) usage > weekly file usage > annual usage  
3. Optimizes cost  

##### S3 PERMISSIONS  
1. Bucket Level Permissions  
  a. List  
  b. Upload / Delete  
  c. View permissions  
  d. Edit permissions  
2. Object Level Permissions  
  a. Open / Download  
  b. View permissions  
  c. Edit permissions  

##### S3 VERSIONING  
1. Tracks all old/new versions of an object  
2. Once turned on you can only "suspend" versioning  
3. Suspended versioning prevents future versioning  
  a. All previous verisons retained  
4. Set up on the Bucket Level
-------

## EC2 - ELASTIC CLOUD COMPUTE

##### EC2 BASICS
1. Scalable computing capacity  
2. Can use one or many virtual servers  

3. Types of Instances  
	1. On-Demand:  
		* most expensive and flexible  
		* charged when running (by hour)  
  b. Reserved:  
    i. purchase for 1-3 years  
    ii. pay entire price upfront or later  
  c. Spot:  
    i. bid on instance type  
    ii. pay when spot price is equal or below bid price  
    iii. instance terminates when spot price > bid price  

continue ............

------

## LAMBDA

##### LAMBDA BASICS
1. Serverless computing  
2. Pay for requests, duration of use, accessing data from other AWS resources  
3. Create Lambda Function  
```
$ aws lambda create-function \
--region us-west-2 \
--function-name helloworld \
--zip-file fileb://file-path/helloworld.zip \
--role role-arn \
--handler helloworld.handler \
--runtime nodejs6.10 \
--profile adminuser 
```

continue ............

-------

## DYNAMO_DB & RDS

##### DATABASE BASICS
1. AWS offers RDS for SQL databases and DynamoDB for NoSQL databases  
2. RDS  
  a. Types:  
    i.   Amazon Aurora  
    ii.  MySQL  
    iii. MariaDB  
    iv.  PostgreSQL  
    v.   Oracle  
    vi.  Microsoft SQLServer  
  b. Data stored in tables (columns & rows)  
  c. Structured data, such as contact lists  
3. DynamoDB
  a. Types:  
    i.   Mongo  
    ii.  Cassandra  
    iii. Oracle NoSQL  
  b. Good for mobile, web, gaming, adtech, IoT  
  c. Stored in JSON-like, name-value documents  
  d. Unstructured data such as cataloging documents  


continue ............

-------

### CLOUDWATCH

**Service that allows you to monitor AWS resources & metrics:**
1. Can monitor EC2, S3, Billing
2. Use dashboard to view metrics
3. Can set thresholds and alarms on metrics
4. Charged based per dashboard, ec2 monitoring, custom metrics, api requests, logs, custom events






















