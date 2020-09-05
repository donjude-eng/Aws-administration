# Cloud Computing

## Types of cloud computing
* Infrastrucure as a service(IaaS)
* Provide building blocks for cloud IT
* Provides networking, computers, data storage space
* Highest level of flexibility
* Easy parallel with traditional on-premises IT
* Platform as a service(PaaS)
* Removes the need for your organization to manage the underlying   infrastructure
* Focus on the deployment and management of your applications
* Software as a service(SaaS)
* Completed product that is run and managed by the service provider

## Aws history
* launched in 2002
* Aws has 216 points of presensse (205 Edge Locations & || Regional caches) in 84 cities across 42 Countries.

 ![aws_topics](regionscope.PNG?raw=true "Title")

## AWS Regions
1. AWS has regions all around the world
2. Names can be us-east-l, eu-west-3...
3. A region is a cluster of data centers
4. Most AWS services are region-scoped

# IAM Roles and services
* Some AWS service will need to perform action on our behalf
* To do so, we will assign permissions to AWS services with IAM roles
* EC instance is just like a virtual server.
* Commom roles
 1. EC instance roles
 2. Lambda function roles
 3. Roles for CloudFormation

## IAM security Tools
* IAM Credentails report(account-level)
  1. A report that lists all you account's users and the status of their various credentails

# IAM Access Advisor(user-level)
  1. Access advisor shows the service permissions granted to a user and when those services were last accessed
  2. You can use this information to revise your policies.

# IAM Gudiliness & Best practice
  * Don't use the root account except for AWS account setup
  * One physical user = One aws user
  * Assign users to groups and assign permission to user
  * MFA is must
  * use access key fpor pragramatic acces
  * Never share IAm key and acces key

## Responsibily of IAM user
  * Users, groups, roles , policies managament and monitoring
  * MFA for all accounts
  * Don't share the access key or IAM user id

# Amazon EC2
* EC2 is the most popular of AWS offering
* EC2 = Elastic Compute C;oud = Infrastructure as a service
* it mainly consists in the capability of :
   1. Renting virtual machines(EC2)
   2. Stroing data on virtual drives.
   3. Distributing load across machines (ELB)
   4. Scaling the services using an auto-scaling group(ASG)
* Knowing EC is fundamental to understand how the cloud works.

# EC2 sizing & configuration option
  1. Operating system (OS): Linux and windows
  2. How much compute powers & cores (CPU)
  3. How much random-access memory(RAM)
  4. how much storage space:
     1. Network-attached (EBS & EFS)
     2. hardware (EC2 instance store)
  5. Network card:Speed of the card, Public IP address
  6. Firewall rules: security group

# EC2 samples
* ![Linux Directories](ec2samples.PNG?raw=true "Title")

# Hands-On EC2->
* We'll be launching a virtual server using aws console.
* We'll get a high level approach to the parameters
* We'll see te web server launched using EC
 user data
* Start stop terminate the instance.

# Launching EC2 instance ->
* Go to > EC2 intsance > Choose AMI > Choose Instance type > Configure instance >

# Security Groups
 * Security Groups are actibg as a "firewall" on EC2 Instances
 * They regulate:
   1. Access to ports.
   2. Autorised IP ranges - IPV4 and IPV6
   3. Control of inbound network (from other to the instances)
   4. Control of outbound network (from the instance to other)

* If we remove the http from security group the browser will loads for long and return to an error.

## SSH
* SSH port 22 rule is must for the host.
* Add in in inbound rule

## EC2 Instances purchasing options
* On-Demand instances: short workload, predictable pricing.
* Reserved instances --Long workload
* Spot instances : Short workload, cheap, Can lose instances.
* Dedicated Hosts
* ![Linux Directories](reservedinstance.PNG?raw=true "Title")

