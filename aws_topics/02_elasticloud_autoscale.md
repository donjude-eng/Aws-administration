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