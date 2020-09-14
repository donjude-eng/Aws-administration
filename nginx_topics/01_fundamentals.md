* Connect to ec2 instance through ssh
* install nginx in the machine
  1. Command is "sudo apt install nginx"

* To get the nginx resources in the system command
  1. ps aux | grep nginx

* Nginx status ->
* service nginx status
* systemctl status nginx

* Download the nginx mainline versioin for nginx.org website.
* Extract the tar file using the command tar -zxvf
* apt get install build-essentials to run the source code

## Custom configuration command
* sudo ./configure --sbin-path=/usr/bin/nginx --conf-path=/etc/nginx/nginx.conf --error-log-path=/var/log/nginx/error.log --http-log-path=/var/log/nginx/access.log --with-pcre --pid-path=/var/run/nginx.pid --with-http_ssl_module

## Configuration

* Transfer files from local machine to ec2 instance
* scp -i C:\Users\DON\aws_course\aws_pem\ECTutorial.pem -r C:\Users\DON\aws_course\aws_pem\demo\demo-site ubuntu@13.233.129.142:~/data/


# Installing nginx configuration

* Access your terminal.
```
Download the NGINX signing key:

$ sudo wget http://nginx.org/keys/nginx_signing.key
Add the key:

$ sudo apt-key add nginx_signing.key
Change directory to /etc/apt.

$ cd /etc/apt
Edit the sources.list file, appending this text at the end:

deb http://nginx.org/packages/ubuntu xenial nginx
deb-src http://nginx.org/packages/ubuntu xenial nginx
Update the NGINX software:

$ sudo apt-get update
Install NGINX:

$ sudo apt-get install nginx
Type Y when prompted.

Start NGINX:

$ sudo service nginx start
Continue to Opening Your Web Page.
```