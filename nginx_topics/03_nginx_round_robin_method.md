* First install nginx
`` ssh command here ``
* Install nginx
``` sudo apt-get install -y nginx ``
* Check the host status
``` sudo netstat -ntpl```
* Check the running status of nginx
``` sudo systemctl status nginx ```
* Command uname to get the index file
``` uname -n | sudo tee /usr/share/nginx/html/index.html ```

## Or another way to setup the nginx load balancer;
* > start two instances and create the ssh and load in in two powershell.
* > install nginx, and enable the firewall
* > Check the status of nginx with ` sudo systemctl status nginx  ` and the port status command is ` sudo netstat -nptl`
* > If the status of both are active then go to edit both instace file from `cd /var/www/html/index.html`
* > Once the file is update then type `curl localhost` to see if the server is up.
* > Then go to the `loadbalancer` instance and edit the default file in `sites-available` and save and exit
  1. The file format should be :
  ```
  upstream web_backend {
        server 13.235.114.105;
        server 13.126.205.139;
        }

        server {
                listen 80;

                location / {
                        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                        proxy_pass http://web_backend;
                }

                location /nginxorg {
                proxy_pass 'http://nginx.org/;
            }
        }

  ```

* once this is update reload nginx `sudo systemctl reload nginx` and open the ip in the browser.
