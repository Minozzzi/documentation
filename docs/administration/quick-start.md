# Quick start

For a easy and fast working example a docker compose stack is available.<br />
This enables a great "10 Min" exprience and prevents frustation.

All you need is a linux host and [docker](https://docs.docker.com/engine/install/#server) with the [compose plugin](https://docs.docker.com/compose/install/linux/) installed. <br />
"Docker Desktop" should also work, but was not tested.

---

Create a nginx config (_`open-haus.conf`_) with the following content:
```nginx
map $http_upgrade $connection_upgrade {
  default upgrade;
  ''      close;
}

server {

    listen 80 default_server;
    server_name 127.0.0.1 localhost open-haus.lan open-haus.local;

    server_tokens off;

    location = /favicon.ico { access_log off; log_not_found off; }
    location = /robots.txt  { access_log off; log_not_found off; }

    location ~ /(api|auth)/(.*)$ {
        resolver 127.0.0.11;
        proxy_pass http://backend:8080/$1/$2;
        proxy_http_version 1.1;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header Connection $connection_upgrade;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

    location ~ /(.*)$ {
        resolver 127.0.0.11;
        proxy_pass http://frontend:80/$1;
        proxy_http_version 1.1;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_set_header Connection $connection_upgrade;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

}
```

Create a _`docker-compose.yml`_:
```yaml
version: "2"
services:
  nginx:
    image: "nginx:1.23.2-alpine"
    container_name: nginx
    hostname: nginx       
    volumes:
      - "./open-haus.conf:/etc/nginx/conf.d/open-haus.conf"
    ports:
      - "80:80"
      - "443:443"
    depends_on:
      - backend
      - frontend
  database:
    image: mongo
    container_name: database
    hostname: database      
    ports:
      - "27017:27017"
  backend:
    image: "openhaus/backend:latest"
    container_name: backend
    hostname: backend    
    environment:
      - NODE_ENV=production
      - DATABASE_HOST=database
      - UUID=00000000-0000-0000-0000-000000000000
      - VAULT_MASTER_PASSWORD=Pa$$w0rd
      - USERS_JWT_SECRET=Pa$$W0rd
      - API_AUTH_ENABLED=false
    ports:
      - "8080:8080"
    depends_on:
      - database
    tty: true
  frontend:
    image: "openhaus/frontend:latest"
    container_name: frontend
    hostname: frontend      
    ports:
      - "3000:80"
    depends_on:
      - backend
  connector:
    image: "openhaus/connector:latest"
    container_name: connector
    hostname: connector  
    ports:
      - "1900:1900"    
    environment:
      - NODE_ENV=production
      - BACKEND_HOST=backend
    depends_on:
      - backend
    tty: true
```


> **Keep in mind to replace `UUID`, `VAULT_MASTER_PASSWORD` & `USERS_JWT_SECRET` with custom values!**

Download the needed docker images:
```sh
wget https://github.com/OpenHausIO/backend/releases/download/v2.0.0/backend-v2.0.0-docker.tgz
wget https://github.com/OpenHausIO/frontend/releases/download/v1.0.0/frontend-v1.0.0-docker.tgz
wget https://github.com/OpenHausIO/connector/releases/download/v1.0.0/connector-v1.0.0-docker.tgz
```

Import the images so we can use them:
```sh
gzip -dk --stdout backend-v2.0.0-docker.tgz | docker load
gzip -dk --stdout frontend-v1.0.0-docker.tgz | docker load
gzip -dk --stdout connector-v1.0.0-docker.tgz | docker load
```

> For exporting the images, `docker save openhaus/...:latest | gzip > ./...-vX.X.X-docker.tgz` was used.

Start everything and boot the application stack:
```sh
docker compose up
```

Then try to access OpenHaus over `http://127.0.0.1` (`localhost` does not work. You will get only the default nginx page.) or the external IP of the host.<br />

If everthings was fine, you have now a wokring OpenHaus stack deployed.

---

Related links: 
- Docker on CentOS: https://docs.docker.com/engine/install/centos/#install-using-the-repository
- Compose plugin: https://docs.docker.com/compose/install/linux/