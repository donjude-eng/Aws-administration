- Connect to ec2 instance through ssh
- install nginx in the machine

  1. Command is "sudo apt install nginx"

- To get the nginx resources in the system command

  1. ps aux | grep nginx

- Nginx status ->
- service nginx status
- systemctl status nginx

- Download the nginx mainline versioin for nginx.org website.
- Extract the tar file using the command tar -zxvf
- apt get install build-essentials to run the source code

## Custom configuration command

- sudo ./configure --sbin-path=/usr/bin/nginx --conf-path=/etc/nginx/nginx.conf --error-log-path=/var/log/nginx/error.log --http-log-path=/var/log/nginx/access.log --with-pcre --pid-path=/var/run/nginx.pid --with-http_ssl_module

## Configuration

- Transfer files from local machine to ec2 instance
- scp -i C:\Users\DON\aws_course\aws_pem\ECTutorial.pem -r C:\Users\DON\aws_course\aws_pem\demo\demo-site ubuntu@13.233.129.142:~/data/

# Installing nginx configuration

- Access your terminal.

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

- The way nginx and its modules work is determined in the configuration file. By default, the configuration file is named nginx.conf and placed in the directory /usr/local/nginx/conf, /etc/nginx, or /usr/local/etc/nginx.

# Reference to static web hosting in nginx server

- https://medium.com/@jasonrigden/how-to-host-a-static-website-with-nginx-8b2dd0c5b301

# Rewrite and return command in nginx

```
events {
}

http {

  include mime.types;

  server {

    listen 80;
    server_name 13.233.129.142;

    root /sites/demo/data/demo-site;

    rewrite ^/user/(\w+) /greet/$1 last;
    rewrite ^/greet/john /thumb.png;

    location /greet {

      return 200 "Hello User";
    }

    location = /greet/john {
      return 200 "Hello John";
    }
  }
}
```

- The example for buffer and timeout in nginx

```
user www-data;

worker_processes auto;

events {
  worker_connections 1024;
}

http {

  include mime.types;

  # Buffer size for POST submissions
  client_body_buffer_size 10K;
  client_max_body_size 8m;

  # Buffer size for Headers
  client_header_buffer_size 1k;

  # Max time to receive client headers/body
  client_body_timeout 12;
  client_header_timeout 12;

  # Max time to keep a connection open for
  keepalive_timeout 15;

  # Max time for the client accept/receive a response
  send_timeout 10;

  # Skip buffering for static files
  sendfile on;

  # Optimise sendfile packets
  tcp_nopush on;

  server {

    listen 80;
    server_name 167.99.93.26;

    root /sites/demo;

    index index.php index.html;

    location / {
      try_files $uri $uri/ =404;
    }

    location ~\.php$ {
      # Pass php requests to the php-fpm service (fastcgi)
      include fastcgi.conf;
      fastcgi_pass unix:/run/php/php7.1-fpm.sock;
    }

  }
}
```

- To text the nginx server in the reverse proxy by using a very simple php server

```
ubuntu@ip-172-31-39-80:~$ php -S localhost:9999
PHP 7.0.33-0ubuntu0.16.04.15 Development Server started at Wed Sep 16 19:58:18 2020
Listening on http://localhost:9999
Document root is /home/ubuntu
Press Ctrl-C to quit.
^Cubuntu@ip-172-31-39-80:~$
ubuntu@ip-172-31-39-80:~$
ubuntu@ip-172-31-39-80:~$ touch rep.txt
ubuntu@ip-172-31-39-80:~$ cat rep.txt
ubuntu@ip-172-31-39-80:~$ sudo nano rep.txt
ubuntu@ip-172-31-39-80:~$ ubuntu@ip-172-31-39-80:~$
ubuntu@ip-172-31-39-80:~$ cat rep.txt
Hello from php server
ubuntu@ip-172-31-39-80:~$
ubuntu@ip-172-31-39-80:~$ php -S localhost:9999 rep.txt
PHP 7.0.33-0ubuntu0.16.04.15 Development Server started at Wed Sep 16 20:03:51 2020
Listening on http://localhost:9999
Document root is /home/ubuntu
Press Ctrl-C to quit.
```


# Reverse proxy nginx
```
events {}

http {
        server {

         listen 8888;

         location / {

         return 200 " Hello from NGINX\n";
        }
          location /php {
            proxy_pass 'http://localhost:9998/';
   }
         location /nginxorg {
            proxy_pass 'http://nginx.org/';
   }

 }
}
```

### Let's encrypt is relatively new provider-
* The first step to using Let’s Encrypt to obtain an SSL certificate is to install the Certbot software on your server.

* First, add the repository.
 ```sudo add-apt-repository ppa:certbot/certbot```

* You’ll need to press ENTER to accept. Then, update the package list to pick up the new repository’s package information.

```sudo apt-get update```
* And finally, install Certbot’s Nginx package with apt-get.

```sudo apt-get install python-certbot-nginx```

* In nginx there will be one master process and two worker process

* Here are a few examples of chmod usage with numbers (try these out on your system).

* First create some empty files:

1. user@host:/home/user$ touch file1 file2 file3 file4
2. user@host:/home/user$ ls -l
```
total 0
-rw-r--r--  1 user user 0 Nov 19 20:13 file1
-rw-r--r--  1 user user 0 Nov 19 20:13 file2
-rw-r--r--  1 user user 0 Nov 19 20:13 file3
-rw-r--r--  1 user user 0 Nov 19 20:13 file4
Add owner execute bit:

user@host:/home/user$ chmod 744 file1
user@host:/home/user$ ls -l file1
-rwxr--r--  1 user user 0 Nov 19 20:13 file1
Add other write & execute bit:

user@host:/home/user$ chmod 647 file2
user@host:/home/user$ ls -l file2
-rw-r--rwx  1 user user 0 Nov 19 20:13 file2
Remove group read bit:

user@host:/home/user$ chmod 604 file3
user@host:/home/user$ ls -l file3
-rw----r--  1 user user 0 Nov 19 20:13 file3
Add read, write and execute to everyone:

user@host:/home/user$ chmod 777 file4
user@host:/home/user$ ls -l file4
-rwxrwxrwx  1 user user 0 Nov 19 20:13 file4
user@host:/home/user$
```