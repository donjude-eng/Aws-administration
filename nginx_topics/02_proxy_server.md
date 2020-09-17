events {}

http {
        server {

         listen 8888;

         location / {

         return 200 " Hello from NGINX\n";
        }
          location /php {
            proxy_pass 'http://localhost:9999/';
   }
 }
}