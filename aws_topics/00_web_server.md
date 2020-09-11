# Web servers
* Web servers are computers which delivers the requested web pages. Every web server has an Ip address and the domain name.

# NGINIX
* A web server which reduces the page load time.
 1. An open software
 2. Web server for reverse proxying. caching and load balacing
 3. Provides HTTP server capabilities.
 4. Designed fo maximum performance and stability.
 5. functions as a proxy server for email
 6. Uses a Non-threded and event drive architecture.

## Nginix Configuration
* Nginix are configured in the nginix config file.
* Core settting are in nginix conf file.
* Important contents of nginix config file :
  1. worker_processes - Defined the number of worker process nginix is used.
   * Nginix is a single threaded the number will be equal to the number of cpu cores.

  2. worker_connection
    * It is the maximum number of simultanuos connections in each worker.

  3. access_log&error_log
   * Used for debugging and troubleshooting.

  4. gzip
   * Compression of nginix response.

# Nginix installation
  * sudo yum install nginx
  * sudo install ufw enable -- To enable the firewall
  * nginx - v ( To check the nginix version

## nginix port open only at port 80.
* Port 80 HTTP shares the unencrypted traffic. nginix opens only in port 80 ehich is unencrypted traffic.
* Port 443 provides the encrypted traffic which is 443

# Commands
* sudo ufw enable
* sudo ufw status
* sudo ufw allow ssh
* sudo ufw app list
* sudo apt-get install nginx
* sudo ufw allow 'Nginx Full'
* sudo ufw allow 'Nginx HTTP'
* sudo ufw allow 'Nginx HTTPS'* sudo systemctl status nginx
# Add user to my console.
* sudo adduser ar
* sudo deluser ar
* cat /etc/os-release --- to know the ubuntu version
* sudo passwd 
* sudo cp -r /home/don/Downloads/. /var/www* sudo vi /etc/hosts
