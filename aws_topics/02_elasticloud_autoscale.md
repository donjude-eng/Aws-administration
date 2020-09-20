# Scalabiltiy & High Availability
* Scalability means that an application / system can handle greater loads by adapting.
* There are two kinds of scalability:
   1. Vertical scalability
   2. Horizontal Scalability ( = elasticity)
* Scalability is linked but different to High Availability

# High availability
* High availability usually goes hand in hand with horizontal scaling
* High avilablity mans running your application /system in at least 2 Availability Zones

# Scalabilty foe EC2;
* Vertical Scaling : Increase instance size (Scale up /scale down)
   1. From: t2.nano - 0.5G of RAM, 1 cpu
   2. To : u-12tbl.metal - 12.3 TB of RAM. 448 vCPUs

* Horizontal Scaling : Increase number of instances (scale out / in)
   1. Austo Scaling Group
   2. Load Balancer
   3. High availabilty

* Scalability means abilty to accomandate a lorger load by making the hardware stronger( scale up), or by adding nodes (sacle out)

# Load balancing:
* Load balancers are servers taht are forwarded internet traffic to multiple servers(EC instance) downstream.

### Elastic load balancer
* An ELB is managed load balancer.
* There are three kind of load balancers offered by AWS;
    1. Application load balanncer (HTTP / HTTPS)
    2. Network load balancer (allows TCP, ultra high performane)
    3. Classic Load Balancer (slowly retiring)

* We can use this command to make a dummmy webserver.
```
#!/bin/bash
# Use this for your user data (script from top to bottom)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
```
# Cost of aws EC2 instance

> AMIs that are eligible for the AWS Free Tier are marked in the Amazon EC2 Launch Wizard as Free tier eligible. The AWS Free Tier allotment for Linux and Microsoft Windows instances is counted separately. You can run 750 hours of a Linux t3.micro, t2.micro, or t1.micro instance plus 750 hours of a Windows t3.micro, t2.micro, or t1.micro instance each month for the first 12 months.


# How to create ASG
> Go to `Auto scaling group` in the aws console >> Create a new ASG >> Put a Name for the AsG group >> Create a template for the mentioned group >> Update the details in the the fields >> And now the tmplate is ready

> Go got autoscaling configurations >> Add the name >> Update the loadbalacing configuration details >>