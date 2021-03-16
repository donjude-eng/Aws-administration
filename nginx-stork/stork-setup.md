# Nginix is installed and enabled the firewall on both the ports.

- Error: (13: Permission denied) while connecting to upstream:[nginx]
- ANS : setsebool -P httpd_can_network_connect 1
- Reference : https://stackoverflow.com/questions/23948527/13-permission-denied-while-connecting-to-upstreamnginx

- Directory is missing in the default confiduration
- Reference : https://stackoverflow.com/questions/17413526/nginx-missing-sites-available-directory

```upstream api_app {
  server 127.0.0.1:3000;
  keepalive 8;
}
server {
  server_name ubool.localdev.com;
  access_log /var/log/nginx/access.ubool.localdev.com;
  error_log /var/log/nginx/error.ubool.localdev.com;
  location / {
    proxy_pass http://api_app/;
    proxy_redirect off;
  }
}
```
