# AWS Solutions Architect Certification  

UDEMY COURSES TO TAKE:
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

# AWS CONCEPTS (UDEMY)  

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

# AWS ESSENTIALS (UDEMY)  

### PROJECT OMEGA  
https://www.lucidchart.com/documents/view/703f6119-4838-4bbb-bc7e-be2fb75e89e5/0  

******************************************************************************

## IAM (IDENTITY & ACCESS MGMT)  
1. manage users and their access to AWS accounts and services  
2. Root user – user created when AWS account is created  

**AWS Best Practices:**  
1. When new AWS account is created, complete task listed in IAM under “Security Status”  
2. MFA (Multi-Factor Authentication) should always be set on your “root” account  
3. NEVER use your root account for day-to-day use  

******************************************************************************

## VPC (VIRTUAL PRIVATE CLOUD)  

**VPC Basics**  
1. By default, a VPC is made for you when you create an AWS account.  
2. VPC is conceptually similar to a home network  
	1. Home Network: Internet -> Modem -> Router/Switch -> Firewall -> Devices  
	2. VPC: Internet -> Internet Gateway -> Route Table -> NACL -? EC2 Instances  

**Internet Gateways (IGW)**  

continue VPC here ........

******************************************************************************

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
	1. all-purporse storage  
	2. default option  
	3. most expensive, most durable (99.999999999%) and available (99.99%)  
5. RRS:  
	1. non-critical, reproducible objects  
	2. 99.99% object durability and availability  
	3. less expensive than Standard  
6. S3-IA:  
	1. for infrequent access, but needed immediatedly  
	2. Durability = 99.999999999%  
	3. Availablity = 99.90%  
	4. less expensive than Standard & RRS  
7. GLACIER:  
	1. long-term archival storage  
	2. takes several hours to retrieve  
	3. Durablity = 99.999999999%  
	4. very low cost  

##### S3 OBJECT LIFECYCLES
1. Rules that automate migration of object's storage class to a different class  
2. Change classes based on future usage  
	1. Update Lifecyle to match every day object (file) usage > weekly file usage > annual usage  
3. Optimizes cost  

##### S3 PERMISSIONS  
1. Bucket Level Permissions  
	1. List  
	2. Upload / Delete  
	3. View permissions  
	4. Edit permissions  
2. Object Level Permissions  
	1. Open / Download  
	2. View permissions  
	3. Edit permissions  

##### S3 VERSIONING  
1. Tracks all old/new versions of an object  
2. Once turned on you can only "suspend" versioning  
3. Suspended versioning prevents future versioning  
	1. All previous verisons retained  
4. Set up on the Bucket Level
******************************************************************************

## EC2 - ELASTIC CLOUD COMPUTE

##### EC2 BASICS
1. Scalable computing capacity  
2. Can use one or many virtual servers  
3. Types of Instances  
	1. On-Demand:  
		* most expensive and flexible  
		* charged when running (by hour)  
	2. Reserved:  
		* purchase for 1-3 years  
		* pay entire price upfront or later  
	3. Spot:  
		* bid on instance type  
		* pay when spot price is equal or below bid price  
		* instance terminates when spot price > bid price  

continue ............

------

## LAMBDA  

##### LAMBDA BASICS  
1. Serverless computing  
2. Pay for requests, duration of use, accessing data from other AWS resources  
3. Use when you want to set up front-end serverless websites  
4. Create Lambda Function  
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

******************************************************************************

## DYNAMO_DB & RDS  

##### DATABASE BASICS  
1. AWS offers RDS for SQL databases and DynamoDB for NoSQL databases  
2. RDS  
	1. Types:  
		* Amazon Aurora  
		* MySQL  
		* MariaDB  
		* PostgreSQL  
		* Oracle  
		* Microsoft SQLServer  
	2. Data stored in tables (columns & rows)  
	3. Structured data, such as contact lists  
	4. Pay based on RDS you choose, RDS instance, On-Demand/Reserved, DB storage, Data transfer  
3. DynamoDB
	1. Types:  
		* Mongo  
		* Cassandra  
		* Oracle NoSQL  
	2. Good for mobile, web, gaming, adtech, IoT  
	3. Stored in JSON-like, name-value documents  
	4. Unstructured data such as cataloging documents  
	5. Pay based on capacity, DynamoDB streams, Reserved capacity, DB storage, Data transfer  


continue ............  

******************************************************************************


## REDSHIFT  

1. Internet Hosting service and database warehouse product  
2. Used to query large amounts of big data from S3  
3. Query from S3 cluster and SQL client that are in the same region  
4. Cost = $5 / TB scanned  
5. Integrates with popular BI tools  
6. Setup  
	1. Load cluster  
	2. Connect favorite query tool  

continue ............  

******************************************************************************

### CLOUDWATCH  

**Service that allows you to monitor AWS resources & metrics:**  
1. Can monitor EC2, S3, Billing  
	1. EC2:  
		* CPU utilization  
		* Status checks  
		* Disk read/writes  
	2. S3:  
		* Number of objects (files)  
		* Bucket size  
2. Use dashboard to view metrics  
3. Can set thresholds and alarms on metrics  
	1. View alarm in Cloudwatch  
	2. Alarm can trigger SNS message  
4. Charged based per dashboard, ec2 monitoring, custom metrics, api requests, logs, custom events






















