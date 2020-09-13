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