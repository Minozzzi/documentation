```nginx
http {

map $http_upgrade $connection_upgrade {
    default upgrade;
    ''      close;
}

server {

 listen 80;
 server_name 127.0.0.1 localhost open-haus.lan open-haus.local;

 # remove server version
 server_tokens off;

 try_files $uri $uri/ =404;

 autoindex off;

 location = /favicon.ico { access_log off; log_not_found off; }
 location = /robots.txt  { access_log off; log_not_found off; }

 location ~ ^/(api|auth)/$ {
     proxy_pass http://127.0.0.1:8080/$1;
     proxy_http_version 1.1;
     proxy_set_header X-Forwarded-Proto $scheme;
     proxy_set_header Connection $connection_upgrade;
     proxy_set_header Upgrade $http_upgrade;
     proxy_set_header Host $host;
     proxy_set_header X-Real-IP $remote_addr;
     proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
 }

 location ~ ^/(.*)$ {
     proxy_pass http://127.0.0.1:3000/$1;
     proxy_http_version 1.1;
     proxy_set_header X-Forwarded-Proto $scheme;
     proxy_set_header Connection $connection_upgrade;
     proxy_set_header Upgrade $http_upgrade;
     proxy_set_header Host $host;
     proxy_set_header X-Real-IP $remote_addr;
     proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
 }

}

}
```

```yaml
version: "2"
services:
  nginx:
    image: "nginx:1.23.2-alpine"
    volumes:
      - "./nginx.conf:/etc/nginx/nginx.conf"
    ports:
      - "80:80"
      - "443:443"
    depends_on:
      - backend
      - frontend      
  database:
    image: mongo
    ports:
      - "27017:27017"
  backend:
    image: "openhaus/backend:latest"
    environment:
      - NODE_ENV=production
      - DATABASE_HOST=database
      - UUID=00000000-0000-0000-0000-000000000000
      - VAULT_MASTER_PASSWORD=Pa$$w0rd
    ports:
      - "8080:8080"
    depends_on:
      - database
  frontend:
    image: "openhaus/frontend:latest"
    ports:
      - "3000:3000"
    depends_on:
      - backend
  connector:
    image: "openhaus/connector:latest"
    depends_on:
      - backend
    net: host
```

https://hub.docker.com/_/nginx
Using environment variables in nginx configuration (new in 1.19)