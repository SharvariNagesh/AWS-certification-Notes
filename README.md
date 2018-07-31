# AWS-certification-Notes
AWS Solution Architect Notes

https://github.com/agasthik/aws-csa-2017#ec2--the-backbone-of-aws  - AWS Training Notes from github
https://aws.amazon.com/cli/?sc_channel=PS&sc_campaign=Acquisition_AU&sc_publisher=google&sc_medium=command_line_b&sc_content=aws_cli_p&sc_detail=aws%20cli&sc_category=command_line&sc_segment=211476420629&sc_matchtype=p&sc_Country=AU&s_kwcid=AL!4422!3!211476420629!p!!g!!aws%20cli&ef_id=WpeN4wAAAFs9SjRz:20180702001944:s - CLI reference

https://s3.amazonaws.com/helpshastudyawspolly.com/index.html - This is where I can enter notes for polly integration

https://aws.amazon.com/certification/certified-solutions-architect-associate/ — exam details and white papers to read before taking the exam

Remit2India code: NDT25
AWS Innovation 2018

Security :
* Multi factor authentication
* Don’t use root user account for admin purposes. Crate a separate user for admin
* temporary security credentials - is short term and is better than access keys, which are not rotated for long time. we can use temp
* AWS cloud trail - it monitors activities of AWS CLI, SDKs . 
* Guard duty- monitors for unusual activities. uses ML . no negative consequences.
* AWS System manager - maintains security patches. 
* VPC lets you decide public & private subnets. 
*  Route53
* Cloud front can be used to protect from 
* AWS WAF
* AWS key management services - manages security keys 
* S3 private buckets
* AWS Secret manager - credentials are stored, rotated safely . secure and audit secrets centrally. Oath permissions are also managed
* AWS trusted advisor - helps you save money, close security gap


Amazon Neptune:
* Graph DB
* supports gremlin and SPARQL
* 

AWS Code services:
* code commit
* code build
* third party tooling
* code deploy
* Lambda
* beanstalk

* Code star integrates all the above
* Cloud9 is a IDE prepackaged with lot of SDKs and libraries for many popular languages
* code pipeline - is continuous build and deploy platform
* can use either cloud star or cloud9 interface to develop code
* Cloudformation - to deploy code

Lambda deployments:
* SAM Template are similar to cloud formation formats
* similar to server less deploy
* uses a yaml file to define the resources used in the lambda, permissions, 

* SAM can also be used to simulate a lambda environment. 
* Can be used to test the lambda functions
* Invoke lambda functions locally
* Debug lambda functions for java/python/nodejs
* Very similar to server less testing. ‘sam local invoke ‘ to invoke lambda code locally
* SAM also provides a way to test lambda locally is by calling the lambda with the parameters in a URL
* we can make lambda and API Gateway know each other. and we can assign the percentage of traffic you want the particular lambda function to receive. say 20% of the traffic is diverted to canary deployment. if we are happy, we can test it, verify and then if we are happy, we increase the load to 100%. This is called Canary releases. The changes can be ruled back
* aws.amazon.com/serverless/nuild-a-web-app/
* 

Overview:
* 16 Regions & 44 availability zones - december 2017 and 6 more regions and 17 more AZs for 2018
* Region is a geographical region . each region consists of 2 or more availability zones(AZ). AZ are different data centres in the same region which will not be affected
* Edge Locations are endpoints for AWS which re used for caching content. Typically this consists of CloudFront, Amazo’s content Delivery network(CDN). The are many more Edge Locations than regions. 

1000 feet overview of services:

* compute
   * - EC2 - virtual machines inside AWS. Elastic compute cloud.
  - EC2 container service - This is where Docker containers are run in scale
  - Elastic beanstalk - this is for developers who don’t understand AWS. All that developers have to upload the code
  *- Lambda - 
  - Lightsail -VPS service. Virtual private service. this is for people who doesn’t understand the VPC and other infrastructure
  - Batch - batch computing

* Storage
  -  S3 (Simple Storage Service) - 
  - EFS - Elastic file system.
  - Glacier - Archival system
  - Snowball - to bring large amount of data into AWS. send a disc to a data centre
  -  Storage Gateways - virtual centres.

* DB
  - RDS- relational database service (Mysql, postgres sql)
  - DynamoDB - non SQL
  - Elasticache - is a way of caching commonly used things in database service.
  - redshift - complex queries are run here. built for data warehousing. 

* Migration
   - AWS Migration Hub
  - Application Discovery service. Detects what applications you have, and what are the dependencies for your application
  - Database migration service. - DB migration
  - server migration service - virtual and physical migrations
  - Snowball

* Network and content delivery
  + - VPC- virtual private cloud - virtual data centre. you configure network route tables, firewalls , proxy etc.
  - Cloud Front - video files and other resource files are moved to a location closer to the user so that it can be served from the nearest location
  - Route53 is the AWS DNS service. 
  - API Gateway - 
  - Direct connect - it is running a direct connection from office to AWS centre

*  Developer tools
   - CodeStar - CI tool to continuous delivery system
  -  Code commit - place to store the code, versioning
  - Code Build is a place where code will be built
  - Code deploy - Automates code deployments to EC2 and also can be used for other deployments
  - CodePipeline - CI system. Visualize, 
  - X-Ray - Analyse and debug server less applications
  - Cloud9 - IDE for developing code 

* Management tools
  - CloudWatch - logs, monitoring other services, alerts
*  - CloudFormation - (Solution Architects need it) - way of scripting infrastructure. All firewalls, proxies can be configured from a script
*  - CloudTrail - all the activities on the AWS environment gets logged in cloudTrail. 
 * - Config - monitors the configurations of all the AWS systems. and keeps a snapshot of it. and the configurations can be gone back
  - OpsWorks - automating environments.
  - Service Catalog - Catalog of IT service. used by big companies to keep track their applications, etc governance 
  - Systems Manager - interface for managing resources. Can be used to roll out security patches to 1000 EC2s
 * - Trusted Advisor - Know the difference between Instructor and trusted Advisor. Trusted Advisor gives advice on multiple things like security configurations like if we have kept a port open, if you are not using AWS services enough, how to save money on AWS
  - Managed Services - EC2 and other manages are managed
 - 
* Media services
  - Elastic Transcoder - takes the video and resizes it to make it look good on android, pc etc
 - MediaConvert - good quality media
 - media package - protects video over the internet
 - media store - to store media
  -MediaTailor - add advertisement in the video

Machine learning
 - Sage Maker - deep learning is made easy (Deep machine learning)
 - Comprehend - sentiment analysis
 - DeepLens - aware cameras which. On the camera which can be programmed to recognise people etc
 - Lex
 - Machine learning - Normal machine learning. upload a dataset and it predicts the output.
 - Polly - texts to speech converter.
 - Rekognition - recognises what is there in a video or image. it tells there is a cat in the video
  - Translate - 
  - Transcribe - automatic speech recognise service which can convert a vedeo speech to text


Analytics
  - Athena - design a query to analyse docs ins S#
*  - EMR - (Elastic map reduce)  processing large amount of data. 
  - CloudSearch & ElasticSearch service - both are search service
*  - kinesis - way of injecting large amount of data into AWS. may be FB hashtag
  - Kinesis video streams 
  - QuickSight - business Intelligence tool. 
*  - Data Pipeline. - a way of moving data between different AWS services
  - Glue - fully managed Extract , Transform and Load (ETL) service


Security & Identity & Compliance
 * - IAM - Identity access management
  - cognito - on mobile phone the user can be authenticated using Facebook or other authentication services after that they get access to AWS resources
  - Guard Duty - detection service that continuously monitors for malicious or unauthorized behavior
* - Inspector - is something that is installed on EC2, which generate reports listing the vulnerabilities
 - Marie - scan S3 for personal identifiable data
 - Certificate Manager - managing SSL certificate
* - CloudHSM - hardware security module - dedicated bits of hardware to store keys. can be used to encryption
* - Directory service - Integrating microsoft security service
*  - WAF- web application firewall. Which monitors the application usage by a user and tries to understand if the user is trying to do a sql injection etc 
 - Shield - helps to prevent DDos attacks. If we get DDOS 
 -  Artefact - on demand access to AWS compliance reports. 

Mobile services
  - mobile hub - set up AWS services for a mobile app. mobile SDK
  - pinpoint - push notifications targetted to mobile applications. may be when the user goes near a store, the store information is push notified 
  - AWS App sync - updates data for mobile apps
  - DeviceFarm - Device Farm is an app testing service that lets you test and interact with your Android, iOS, and web apps on many devices at once, or reproduce issues on a device in real time. View video, screenshots, logs, and performance data to pinpoint and fix issues and increase quality before shipping your app.
  - Mobile analytics - for mobile

AR/VR
  -  Sumerian - can build your own room/world
  -  

Application integration
  - Step function - AWS Step Functions makes it easy to coordinate the components of distributed applications as a series of steps in a visual workflow. You can quickly build and run state machines to execute the steps of your application in a reliable and scalable fashion.
  - Amazon MQ - message queue which stores redundant messages in multiple AZ
*  - SNS
*  - SQS - a queuing service which can be fed into EC2 instance
*  - SWF - Work flow service - a job workflow may be something like Amazon post service. 

Customer Engagement
  - Connect - contact centre as a service
*  - Simple Email Service - email service to send large amount of emails
 
Business Productivity:
  - Alexa for business - can be used to dial in , order ink, 
  - Chime - google hangouts or meeting app. 
*  - Work Docs - Drop box for AWS. Safely and security work docs
  - Work Mail - like google mail 


Desktop & App Streaming
   - Workspaces -  VDI solutions. running an actual OS in the cloud and streaming it into your device.
  - App stream 2 - streaming the application into the device. similar to workspaces but for applications. 

IOT:
  - iOT - thousands of devices sending back data may be temperature etc
  - iOT device management
  - Free RTOS - OS for micro controllers. free
  - Green Grass - software local computing , machine learning etc for connected devices. 

Game development
  - GameLift. - a service to develop games. 

* IAM (Identity Access Management)

	⁃	Centralised control of your AWS account
	⁃	Shared Access to your AWS account
	⁃	Granular permissions
	⁃	Identity Federation (including Active Directory, Facebook etc)
	⁃	Multifactor authentication
	⁃	Provide temporary access for users/devices and services where necessary
	⁃	Allows you to set up your ow password rotation policy
	⁃	Integrates with many different AWS services 
	⁃	Supports PCI DSS Compliance

* 4 terms in IAM:
1. Users
2. Groups
3. Roles - 
4. policies - a document that defines one or more permissions

* IAM is always Global. 
* IAM Roles- are a way to grant permissions to entities that you trust
* The “Root account” is simply the account created when first setup your AWS account. It has complete Admin access.
* “power user” is an account which has all AWS access except managing users and groups

* We can set billing alerts and billing limits can be created to send alerts if the cost exceeds the amount set in billing limits.
* IAM also enables you to grant temporary security credentials (temporary access keys and a security token) to any IAM user to enable them to access your AWS services and resources. You can also manage users in your system outside AWS. These are referred to as federated users. Additionally, users can be applications that you create to access your AWS resources.

S3 (Simple Storage Service):

* object storage. so one can’t install OS like in block storage devices like EC2
object based storage is basically files like videos, pdf etc. 
* files can be from 0 bytes to 5 TB. The largest object that can be uploaded in a single PUT is 5 gigabytes. For objects larger than 100 megabytes, customers should consider using the Multipart Upload capability.
* There is unlimited storage
* Files are stored in buckets( folder)
* S3 is universal namespace, that is names must be unique globally. example: https:/s3-au-west-1.amazonaws.com/acludguru <— this is the format of the S3 resource
* when a file is uploaded, server returns 200 OK HTTP code
** read after write consistency for puts
* eventual consistency for overwrite puts(update) and deletes ( can take some time to propagate)
* updates to S3 are atomic. 
* S3 is simple key, value store. version id, metadata, sub resources ( They exist below the object and does not exists on it’s own. e.g.: ACL, torrent)
	If a spread sheet ACL has access set only to finance departments
* S3 - SLA - 99.99 availability and 99.999999999(11 9’s) durability guaranty(data lost). and is designed to sustain the loss of 2 facilities concurrently.
* tiered storage available
* Lifecycle management
* can do encryption in multiple ways.
* secure your data using ACL and bucket policies. Bucket policy applies to a bucket where as ACL can be applied to each file
* By default buckets are private and all objects stored inside them are private
* Types of S3: 
  - S3 Standard (durable , immediately available, frequently accessed
	99.99% availability , 99.99999999999% durability, stored redundantly across multiple devices in multiple facilities and is designed to sustain the loss of 2 facilities concurrently.
  - S3 IA(Infrequently accessed & lower fee than S3), 
	there is a charge  for retrieval
  - S3 One Zone -IA: want a lower-cost option for infrequently accessed data, but do not require the multiple availability zone data resilience. data can be lost if the zone is damaged.
  - RRS( Reduced redundancy storage) 99.99% durability and 99.99%availability of objects over a given ear
  - Glacier - very cheap. archival only. It takes 3-5 hours to restore from Glacier. Has it’s own landing page. $.01$ per GB. 
	+ Expedited - restored within minutes
	+ Standard - restored within 3-5 hours
	+ Bulk - restored within 5-12 hours 
* S3 Charges
    	- storage
	- requests
	- storage management pricing - data tagging.
  	- Data transfer pricing. Data moving from one region to another	- Transfer Acceleration
	   Amazon S3 Transfer Acceleration enables fast, easy and secure transfers of files over long distances between your end users and an S3 bucket. Transfer acceleration takes advantage of Amazon CloudFront’s globally distributed edge locations. As the data arrives at an edge location, data is routed to Amazon S3 over an optimized network path.
* S3 Transfer Acceleration: edge locations are closer to the user. upload speed can be accelerated by using this.
* Read S3 FAQ before sitting for the exam
*  hosting a website using Route 53. S3 can be used to host static websites without any dynamic content like php etc.
* The static website can scale automatically without having to configure a load balancer
* To make a request to an S3 bucket over IPv6, you need to use a dual-stack endpoint. 
* To access S3 bucket using IPV6, one has to use dual-stack end point. The URI for dual stack end point looks like: 
  virtual host style url : bucketname.s3.dualstack.aws-region.amazonaws.com
  path style url: s3.dualstack.aws-region.amazonaws.com/bucketname
* Amazon S3 supports virtual hosted-style and path-style access in all regions
* Virtual Hosting of Buckets :
  In general, virtual hosting is the practice of serving multiple web sites from a single web server. One way to differentiate sites is by using the apparent host name of the request instead of just the path name part of the URI. An ordinary Amazon S3 REST request specifies a bucket by using the first slash-delimited component of the Request-URI path. Alternatively, you can use Amazon S3 virtual hosting to address a bucket in a REST API call by using the HTTP Host header. In practice, Amazon S3 interprets Host as meaning that most buckets are automatically accessible (for limited types of requests) at http://bucketname.s3.amazonaws.com. Furthermore, by naming your bucket after your registered domain name and by making that name a DNS alias for Amazon S3, you can completely customize the URL of your Amazon S3 resources, for example, http://my.bucketname.com/.
   a second benefit of virtual hosting is the ability to publish to the "root directory" of your bucket's virtual server. This ability can be important because many existing applications search for files in this standard location. For example, favicon.ico, robots.txt, crossdomain.xml are all expected to be found at the root.
* Amazon S3 routes any virtual hosted–style requests to the US East (N. Virginia) region by default if you use the US East (N. Virginia) endpoint (s3.amazonaws.com), instead of the region-specific endpoint (for example, s3-eu-west-1.amazonaws.com).
* By default, you can create up to 100 buckets in each of your AWS accounts. If you need more buckets, you can increase your bucket limit by submitting a service limit increase. 
* CORS - cross origin resource sharing - one resource is allowed to access a resource on the other S3 bucket. Eg: a javascript on one S3 can reference an other javascript on some other S3
* Encryption:
   + In Transit;
       SSL/TLS
    + At rest
	- client side encryption
	- server side encryption
	   + with amazon S3 managed keys (SSE-S3  —> Server side encryption-S3)
	   + Server side encryption with KMS (SSE-KMS)
	   + Server side encryption with customer provided keys (SSE-C)

  Versioning:
   - once versioning is enabled, it can’t be disabled. it can only suspend versioning. Each version of the file is stored as a separate individual file. so cost can go up if versioning is enabled. 
   - if a file is deleted, it can be restored by going to   - versions- “Show”. Delete the delete marker and the file is restored. 
   - To delete a version, click on the file, in the pop up window, click on “Latest version” and delete the version we don’t want. We can also restore a file from this same location. we can download the old version of the file we want to restore and upload it back. 
  - If you delete an object, instead of removing it permanently, Amazon S3 inserts a delete marker, which becomes the current object version. You can always restore the previous version. For more information, see Deleting Object Versions.
   - Version control saves the entire files for each versions. So if we are using version control to store different versions of very big files, it can add up to the storage costs for us
   - To delete the entire file go to version-“show” and delete the entire file. 
   - docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html
   - Objects stored in your bucket before you set the versioning state have a version ID of null. When you enable versioning, existing objects in your bucket do not change. What changes is how Amazon S3 handles the objects in future requests. For more information, see Managing Objects in a Versioning-Enabled 
Bucket.
   - another layer of security by configuring a bucket to enable MFA (multi-factor authentication) Delete, which requires additional authentication for either of the following operations.
	•	Change the versioning state of your bucket
	•	Permanently delete an object version
  - Integrates with lifecycle rules
  - Versioning must be enabled on both the source and destination buckets.
  Replication:
https://aws.amazon.com/answers/infrastructure-management/crr-monitor/
    - regions must be unique.
    - versioning must be enabled on both the source and destination
    - when replication is configured and a new bucket is given as the target, versioning has to be enabled. Without versioning, replication doesn’t work. 
    - After enabling versioning, only when a new version of a file is uploaded to parent bucket, it gets replicated in the replication bucket. The existing files does not get copied.
    - Even when a file is deleted, the deleted file marker gets replicated. But when a deleted file marker is deleted or deleting individual versions, it doesnt	get replicated. 

Building a server less webpage with API gateway & Lambda

* When registering the domain name in route53, make sure the same name S3 bucket can be created. Without the matching S3 bucket name, AWS does not let you create a DNS entry

   Lifecycle management:
     - can be used in conjunction with versioning
    - can be applied to current versions and previous versions.
    - following actions can now be done:
       - transition to the standard -IA storage class (minimum - 128Kb and 30 days after the creation date)
       - Archive to the Glacier storage class ( min 30 days after IA, if relevant
      - permanently delete

   CloudFront (CDN):
     - edge location- this is the location where content will be cached This is separate to an AWS region /AZ
    - There might not be a region but an edge location can exist.
    - Origin - This is the origin of all the files that the CDN will distribute. This can be either an S3 Bucket, an EC2 instance, an Elastic load balancer or Route53
    - Distribution - CDN which consists of a collection of Edge locations. two types of distributions:
	 + web distribution -websites
	 + RTMP - used for media streaming
    - edge locations are also for write. Not just for read only
    - you can clear cached objects, but you will be charged
    - objects are cached for the life of TTL(Time to Live). By default it is 86400 seconds. which is one day. So our cloud front caches the data in edge locations for one day by default
    - There can be multiple origins
*   - If you set “Restrict bucket access” then all request must go via cloudfront. direct s3 bucket links can not be used.


   Storage Gateway: https://docs.aws.amazon.com/storagegateway/latest/userguide/WhatIsStorageGateway.html
    - AWS Storage Gateway is a service that connects an on-premises software appliance with cloud-based storage to provide seamless and secure integration between an organisation’s on-premises IT environment and AWS’s storage infrastructure. The service enables you to securely store data to the AWS cloud for scalable and cost-effective storage.
    - AWS Storage Gateways’ software appliance is available for download as a VM(virtual machine) image that you install on a host in the datacenter. 
    - Storage Gateway supports either VMware ESXi or Microsoft Hyper-V. (The hypervisor presents virtual, or guest operating systems to virtual machines andmanages the execution of these virtual operating platforms, which can consist of a variety of operating systems. ... Two of the most common choices for hypervisors include vSphere, a VMware product, and Hyper-V, by Microsoft.)
    - Four types of Storage Gateway
	+ File Gateway - (uses NFS) - flat files. Usually stored in S3. Life cycle management policy can be applied to it. This is directly stored on S3 and no caching locally
	+ Volumes Gateway (iSCSI-Internet Small Computer System Interface)  - block based storage. May be virtual hard disc where VM is running,  OS volume or VM on which mysql is installed. not directly stored in S3. It stores in a EBS volume and then in S3	    -  2 types:
	       - Stored volumes  — entire set of dataset will be stored on premises. Gateway stored volumes is the old name
		- Cached volumes - recently accessed data is stored on premises where as rest of the data is backed up in AWS. Gateway cached volumes
	+ Tape Gateway(VTL) - back up & archiving solution. This allows to create virtual tapes and send it to AWS Glacier and manage it using Lifecycle management. old name- Gateway virtual tape library
    - File Gateway: Files are stored as objects in S3 buckets, accessed through a NFS (Network File system) mount point. 
	+ ownership, permissions and timestamps are durably stored in S3 in the user metadata.
	+ File Gateway can connect to AWS using Direct connect( An AWS service), internet or Amazon VPC (Virtual private cloud)
    - Volume Gateway
	 - It is a block based storage can be used to store OS , Applications. It is a virtual hard disc
	 - data written to these volumes can be asynchronously backed up as point-in-time snapshots of your volumes and stored in the cloud as Amazon EBS snapshots
	 - Snapshots are incremental backups that capture only changed blocks. All snapshot storage is also compressed to minimise your storage changes
	 - Stored volumes let you store your primary data locally, while asynchronously backing up that data to AWS. The application can access the data locally with less latency where as there is a backup safely stored asynchronously in the AWS. 1GB - 16 TB in size for stored volumes
	 - Cached Volumes let you use Amazon Simple Storage Servie (S3) as the primary data storage while retaining frequentlt accessed data locally in your storage gateway. Cached volumes minimise the need to scale your on-premises storage infrastructure, while still providing your applications with low-latency access to the frequently accessed data. . You can create volumes upto 32 TiB in size and attach to them as iSCSI devices from your on-premises application servers. Your gateway stores data that you write to these volumes in Amazon S3 and retains recently read data in your on-premises storage gateway’s cache and upload buffer. 1GB-32TiB for cached volumes.
	 - Tape Gateway - uses Gateway virtual tape library(VTL), used for backup and uses popular backup applications like NetBackup, Backup Exec, Veeam etc. 

	
  Snow Ball:
   - AWS Import/Export disk was the predecessor of this service. AWS accelerates moving large amounts of data into and out of the AWS cloud using portable storage devices. AWS transfers data onto and off of storage devices using amazon’s high-speed internal network and bypassing the internet. But this became a difficult for AWS. So they introduced Snowball. There are 3 types of Snowball:
	+ Snowball
	+ Snowball Edge
	+ Snowmobile
    - Snowball is petabyte-scale data transport solution that uses secure appliances to transfer large amounts of data into and out of AWS. Snow ball addresses common challenges with large scale data transfers including high network costs, long transfer times and security concerns. Transferring data with Snowball is simple, fast, secure and can be as little as one-fifth the cost of high-speed internet. 
    - 80TB snowball in all regions. Snowball uses multiple layers of security designed to protect your data including tamper-resistant enclosures, 256-but encryption, and an industry standard Trusted Platform Module(TPM) designed to ensure both security and full chain of custody of your data. 
    - AWS performs a software eraser
    - Snowball Edge 
	+ is a 100TB data transfer device with on-board storage and compute capabilities. This is a little datacenter which can be brought to your workplace. This can also run lambda functions
    - Snow Mobile : 100 petabytes per snowmobile a 45 foot long ruggedised shipping container
	+ massive safe container on the back of a huge truck.
	+ this is for petabyte or even exabyte levels of data.


S3 Transfer Acceleration:
   - S3 Transfer Acceleration utilises the cloudFront edge network to accelerate your uploads to S3. Instead of uploading directly to your S3 bucket, you can use a distinct URL to upload directly to an edge location which will then transfer that file to S3. you will get a distinct URL to upload to      
 
   e.g acceleration URL.: <bucket name>-S3-accelerate.amazonaws.com

  * AWS calculates which region is fastest

Static website using S3
   * Domain name created using route53 should be same as bucket name
   * only static websites can be created. AWS take care of  load balancing for the website. 
   * The static website end point will be something like : <bucketname>.s3-website-<region>.amazonaws.com




EC2: Elastic Compute Cloud (ECC -> EC2) https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html
   is a web service that provides resizable compute capacity in the cloud. 
  EC2 changes the economics of computing by allowing you to pay only for capacity that you actually use. Amazon EC2 provides developers the tools to build failure resilient applications and isolate themselves from common failure scenarios.
   EC2 options:
	1. on demand: allows you to pay a fixed rate by the hour or by sec with no commitment. 
    	use case:
		a. perfect for users that want the low cost and flexibility of amazon EC2 without any up-front payment of long term commitment
		b. applications with short term, spiky or unpredictable workloads that can not be interrupted.
		c. applications being developed or tested on amazon ec2 for the first time.
	2. Reserved: provides you with a capacity reservation, and offer a significant discount on the hourly charge for an instance. 1 year or 3 year terms
	Use Case:
		a. applications with steady state or predictable usage
		b. apps that require reserved capacity
		c. users can make up-front payments to reduce their total computing costs even further
		   i. standard Reserved  instances (RI) - upto 75% off on -demand)
	  	   ii. convertible RI (upto 54% off on-demand) feature the capability to change the attributes of the RI as long as the exchange results in the creation of reserved instances of equal or greater value.
		   iii. Scheduled RIs are available to launch within the time window you reserve. this option allows you to match your capacity reservation to a predictable recurring schedule that only requires a fraction of a day, a week or a month.
	3. spot: enables you to bid whatever price you want for instance capacity, providing for even greater savings if the applications have flexible start and end times. If amazon terminates , you don’t have to pay anything
		a. applications that have flexible start and end times
		b. applications that are only feasible at very low compute prices
             c. Users with an urgent need for large amounts of additional computing capacity
	4. Dedicated hosts: physical EC2 server dedicated for your use. dedicated hosts can help reduce costs by allowing you to use existing server bound software licenses - oracle license etc
	      a. useful for regulatory requirements that may not support multi tenant virtualization.
  		b. Great for licensing which does not support multi-tenancy or cloud deployments.
		c. can be purchased on demand (hourly)
		d. can be purchased as a reservation for upto 70% off the on-demand price.

   EC2 instance Types:
family
speciality
use case
F1
Field programmable gate array
genomics research, financial analytics, big data
I3
high speed storage
no sql
G3
Graphics intensive
video encoding
H1
high disk throughput
map reduce based workloads, distributed file systems
T2
lowest cost, general purpose
web servers/small dos
D2
Dense storage
file servers, data warehousing
R4
memory optimised

M5
General purpose
application servers
C5
compute optimised
CPU intensive apps
P3
graphics/general purpose
machine learning, bit coin mining etc
X1
memory optimised
apache spark

To remember this: DR MC GIFTPX  new one: FIGHT DR MC PX
D for density
R for RAM
M - main choice for general purpose apps
C- compute
G- Graphics
I for IOPS
F for FPGA
T cheap general purpose
P Graphic and general
X - Extreme memory


EBS:
  * EBS : EBS allows you to create storage volumes and attach them to EC2 instances. once attached, you can create a file system on top of these volumes, run a database etc. 
  * EBS volumes are placed in a specific availability zone, where they are automatically replicated to protect you from the failure of a single component. 
  * EBS is  a virtual disc
  * EBS volume types:
      SSD:
	  - General purpose SSD (GP2)
		  general purpose, balances both price and performance.
		  ratio of 3 IOPS per GB with upto 10,000 IOPS and the ability to burst upto 3000 IOPS for extended periods of time for values at 3334 GiB and above
	 - Provisioned IOPS SSD(IO1)
	    designed for I/O intensive applications such as large relational or no sql db.
	    use if you need more than 10,000 IOPS. upto 20,000 IOPS
      Magnetic
	 - Throughput optimised HDD (ST1)
		biodata, log processing. 
		can not be boot volume
	- Cold HDD(SC1)
		lowest cost storage for infrequently accessed workloads. this also can’t be a boot volume
	- Magnetic (standard)
		lowest cost per GB, used where data is accessed infrequently. . 

* Creating an EC2 instance :
  - AMI - Amazon machine image
  -  Default VPC is created in each region
  - a Subnet will be created for each availability zone
* If ‘Delete on Termination’ is turned on, the root volume will be deleted on termination.
* root storage provided by AWS can not be encrypted. but a third party tool can be used to encrypt the root volume
* Termination protection is turned off by default.

Security Groups:
   * In the security Groups section on the EC2 dashboard, we can set the IP addresses which are allowed to access the EC2 in the source section 
   * if you add an inbound row , automatically, an outbound rule is added . Security groups are stateful
   * all inbound traffic is blocked by default. we can’t add a rule to deny any traffic here
   * All outbound traffic is allowed
   * Changes to security groups take effect immediately
  * multiple security groups can be associated with an EC2 instance. This can be done by going to Actions drop down, networking and security configuration
  * Also, you can have any number of EC2 instances within a security group.
   * you can not block specific IP Addresses using security groups, instead use network access control list

EBS Volumes: 
  * Volume exist on EBs and it is just a virtual hard disk
  * The EC2 instance and it’s EBS volumes will be in the same availability zone
  * EBS volumes can be modified without losing the data. there will be a performance issue. we can change both volume sizes and storage type on the fly.
  * But magnetic standard storage, can not be modified
  * To create an other volume in another availability zone, first create a snapshot. from a snapshot, we can create a volume, image etc. when we create a new volume out of this snapshot, we can create this volume on a different storage type and also we can change the availability zone
	* a snapshot can be copied to any other regions
  * Snapshots are created for backups and images are created for booting a similar system. snapshots exist on S3, thought we can’t see them. 
   * snapshots are incremental.
   * Snapshots of encrypted volumes are encrypted. only unencrypted volumes can be shared with other users, other accounts and made public
   ** Can I delete a snapshot of an EBS Volume that is used as the root device of a registered AMI - answer is no. you must deregister the AMI before being able to delete the root device. http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-snapshot.html
  * EBS vs instance store : 
	* instance store volumes are sometimes called ephemeral storage.
	* Instance store volumes can not be stored if the underlying host fails, you will lose your data.  
	* EBS backed instances can be stopped. you will not lose the data on this instance if it is stopped.
	* you can reboot both, you will not lose your data
	* By default, both ROOT volumes will be deleted on termination. However, with EBS volumes, you can tell AWS to keep the root device volumes. 
       * Instance meta-data : used to get information about an instance (such as public ip)
       	+ curl http://169.254.169.254/latest/meta-data/
       	+ curl http://169.254.169.254/latest/user-data/	

RAID: (Redundant Array of independent disks)
	+RAID 0 is striped, no redundancy, good performance
	+ Raid 1 - mirrored , redundancy
	+ RAID 5 - Good for reads, bad for writes, AWS does not recommend RAID 5s on EBS
	+ RAID 10 - Striped and mirrored, good redundancy, good performance.combination of RAID 1 & 0
  * RAID arrays are used when not getting the disk IO
  * Snapshots of encrypted volumes are encrypted automatically
  * volumes restored from encrypted snapshots are encrypted automatically
  * you can share snapshots but only if they are unencrypted. encryption key is tied to AWS account.
  * Instance store sometimes known as ephemeral storage - can not be stopped. If the volume is installed on an EBS and if the hypervisor is corrupt, it can be stopped and started again, which gets provisioned on a new hypervisor. EBS came after instance store. 
  * To create a snapshot for amazon EBS volumes that serve as root devices, you should stop the instance before taking the snapshot.

Load Balancers: old name for load balancers is ELB(referred to classic load balancer) - elastic load balancers.
   there are 3 types of load balancers
	1. application load balancer - OCI layer 7 load balancer. balances load based on the application
	2. network load balancer - OCI layer 4 load balancer. balances load at the network level
	3. classic load balancer (also called ELB) - legacy elastic load balancer. you can load balance HTTP/HTTPS applications and use layer 7-specific features, such as X-forwarded and tacky sessions
  * Error 504 is displayed when gateway times out.
  * Load balancers forward private IP address to the applications. If you need the public IP Address of the requester, we need to look for X-Forwarded-For header.
  * Load balancers are always referred using a DNS name and not an IP. IP can change so AWS manages it for you.

Cloud Watch:
   Metrics available in cloud watch for EC2: 1. CPU related, 2. network related 3. Disk related. 4. status related
   * Dashboard - We can create our own customised dashboards and add any metrics to be monitored. We can add graphs or numbers and different metrics can be monitored. 
	 + standard monitoring is 5 mins. detailed monitoring is 1 min
   * Alarms - We can create alarms which send an email notifying when particular thresholds are hit.
   * Events - cloud watch events helps you to respond to state changes in  your AWS resource
   * Logs - cloud watch logs helps you to aggregate , monitor and store logs
   8 Cloud watch also accepts logs from outside

Roles & IAM:
   * IS it possible to attach a role to running EC2 instance? - YES
    + Creating roles is secure. No need to install anything locally. 
    + by creating roles like S3 full access and assigning them to EC2 instances, we can access S3 bucket on command line of EC2.
    + We can copy files from S3 buckets to EC2 instance by command line. but we have to make sure to include the —region tag when the S3 bucket is not in the same region as EC2
    + Roles are more secure than storing your access key and secret access key on individual EC2 instances.
    + Roles are easier to manage.
    + Roles can be assigned to an EC2 instance after it has been provisioned using both the command line and the AWS console.
    + Roles are universal - you can use them in any region. (Everything in IAM is universal)


* Boot strap scripting:  While creating EC2 instances, we can add a boot strap script 
   + In step 3, configure instance details, click on “Advanced details” and add a bash script. Ex: We can add a bash script to install Apache, configure files from S3 bucket, and start apache. So that way, a server can be configured when it is being created

* To get meta data of an EC2 instance, logon to the EC2 and run the below curl command:
	curl http://169.254.169.254/latest/meta-data/
		curl http://169.254.169.254/latest/meta-data/public-ipv4 - will fetch the public ip address of the instance

Placement groups: **
   There are two types of placement groups;
    1. clustered placement group
	a grouping of instances within a single availability zone. Placement groups recommended for applications that need low network latency , high network throughput or both
	only certain instances can be launched into a cluster placement group
    2. Spread placement group	
	A spread placement group is a group of instances that are each placed on distinct underlying hardware.spread placement groups are recommended for applications that have a small number of critical instances that should be kept separate from each other.
   
   * A clustered placement group can’t span multiple availability zones
   * A spread placement group can
   * The name you specify for a placement group must be unique within your AWS account
   * Only certain types of instances can be launched in a placement group (compute optimised, GPU, memory optimised, storage optimised)
   * AWS recommend homogeneous instances within placement groups
   * you can’t merge placement groups.
   * you can’t move an existing instance into a placement group. you can create an AMI from your existing instance, and then launch new instance from the AMI into a placement group
	
EFS: Elastic File system:
   * file storage services for EC2. easy to use and simple interface to create and configure file system.
   * EFS storage capacity is elastic . growing and shrinking automatically as you add and remove files. So application has the storage when they need it.
   * Supports NFSv4 (Network File system 4) protocol
   * One pays for what they use. (Unlike EBS - which can not expand, EFS can expand as the storage requirement increases) - 30 cents per Gb. can scale upto petabyte
   * can support multiple NFS connections.
   * Data is stored across multiple AZ within a region
   * EFS is block based storage unlike S3, which is object based. So EFS can be shared among multiple EC2 instances.
   * Read after write consistency like S3.
   * Multiple EC2 instances can connect to same EFS
   * If the security group does not allow inbound and outbound NFS connection, then this does not work.
=====To be continued ===


Lambda: 
  Scaling up vs Scaling out: scaling up - is increasing the resources like machines, memory etc, as happens in Autoscaling. Where as scaling out is increasing the number of instances.
   * Event driven compute service where AWS lambda runs your code in response to events
   * Some triggers are available only on some locations. N.virginia has all the triggers usually
   * If there are 2 users invoking the lambda function, two instances are created
   * Event driven compute service 
   * first 1 million requests are free, and $.021 per next 1million $. billing is 
    * Duration is calculated when the code begins execution and rounded up to nearest 100 ms. The price depends on the amount of memory used.
      $.00001667 for GB-second used.
    * AWS X-ray allows you to debug
    * Know your triggers - 
    * Know the languages supported in Lambda.
   * Know what services are server less - Lambda, API Gateway, S3, dynamoDB etc

   * cloud 9 is a IDE which AWS acquired and integrated with Lambda. that is the editor used in lambda
    * Lambda is a compute service.


* An Elastic IP address is a static IPv4 address designed for dynamic cloud computing. An Elastic IP address is associated with your AWS account. With anElastic IP address, you can mask the failure of an instance or software by rapidly remapping the address to another instance in your account.

Route53:

IPv6 is not supported by the backend yet on AWS. So IPV6 is still not useable. 
  * Route 53 is a global service. just like S3 and IAM
  * Route 53 is called so because the service is on port 53.
  * There is a limit on how many records are supported. the limit is set to 50. but it can be extended by contacting AWS support.
  * IANA(Internet Assigned Numbers 	Authority) controls the top level domain names in a root zone database ,which is a db of all available top level domain names. one can view all top level domain names by visiting: www.iana.org/domains/root/db
   *Domain registrars : All domain names needs to be organised so that there is no duplication. So domain registrars can assign domain names directly under one or more top level domains. These domains register with InterNIC, a service of  ICANN, which enforces uniqueness of the domain names across the internet. each domain name gets registered in a central database called WhoIs Database.
   * Popular registrars - GoDaddy.com, 123-reg.co.uk etc. even amazon has become a registrar now.
SOA Records:
   * SOA record stores information about:
	+ the name of the server that supplied the data for the zone
	+ Administrator for the zone.
	+ the current version of the data file.
	+ the number of seconds a secondary name server should wait  before checking for updates.
	+ the default number of seconds for the time to live (TTL ) file on resource records.

NS Records: NS stands for name server records and are used by top level domain servers to direct traffic to the content DNS served which contains the authoritative DNS records.

A Records : An “A” record is the fundamental type of DNS record and the “A” in A record stands for “Address”. The A record is used by a computer to translate the name of the domain to the IP address.

TTL Record : the length that a DNS record(with the IP address of the destination) is cached on either the resolving server or the users own local pc is equal to “Time to live” (TTL) in seconds

CNAMES : canonical Name can be used to resolve one domain name to another (alias domain name)

Alias records: Very similar to CNAMES, but if a url, does not have “www”(which is called naked domain names or zone apex record) can’t have a CNAME. So those naked domains must either be an A record or an alias.
	* Alias resource record sets can sae you time because Amazon Route 53 automatically recognises changes in the record sets that the alias resource record set refers to. 
	* Alias is used in ELBs. because ELBs do not have ip addresses. They are accessed using domain name.
	* If route53 request is made for CNAME, there will be a charge associated with that, where as for alias there is no fee involved. Given the choice, always choose an alias record over a CNAME.

**MX records : I am not sure what it is. But this question was there in the quiz. https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html
Routing policies:
   	+ Simple :
	   This is the default routing policy. Used when there is only one resource. There is no logic here. 
  	+ Weighted 
  	   Here each region can be given a weight.
	+ Latency
          latency based routing allows you to route based on lowest network latency for your user. To use latency based routing, you create a latency resource record set for the EC2 or ELB resource in each region that hosts the website. When Route53 receives a query for your site, it selects the latency resource record set for the region that gives the user the lowest latency.Route53 then responds with the value associated with that resource record set.
	+ Failover
	    Failover routing policies are used when you want to create an active/passive set up. for example, you may want your primary site to be EU-WEST-2 and you secondary DR site in AP-SOUTHEAST-2. Route53 will monitor the health of your primary site using a health check. If primary fails, route53 passes traffic to the secondary site.
	+ Geolocation
	   routing will be done based on the geologial location of the user.


Databases

* Relational databases supported by AWS are: SQL server, Oracle, MySQL, postgreSQL, Amazon Aurora(Amazon’s own powerful DB), MariaDB
* In non relational databases, the terms used and their equivalent terms in relational db are
	+ Collection —> Table
	+ Document —> Row
	+ Key value pairs —> fields

* Data warehousing: 
	+ Used for business intelligence. tools like Cognos, Jaspersoft, SQL server reporting services, Oracle Hyperion, SAP Netweaver.
	+ Used to pull in very large and complex data sets. Usually used by management to query data such as current performance vs targets etc.
*OLTP vs OLAP : Online transaction processing(OLTP)(RDS) & Online Analytics processing(OLAP)
   +OLTP example: order number 01020
   + OLAP is used in data warehousing. for example: net profit for EMEA & pacific for product A, this pulls in large number of records. e.g.: sums of product sold in EMEA region, sums of products sold in Pacific region, price of each item, profit etc



* DynamoDB is the no SQL DB
* Redshift - OLAP (data warehouse)
* both EC2 and RDS are on different security groups on RDS security group configuration, make sure to allow security group to which EC2 is associated in MySQL(or any db) security group port for EC2 to connect to RDS

** RDS - Back ups, Multi-AZ & Read replicas:
 * There are two types of backups for AWS RDS : automated backups and database snapshots.. 

Automated backup:
* automated backups allow you to recover your database to any point in time within a “retention period”. The retention period can be between one and 35 days Automated backups will take a full daily snapshot and will also store transaction logs through the day. when you do a recovery, AWS will first choose the most recent daily backups and then apply transaction logs relevant to that day. this allows you to do a point in time recovery down to a second, within the retention period.
*  automated backups are enabled by default. the backup data is stored in S3 and you get free storage space equal to the size of your database. So if you have an RDS instance of 10Gb, you will get 10Gb worth of storage.
* Backups are taken within a defined window. During the backup window, storage I/O may be suspended while your data is being backed up and you may experience elevated latency.

Snapshots:
* DB snapshots are done manually. They are stored even after you delete the original RDS instance. Where as automated backups get deleted once RDS instance is deleted

* After restoring, it is a complete different URL. 
* encryption at rest is supported through AWS Key management service (KMS ) service. once your RDS instance is encrypted, the data stored at rest in the underlying storage is encrypted, as are its automated backups, read replicas and snapshots.
* At present, encrypting existing DB instance is not supported.

Multi-AZ :
* multi-AZ allows you to have an exact copy of your production database in another availability zone. AWS handles replication. When data is written to one DB, AWS automatically replicates it in the other AZ. In the event of db maintenance, failure, or AZ failure, Amazon RDS will automatically failover to the standby so that database operations can resume quickly without administrative intervention.
* multi AZ is disaster recovery only. Not for improving performance. For performance improvement, use read replicas.
* DBs supported in multi AZ are: SQL server, Oracle, MySQL server, PostgreSQL, MariaDB. Aurora as well

Read Replica :
* Read replicas allow you to have a read-only copy of your production db. this is achieved by using asynchronous replication from the primary RDS instance to the read replica. read replicas are used for very read-heavy database workloads.
* multi AZ is synchronous where as read replicas are asynchronous.
* Read replica DBs are available for MySQL server, postgreSQL, MariaDB, Aurora
* Read replica’s is for scaling and nor for disaster recovery
* automatic backups turned on in order to deploy a read replica.
* one can have upto 5 read replica copies of any db.
* you can create read replica of read replicas
* each read replica will have its own DNS end point.
* you can have read replicas that have multi-AZ.
* you can create read replicas of multi-AZ source dbs.
* read replicas can be promoted to be their own databases. this breaks the replication.
* you can have read replicas in a different region. need not be tied to same region.

Dynamo DB:
* consistent, single digit milli second latency at any scale.
* fully managed DB which supports both document and key-value data models.
* Stored on SSD storage.
* spread across 3 geographically distinct data centres. so has reliability built in. It has eventual consistent read and strongly consistent read.
Eventual consistency : This is the default. consistency across all copies of data is reached within a second. repeating a read after a short time should return consistent data. this gives the best read performance.
Strong consistency: A strongly consistent read returns a result that reflects all writes that received a successful response prior to the read.
* If you want the write to be immediately available , you should go with strong consistency. If you are ok to wait till the write is propagated to all the regions, you should go with eventual consistency.
* Dynamo DB is priced based on:
	+ provisioned throughput capacity:
	   - Write throughput  $0.0065 per hour for every 10 units
	   - read throughput $0.0065 per hour for every 50 units.
        + Also charges storage costs of $0.25 per Gb per month.
*DynamoDB is cheap for reading but can be expensive for writes.
* If more read operations are required and there is no join operation required, dynamoDB is a good option
* Dynamo DB has push button scaling. where scaling is automatic, which is not possible in RDS.']\

Elasticache: 
Elasticache: it is a web service that 	makes it easy to deploy, operate,and scale an in memory cache in the cloud. The service improves the performance of web applications by allowing them to retrieve information from fast, managed , in-memory caches instead of relying entirely on slow disk based databases.
* Elasticache supports two in memory caching engines:
    1. Memcached
    2. Redis 
* caching improves application performance by storing critical pieces of data in memory for low-latency access. 
* There are 2 types of Elasticache
   + Redis: a popular open-source in-memory key-value store that supports data structures such as sorted sets and lists. ElastiCache supports master/slave replication and multi-AZ which can be used to achieve cross AZ redundancy. Redis supports mutli-AZ redundancy which memcached does not
   + memcached: A widely adopted memory object caching system. ElastiCache is protocol compliant with Memcached, so popular tools that you use today with existing memcached environments will work seamlessly with the service.
* when a particular db is under a lot of stress/load, elasticache  is a good choice if your db is particularly read heavy and not prone to frequent changing.
* Redshift is a good choice if the db is under stress because manGEMENT keep running OLAP transactions on it.

Aurora:
* Aurora runs only on AWS cloud. It is mysql compatible, relational database engine. 
* It combines speed and availability of high-end commercial db with the simplicity and cost-effectiveness of open source db. 
* amazon aurora provides upto five times better performance than mysql at a price point one tenth that of a commercial database while delivering similar performance and availability.
* big challenge to oracle.
* start with 10GB  and scales in 10GB till 64TB
* compute resources can scale up to 32vCPUs and 244GB of memory.
* 2 copies of data is kept in different availability zones with minimum of 3 AZ. totally 6 copies of 
* Aurora can transparently handle write upto 2 copies of loss  and upto 3 copies loss for read operation.
* Aurora storage is self healing. it repairs automatically.
* We can have upto 15 aurora replicas and 5 mysql replicas
* When the primary fails, AWS automatically fails over and uses the replica. It is sufficient to use Cluster URL and no need to use replica URL.

Things to focus:
1. Different RDS storage types and the maximum storage : https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Storage.html#USER_PIOPS
2. Backing up and restoring
3. I/O is suspended when snapshot is taken
4. read about redshift

VPC  (Virtual private cloud):  VPC is a very important topic from the exam point of view. we should be able to set up VPC on our own before going to exam
* Every region has a default VPC
* amazon VPC lets you provision a logically isolated section of the AWS cloud. one can launch AWS resources in a virtual network.
* user has complete control over their virtual network environment including selection of IP address range, submit creations and configuration of route tables and network gateways.
* one can easily customise the network configuration for VPC. For example:
	+ public facing subnet for your web servers that has access to the internet
	+ place databases or application severs in a private facing subnet with no internet access
	+ leverage multiple layers of security, including security groups and network access control lists, to help control access to EC2 instances in each subnet.
	+ can create hardware VPN connection between corporate datacenter and VPC and leverage the AWS cloud as an extension of your corporate datacenter.
* each subnet address sits in a different AZ. 
* CIDR.xyz can be used to see the address range created for the IP Address range.
* security groups can span subnets.
* The internal ip address in a region can range from
	+ 10.0.0.0 - 10.255.255.255 (10/8 prefix)
	+ 172.16.0.0 - 172.31.255.255 (172.16/12 prefix)
	+ 192.168.0.0 - 192.168.255.255 (192.168/16 prefix)
* the soft limit on number of VPCs in a region is 5. but this can be increased by sending a mail to AWS
* 10.0.0.0/28 is the smallest address range you can have with Amazon
* launch instances into a subnet of your choosing
* assign custom IP address ranges in each subnet
* Configure route tables between subnets. route tables tell which subnet can speak to which other subnets
* we can create a internet gateway and attach it to VPC. Remember : each VPC can have only one internet gateway. (There are questions like internet is slow, how to fix it and options are like create one more internet gateway)
* much better security control over your aws resources as network ACL can be created, subnets can be created and route tables also give some security . 
* Instances can be moved to private subnets
what can VPC do:
+ launch instances into a subnet of your choosing
+ Assign custom IP address ranges in each subnet
+ configure route tables between subnets
+Create internet gateway and attach it to our VPC
+ Much better security control over your AWS resources
+ Instance security groups
+ Subnet network access control lists

Default VPC vs Custom VPC:
* Default VPC is user friendly, allowing you to immediately deploy instances. 
* All subnets in default VPC have a route out to the internet. 
* Each EC2 instance has both public and private IP address. Where as in private VPC, we can configure it to face only to private network

VPC peering: A VPC peering connection is a network connection between two VPCs that enables you to route traffic between them using ipv4 or ipv6 addresses
* instances behave as if they were on the same private network
* you can peer VPC’s with other AWS accounts as well as with other VPCs in the same account.
* Peering is in a star configuration: i.e. 1 central VPC peers with 4 others. No transitive peering, meaning, if vac a is peering with vpc b & c, then vpcA can access resources in both B&C but B&C can’t access each others resources

Exam tips :
* VPC consists of IGW(virtual private gateways), route tables, network access control lists, subnets and security groups
* 1 subnet = 1 availability zone
* security groups are stageful; network access control lists are stateless. Meaning, if port 80 is opened on security group, both inbound and outbound traffic can pass through. where as in network ACL , both has to be separately opened up

* We can create a VPC in a default tenancy or dedicated tenancy. Dedicated tenancy will get very expensive.
* When VPC is created, by default a route table, network ACL and a security groups are created. but subnet or internet gateways are not created.
* the AZ name displayed in one account could be named differently in some other account. AWS randomises the AZ because, everybody selects the first AZ in the drop down. And if not randomised, only one AZ gets overloaded.
* If subnet mask is created as /24, instead of 256, AWS gives only 215 IP addresses. The reason for that is, 5 ip addresses are reserved. first 3 are reserved for n/w address, DNS , VPC router. and last two are reserved for future use, and one fore broadcast
* When subnets are created, the router will have a default rule to allow both the subnets to talk to each other and add the subnets to the router list. This can dangerous if the router has an internet connection. All subnets created will automatically will be added to default router and it have internet access. So it is better to create a second router to connect to internet . 
* the router with internet connection should have 0.0.0.0/0 set as destination
* ::/0 will give internet access to IPv6.
* We  have to select the subnet for which ip access is required
* VPCs by default will not have assign ipv4 address disabled. we have to manually enable it.
* Security groups exists only inside VPCs

NAT instances and NAT Gateways:
* NAT instance is EC2 instance from the community AMIs. This NAT instances should be added to the subnet with internet access. add this instance to the security group which has HTTP and HTTPS access enabled. 
*  we don’t have to login to NAT instance at all. but one thing that we need to change is: go to Actions-> Networking -> source and destination Check disable
   * Each EC2 instance does source and destination checks by default. This means that the instance must be the source or destination of any traffic it sends or receives. But a NAT instance should be able to send and receive data when it is not the source or destination. So source & destination check should be disabled. This should be done only on NAT instance and not on NAT gateway
* Then create a route from default route table to NAT instance.
* Problem with NAT instance is all internet connection from private servers depends on one small NAT server with is a single server in single AZ. So it might put lot of load on NAT instance or if NAT instance dies, the internet connection to all the 

* NAT gateways is an option inside VPC. NAT gateway works on IPV4. There is one more service called Egress only Internet gateway. This works with IPv6
* Place the NAT Gateway in the public subnet and add a route from NAT gateway to any ip address
* Comparison of NAT Gateway & NAT instance.: https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-comparison.html
* NAT Gateways is not a single server but a cluster of instances provided by AWS. we don’t have to worry about NAT gateway patching or managing the server. AWS takes care of it.

Exam tips:
* When creating NAT instances, disable source/destination check on the instance.
* NAT instance must be in a public subnet.
* There must be a route out from private instances to NAT instance for it to connect to internet.
* The amount of traffic a NAT instance can support depends on the instance size. If you are bottlenecking, increase the NAT instance size.
* you can create high availability using autoscaling groups, multiple subnets in different AZs, and script to automate failover.
* Behind a gateway
* It is phasing out but still needed for the exams

NAT Gateway:
* Preferred by businesses
* scale automatically upto 45Gbps
* no need to patch
* not associated with security group.
* automatically assigned a public  IP address
* remember to update your route tables.
* no need to disable source/destination check
* more secure than NAT instance. No SSH connection to the instance, and AWS patches this

Network access list vs Security list :
REF: https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html
* A subnet can be associated with only one network ACL but a NCL can be associated with multiple subnets.
* similarly one network ACL can span only one VPC. 
* When a private network ACL is created, by default everything is denied.
* Amazon recommends rule no in NCL to start with 100. 100 for IPV4 and 101 for IPv6
* NCL is stateless and even if inbound traffic is allowed, outbound traffic will still be denied until manually enabled.
* Ephemeral port - traffic is sent back through an ephemeral port, which is a random port in a range configured. Ref: https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html#VPC_ACLs_Ephemeral_Ports
* The default network ACL is configured to allow all traffic to flow in and out of the subnets to which it is associated. Each network ACL also includes a rule whose rule number is an asterisk. This rule ensures that if a packet doesn't match any of the other numbered rules, it's denied. You can't modify or remove this rule.
* An ephemeral port is a short-lived endpoint that is created by the operating system when a program requests any available user port. The operating system selects theport number from a predefined range, typically between 1024 and 65535, and releases the port after the related TCP connection terminates.
* NCL rules are always read in the order of Rule#. If a deny rule is put after allow all rule, it will not be respected.
* VPC automatically comes with a default network ACL, and by default it allows all inbound and outbound traffic.
* You can create custom network ACLs. By default, each custom network ACL denies all inbound and outbound traffic until you add rules.
* Each subnet in your VPC must be associated with a network ACL. If you don’t explicitly associate a subnet with a network ACL, the subnet is automatically associated with the default network ACL.
* Network ACLs contain a numbered list of rules that is evaluated in order, starting with the lowest numbered rule.
* Network Acs are stateless where as security groups are stateful
* block ip addresses using network ACLs not security groups

* Load balancers: 9 out of 10 times you should chose application load balancers. Network load balancers are used when ultra high performance is required or when static IP addresses are required.
* When creating a load balancer inside a VPC, make sure the EC2 instances are in atleast 2 separate AZ and they must be internet facing.

VPC Flow logs:
 This is a feature used to capture IP traffic flowing through the VPC. Flow log VPC is stored using cloud watch.
* VPC logs can be captured at 3 different levels:
	+ VPC logs
	+ Subnet
	+ N/w interface level
* We need to create a log group in cloud watch before directing the glow logs to cloud watch.
* We can direct these flow logs to lambda so that we can take action if certain kind of logs are flowing

Not all IP Traffic is monitored in flow logs :
* traffic generated by instances when they contact the Amazon DNS, except when our own DNS server is used
* traffic generated by windows instances for license activation
* traffic from 169.254.169.254 for instance metadata.
* DHCP traffic
* traffic to the reserved IP addresses for the default VPC router 
* Can not enable logs for the VPCs that peered unless peered VPC is in your account
* you can not tag a flow log
* after you have created a flow log, you can’t change it’s configuration or change it’s IAM role 


NAT vs Bastion:
Bastion is used to connect to computers in the private network for security
* A Nat is used to provide internet traffic to EC2 instances in private subnets
* A Bastion is used to securely administer EC2 instances (using SSH or RDP) in private subnets. In Australia it’s called Jump boxes

* Using a VPC End point, we can give access to EC2instances in my private subnet to access other resources within the AWS. For example S3 bucket.
* When VPC end points are created, we don’t need a NAT gateway to connect to S3. NAT Gateway is going via the internet.


SQS : 
* SQS is pull based system where as SNS is push based system.
* SQS has a invisibility timer. If the application has not processed it, the message reappears and a new application server picks it up after the invisible timer expires. This results in message being delivered more than once. 
* default invisible timer is 30 seconds and maximum it can take is 12 hours.
*  SQS acts as a buffer between the producing and processing the data. Queue resolves the issues that arise if the producer is producing work faster than the processor can process or if producer or consumer is connected to internet intermittently to the network.
*  We can configure autoscaling processors to monitor SQS queues. If the number of messages increase beyond a threshold, new processes can be spawned.
* There are 2 types of queues:
  + Standard Queue:
  + FIFO Queue :
* Messages are 254kb size.
* messages can be kept in queue from 1 minute to 14 days.
* Default retention period is 4 days
* SQS guarantees that message is processes at least once.
* there are 2 types of Polling. short polling and long polling.
* Short polling returns imm
* SQS is a distributed message queuing system


* Standard queue: Standard queue. by default the queue type is standard. 
* It lets you have nearly unlimited number of transactions per second
* Standard queue guarantees that a message is delivered atleast once. however In some cases some messages might get delivered more than once in out of order.
* Standard queue provides best effort ordering, which ensure messages are generally delivered in the same order as they are sent.


FIFO: The order in which messages are sent and received is strictly FIFO and exactly once processing.
* strictly FIFO. message delivered once, no duplicates. suited for banking applications.
* messages are delivered once and remain available until a consumer processes and deletes it.
* duplicates are not introduced into the queue
* Also supports FIFO groups that allow multiple ordered message groups within a single queue. 
* FIFO queues are limited to 300 transactions per second but have all standard queue features.

Long polling:
* SQS long polling is a way to retrieve messages from your Amazon SQS queues.
* while short polling returns immediately (even if the queue is empty), long polling doesn’t return until a message is received in the queue or the poll times out.
* Long polling can save you money.

Short polling: they return immediately even if there are no messages in the queue.

* Better to read FAQ before going into the exam

Elastic Transcoder:
Media transcoder in the cloud. Convert media files from their original source format in to different formats that will play on smartphones, tables, pcs etc.
* Provides transcoding presets for popular output formats, which means that you don’t need to guess about which settings work best on particular devices.
* pay based on the minutes that you transcode and the resolution at which you transcode.

API Gateway:

* API Caching : it caches endpoint’s response. With caching, you can reduce the number of calls made to your endpoint and also improve the latency. API Gateway caches the response for a specified time-to-live( TTL), in seconds.
* Low cost and efficient
* scales effortlessly
* throttle requests to prevent attacks
* connect to cloud watch to log all requests

Same Origin Policy & Cross-origin Resource Sharing (CORS)
* Same origin is an important concept in the web application security. model under the policy, a web browser permits scripts contained in a first webpage to access data in a second webpage, but only if both webpages have the same origin.
* CORS is a mechanism that allows restricted resources (E.g fonts) on a web page to be requested from another domain outside the domain from which the first resource was served.
* Usual errors on AWS: “Origin policy can not be read at the remote rescue?” — for this error enable CORS on api gateway
* If you are using javascript/AJAX that uses mute domains with API gateway, ensure that you have enabled CORS on API Gateway.

Kinesis :

* Kinesis is a platform on AWS to send your streaming data to. Kinesis makes it easy to load and analyse streaming data and also providing the ability for you to build your own custom applications for your business needs.
* There are 3 core kinesis services
1. Kinesis Streams
2. Kinesis Firehose
3. Kinesis Analytics
* Kinesis Streams  receive data from a variety of devices like EC2, laptop, mobile and stores them in a device called “Shard”s. by default it stores the data for 24 hours but can be increased it to 24 hours. then EC2 instances pick up the data, process it and store it in a variety of devices. e.g.: The data could be social media data and analysed for sentiments ; stock market data analysed for share prices etc
* Shards supports 5 transactions per second for reads, upto a ma total data read rate of 2MB per second and upto 1,000 records per second for writes upto a max total data write rate of 1MB per second. The data capacity of your stream is a function of the number of shards that you specify for the stream. The total capacity of the stream is the sum of the capacities of it’s shards

* kinesis Firehose : no shards or streams. It is completely automated. Lambda . but it is optional to use data analysis. once analysed data can be stored in S3. Firehose doesn’t store data. As soon as the data is received it is processed either using lambda and stored in S3. 

* Kinesis Analytics : J=Kinesis Analytics runs a SQL query on the data in both kinesis streams and firehose and the query is stored in S3/Redshift/elasticsearch cluster


SWF (Simple Workflow Service)
* It is web service that makes it is easy to coordinate work across distributed application components. 
* it enables applications for a range of use cases : media processing, web application backends, business process workflows , analytics pipelining etc
* It is designed as coordinated tasks
* Tasks represent invocation of various processing steps in an application , which can be performed by executable steps.
* Workers: these are programs that interact with SWF to get tasks, process received tasks, and return the results
* Decider: Is a program that controls the coordination of the tasks.
* Workers & deciders can run in AWS cloud, may be in an EC2 instance. 
* SWF brokers the interaction between deciders and workers. It allows the decider to get consistent views into progressing tasks and to initiate new tasks in an ongoing manner.
* At the same time SWF stores the tasks, assigns them to workers when they are ready, and monitors their progress. It ensures a work is assigned only once and never duplicated.
* SWF maintains the application states and workers and deciders need not have to keep track of states. they can scale quickly
* SWF Actors:
   + Workflow started. an application that starts the workflow. could be ecommerce website
   + deciders - control the flow of activity task  in a workflow execution. if something has finished or failed, decider decides what to do next.
   + activity workers - carry out the activity tasks- may be humans
* Domain in SWF referee to : A collection of related workflows

SQS vs SWF:
* SWF is assigned only once  and never duplicates where as SQS can duplicate and assigned twice . Users have to manage the duplicate messages and ensure a message is processed only once.
* SQS is a message oriented API where as SWF is a task oriented API
* SWF keeps track of all the tasks & event in the application . where as SQS user has to implement application level tracking especially if multiple queues are used.	
* SQS has a retention period of 14 days, SWF upto 1 year for work flow executions.

SNS (Simple Notification Service):
* It can push notifications mobile, deliver notifications by sms text or email, to SQS queues, to any HTTP endpoint.
* SNS notification can also trigger lambda functions.When a message is published, it can trigger a lambda with the message in the payload
* Messages are stored across multiple AZ to make sure the message is not lost.
Benefits:
* Instantaneous , push based , no polling
* SNS subscribers - HTTP , HTTPS, Email, Email-JASON, SQS, application, lambda

SNS Vs SQS:
* both messaging services in AWS
* SNS - push based, SQS- pull based (polled)
* 

CloudFormation:

ARCHITECTING FOR CLOUD:
Businness benefits of cloud:
* Almost zero upfront infrastructure investment
* just-in-time infrastructure
* more efficient resource utilisation
* usage-based costing
* reduced time to market

Technical benefits:
* automation - scriptable infrastructure
* Autoscaling
* Proactive scaling
* more efficient development lifecycle
* imposed testability
* disaster recovery and business continuity 
* Overflow the traffic to the cloud (if traditional infrastructure overflows, move it to cloud using private load balancer)

Design For failure:
Rule of thumb:
* be a pessimist when designing architecture in the cloud, assume things will fall. and design disaster recovery.
* decouple your components. the key is to build components that do not have tight dependencies. if one application fails, other comonents should not have dependency on this particular instance and should be able to handle
* implement elasticity: there are three types of scaling required:
  1. proactive cyclic scaling: if we know the server is going to be busy during month end, be proactive in scaling
  2. proactive event based scaling: any special event is coming up
  3. Autoscaling: based on demand. 
* Secure your application:
	1. enable ssh , https


Intro to the architected framework:

link: https://aws.amazon.com/architecture/well-architected/
* There are 5 pillars for well architected framework
* security
* reliability 
* performance efficiency
* cost optimisation
* operational excellence

* General design principles
	+ stop guessing your capacity needs
	+ test system at production scale
	+ automate to make architectural experimentation easier
	+ Allow for evolutionary architectures
	+ Data-Driven architecture
	+ improve through game days - simulating production special days. 
	+ 

Pillar 1 - Security Pillar:
* Apply security at all layers including patches
* enable traceability
* automate responses to security events - 
* Focus on securing your system. - as a customer is responsible for securing data, os, machines
* Automate security best practices - harden an operating system and use the hardened image to deploy new EC2 instances.
*** Shared responsibility Model : (IMP) 
   both AWS and customer is responsible for security:
   customer is responsible for :
   * customer data, platform, applications, identify & access management
   * operating system, network & Firewall configuration 
   * Client side data encryption & Data integrity authentication, server-side encryption, network traffic protection
   AWS is responsible for :
   * Compute, storage, Database, networking
   * regions, AZs, Edge location
* security in the cloud consists of 4 areas:
  + data protection
  + privilege management
  + infrastructure protection
  + Detective controls
1. Data protection - best practices:
   before architecting, security practices across your environment, basic data classification should be in place. one should organise and classify data as publicly available, available to only members of the organisation, available to only certain members of the organisation etc. 
   - implement a least privilege access system so that people access what they need.
  - most importantly one should encrypt where possible, whether it be at rest or transit. (HTTPS, encrypt data when stored)
* AWS customers maintain full control over data
* AWS makes it easier to encrypt keys , include regular key rotation, 
* Detailed logging
 * AWS has designed storage systems for exceptional resiliency, As an example, amazon simple storage service is designed for 11 nines of durability.
* Versioning on S3 can protect against accidental overwrite
* AWS never initiates the movement of data between regions. Content placed in a region will remain in the region unless customer explicitly enable a feature 

Ask yourself :
* how are you protecting your data at rest and transit?

2. Privilege management :
* this ensures that only authorised and authenticated users are able to access resources only in the manner intended. This can be done by: 
  - ACLS
  - Role based access controls
  - password management
Questions: 
 * How are you protecting access to and use the AWS root account credentials?
 * how are you defining roles and responsibilities of system users to control human access to the AWS management console & APIs?
 * How are you limiting automated access (such as for applications, scripts or third party tools or services) to AWS resources?
* How are you managing keys and credentials

3. Infrastructure protection :
  CC Tv, physical access control etc
Questions :
  * how are you enforcing network and host-level boundary protection. Are you using private EC2 or public, etc
  * how are you enforcing AWS service level protection?
  * How are you protecting the integrity of the os on EC2, antivirus installed?

4. Detective controls:
   * you can use detective controls to detect or identify a security breach. AWS services to achieve this include:
  + CloudTrail
   + Amazon Cloudwatch
   + AWS Config
   + Amazon S3
   + Amazon Glacier
  Questions:
   * How are you capturing and analysing AWS logs?	
   * 

Pillar 2- Reliability :

The reliability pillar cover :
   1. the ability of a system to recover from service or infrastructure outages/disruptions 
    2. ability to dynamically acquire computing resources to meet demand.

Design principles:
 * test recovery procedures e.g.: netflix has developed semien army to push net
 * automatically recover from failure - sophisticated tools . monitoring systems for key performance indicators. if the performance decreases, using automated tools to increase the performance, may be auto scaling
 * scale horizontally to increase aggregate system availability - replacing one big system with many small machines so that even if one fails, there are other services to take over. Scaling out rather than scaling up
 * stop guessing capacity - problem in case on on premises resources.

* reliability in the cloud consist of 3 areas:
  - foundations
  - change management
  - failure management
  * Foundations: AWS provides foundations but do put service limits on users to make sure they don’t accidentally provision more than the service limit. to increase the service limit, need to send a mail to AWS
  
*Question:
  - how are you managing AWS service limits for your AWS accounts?
  - how are you planning your network topology on AWS?
  - Do you have an escalation path to deal with technical issues?

Change management:
* One should be aware of changes and proactive management is required.
* Monitoring for the changes is important
* AWS makes these things lot easier, you can use cloud watch to monitor environment and services like autoscaling to automate change response 

Questions:
 * How does your system adapt to changes in demand?
 * How are you monitoring AWS resources?
 * How are you executing change management?

Failure Management:
  * with cloud you should always architect your system with the assumptions that failure will occur. 
  * you should become aware of failures, how they occurred, how to respond to them and then plan on how to prevent them from happening again.

Questions:
  * How are you backing up your data?
  * How does your system withstand component failures?
  * How are you planning for recovery?


Key services match Reliability key pillar:
  Foundations - IAM , VPC
  Change Management - AWS Cloudtrail
  Failure Management - AWS Cloudformation (RDS, multi AZ configurations)


Pillar 3 - Performance Efficiency pillar:
* This pillar focuses on how to use computing resources efficiently to meet your requirements and how to maintain that efficiency as demand changes and technology evolves.
* When AWS releases new services, one should ask ‘Am I building the solution on the right services?’

Design principle:
* Democratise advanced technologies - AWS is democratising services. Unlike earlier days, now we don’t need a noSQL DBA. Anybody can use Dynamodb by reading the manual. Similarly machine learning, we don’t need an expert in machine learning expert
* Go global in minutes - cloud formation can be deploy the same architecture in multiple regions/zones. which will help reducing the latency in different regions
* User server less architecture - 
* Experiment more often - 

Definition:
performance efficiency in the cloud consists of 4 areas :
  - Compute
  - Storage
  - Database
  - Space-time trade-off

Compute : use right server. Some are CPU heavy and some memory heavy. Lambda can be a very efficient and save lot of money

Questions :
 * how to select the appropriate instance type for your system?
 * How do you ensure that you continue to have the most appropriate instance type as new instance types and features are introduced?
 * How do you monitor your instances post launch to ensure they are performing as expected?
 * How do you ensure that the quantity of your instances matches demand?

Storage: 
   optimal storage solutions for your environment depends on a number of factors. For example:
  - Access method - block, file or object
  - Patterns of Access - Random or sequential 
  - Throughput Required
  - Frequency of Access - online, offline or Archival
  - Frequency of Update - Worm, Dynamic
  - Availability Constraints
  - Durability Constraints

* At AWS Storage is virtualised. 
* With S3 you can have 11x9’s durability, cross region replication etc. 
* With EBS you can choose between different storage mediums(such as SSD, Magnetic, PIOPS etc)
* you can also easily move volumes between the different types of storage mediums.

Questions:
* how do you select the appropriate storage solution for your system?
* how do you ensure that you continue to have the most appropriate storage solution as new storage solutions and features are launched?
* How do you monitor your storage solution to ensure it is performing as expected?
* how do you ensure that the capacity and throughput of your storage solutions matches demand?

Database:
* The optimal database solution depends on a number of factors. Do you need database consistency, do you need high availability, do you need No-SQL, do you need DR etc
* With AWS you get lot of options - RDS(mysql, aurora..), DynamoDB,redshift etc
Questions:
* how do you select the appropriate database solution ?
* how do you ensure that you continue to have the most appropriate db solution and features as new db solutions are launched?
* how do you monitor your db to ensure performance is as expected?
* how do you ensure the capacity and throughput of your db matches demand?


Space-Time trade-off:
* when you are building out your infrastructure there is a trade off where space(memory/storage) is used to reduce processing time(compute time) or time is used to reduce space. you can also cache data to reduce time (CloudFront or Elasticache)
* RDS can provide read replicas, which will reduce load on db and lowers latency
* you can use Direct Connect to provide predictable latency between HQ and AWS
* you can use global infrastructure to have multiple copies of your environment, in regions that is closest to your customer base.
* caching see vices such as elastic ache or cloud front reduces latency.
Questions:
* how do you select the appropriate proximity and caching solution
 for your system
* how do you ensure that you continue to have the most appropriate proximity and caching solution as new services are launched?
* how do you monitor your proximity and caching solutions to ensure performance is as expected?
* how do you ensure that the proximity and caching solutions you have matches demand?
* what services are we talking about: 
	+ Compute - Autoscaling
  	+ Storage - EBS, S3, Glacier
	+ Database - RDS, DynamoDB, Redshift
	+ space-time trade -off  - cloud front, elastic ache, direct connect, RDS read replicas etc


Pillar 4 - Cost optimisation pillar:
* use it to reduce costs to a minimum and use those savings for other parts of your business. A cost-optimised system allows you to pay the lowest possible price while still achieving business objectives.

Design principles :
* transparently attribute expenditure
* use managed services to reduce cost of ownership
* trade capital expense for operating expense
* Benefit from economies of scale
* Stop spending money on data centre operations
* 
Definition:
cost optimisation int he cloud consists of 4 areas:
  1. matched supply and demand
  2. cost-effective resources
  3 expenditure awareness
  4. optimising over time

1. matched supply and demand:
* don’t over/under provision, instead as demand grows, so should your supply of compute resources. 
* autoscaling which can scale with demand.
* lambda execute only when a demand comes in.
* Services such as cloud watch can also help you keep track as to what your demand is.
Questions:
*  how do you make sure your capacity matches but does not substantially exceed what you need?
* how are you optimising your usage of AWS services?

2. Cost effective resources:
* Using the correct instance type can be key to cost savings. for example, you might have a reporting process that is running on a t2-micro and it takes 7 hours to complete. That same process could be run on m4.2xlarge in a manner of minutes. The result remains the sam but the t2.micro is more expensive because it ran for longer.
* A well architected system will use the most cost efficient resources to reach the end business goal.
Questions:
* Have you selected the appropriate resource types to meet your cost targets?
* have you selected the appropriate pricing model to meet your cost targets?
* are there managed services(higher level services than EC2, EBS, S3) that can increase your ROI?


Expenditure awareness:
* If multiple teams are incurring costs on different AWS accounts, being aware of what each team is spending is crucial. 
* Cost allocation tags can help track this, billing alerts & consolidated billing can help too
Questions:
* what access controls and procedures do you have in place to govern AWS costs?
* how are you monitoring usage and spending?
* how do you decommission resources that you no longer need or stop resources that are temporary not needed?
* how do you consider data-transfer charges when designing your architecture?


Optimising over time:
* AWS keeps changing FAST. They add hundreds of new services every year. So what was a good architecture might not be very effective without using the latest services. 
* to keep track of changes made to AWS constantly re-evaluate your existing architecture . you can do this by subscribing to AWS blog and by using services such as Trusted Advisor
Questions:
how do you manage and adapt to new services

Key AWS services in this category:
  - matched supply and demand - Autoscaling
  - cost-effective resources - EC2, AWS Trusted Advisor
  - Expenditure awareness - Cloud watch alarms, SNS
  - optimising over time - AWS blog, AWS Trusted advisor


Pillar 5 - Operational Excellence :

* includes operational practices and procedures used to manage production workloads.
* This includes how planned changes are executed and responses to unexpected operational events.
* Change execution and responses should be automated. All processes and procedures of operational excellence should be documented, tested and regularly reviewed

Design principle:
* perform operations with code. Automating the changes
* align operations processes to business objectives. we should collect metrics only which will help business objectives. 
* make regular small, incremental changes
* Test for responses to unexpected events - simian army tools, kios monekey, kiss snake.
* Learn from operational events and failures. Should catch errors
* keep operations procedures current. docs should be uptodate

Definition:
There are 3 best practice areas for operational excellence in the cloud :
1. preparation
2. operation
3. response

1. Preparation:
* Effective preparation is required to drive operational excellence
* operations checklists will ensure that workloads are ready for production operation and prevent unintentional production promotion without effective preparation.
* workloads should have :
  - Runbacks - operations guidance that operations team can refer to while performing daily tasks
  - Playbooks - guidance for responding to unexpected operational events. playbook should include response plans, as well as escalation paths and stakeholder notifications.
* Best practices
  - In AWS there are several methods, services and features that can be used to support operational readiness and ability to prepare for normal day-to-day operations as well as unexpected operational events.
  - Cloud formation can be used to ensure that environments contain all required resources when deployed in production, and that the configuration of the environment is based on tested best practices, which reduces the opportunity for human error.
  - Auto scaling will allow workloads to automatically respond in case of operational needs
  - AWS Config with the AWS config rules feature create mechanisms to automatically track and respond to changes workloads and environments
  - tagging makes sure all resources in a workload can be easily identified during operations and responses.
Questions:
  * what best practices for cloud operations are you using?
  * how are you doing configuration management for your workloads?

* documentation should not become stale as procedures change and should be thorough
* documentation is not complete without application designs, environment configurations, resource configurations, response plans and mitigation plans. 
* If documentation is not updated and tested regularly, it will not be useful when required.
* if workloads are not reviewed before production, operations will be affected when undetected issues occur. If resources are not documented, when operational events occur, determining how to respond will be more difficult while the correct resrouces are identified.

2. Operations:
* operations should be standardised and manageable on a routine basis.
* Focus should be on automation, small frequent changes, regular quality assurance testing and defined mechanisms to track, audit, roll back and review changes
* changes should not be large and infrequent. they should not require scheduled downtime and they should not require manual election.
* logs and metrics on key operational indicators for a workload should be collected and reviewed to ensure continuous operations
* AWS can setup CI & CD (source code repository, build systems, deployment and testing automation.
* release management processes should be tested and based on incremental changes and tracked versions.
* should be able to revert changes that introduce operational issues without causing operational impact.

Questions:
* how are you evolving your workload while minimising the impact of change?
* how do you monitor your workload to ensure it is operating as expected?


*  automate as much as possible. 
* release should be small and roll back plan should be in place
* impact of failure should be planned
* alerts should be timely
* responses should follow pre-defined playbooks
* escalation process and procedures should be in place
* heirarchical escalation should be automated and escalated priority should result in stakeholder notifications.
* AWS has several mechanisms to ensure alerting and notifications - Cloudwatch
Questions
* how do you respond to unplanned operational events?
* how is escalation managed when responding to unplanned operational events?

3. Preparation :
key AWS services
  - preparation - AWS Config provides inventory of AWS resources and configuration and continuously records configuration changes 
  - service catalog helps to create standardised set of service offerings that are aligned to best practices.
  - designing workloads that use automation with services like autoscaling, SQS are good methods to ensure continuous operation
  - code commit, code deploy and code pipeline can be used to manage and automate code changes to AWS workloads
  - Use AWS SDKs to automate operational changes
  - CloudTrail to adit environment changes

3. Response:




