# Quick start

For a easy and fast working example a docker compose stack is available.<br />
This enables a great "10 Min" exprience and prevents frustation.

All you need is a linux host and [docker](https://docs.docker.com/engine/install/#server) with the [compose plugin](https://docs.docker.com/compose/install/linux/) installed. <br />
"Docker Desktop" should also work, but was not tested.

Keep in mind that the linux/docker host needs to be run in your local network (LAN) to be able to discover devices & services via SSDP and MDNS. Its also possible that you need to create a firewall rule to allow inbound traffic for the ports `1900/udp` & `5353/udp` if you dont receive any SSDP/MDNS messages in the connector. (Example below)

---

### Create a _`docker-compose.yml`_:
```yaml
version: "3"
services:

  database:
    image: mongo
    container_name: database
    hostname: database

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
    depends_on:
      - database
    tty: true

  frontend:
    image: "openhaus/frontend:latest"
    container_name: frontend
    hostname: frontend
    ports:
      - "80:80"
      - "443:443"
    depends_on:
      - backend
    environment:
      - BACKEND_HOST=backend
      - NODE_ENV=production

  connector:
    image: "openhaus/connector:latest"
    container_name: connector
    hostname: connector
    environment:
      - NODE_ENV=production
      - BACKEND_HOST=127.0.0.1
      - BACKEND_PORT=80 # Frontend container exposed http port, it works as reverse proxy
      - STARTUP_DELAY=2000
    network_mode: host
    depends_on:
      - frontend
    tty: true

```

The host network is needed to send/receive multicast packets to/from the connector to make the autodiscover function over ssdp work.
There is currenlty no other way to forward multicast traffic.

> **Keep in mind to replace `UUID`, `VAULT_MASTER_PASSWORD` & `USERS_JWT_SECRET` with custom values!**

### Download the needed docker images:
```sh
wget https://github.com/OpenHausIO/backend/releases/download/v2.0.0/backend-v2.0.0-docker.tgz
wget https://github.com/OpenHausIO/frontend/releases/download/v1.0.0/frontend-v1.0.0-docker.tgz
wget https://github.com/OpenHausIO/connector/releases/download/v1.0.0/connector-v1.0.0-docker.tgz
```

### Import the images so we can use them:
```sh
gzip -dk --stdout backend-v2.0.0-docker.tgz | docker load
gzip -dk --stdout frontend-v1.0.0-docker.tgz | docker load
gzip -dk --stdout connector-v1.0.0-docker.tgz | docker load
```

> For exporting the images, `docker save openhaus/...:latest | gzip > ./...-vX.X.X-docker.tgz` was used.

### Start everything and boot the application stack:
```sh
docker compose up
```

Then try to access OpenHaus over `http://127.0.0.1`  or the external IP of the host.<br />

If everthings was fine, you have now a wokring OpenHaus stack deployed.

When you have a problem with mdns/ssdp traffic, add the following firewall rules (Example for [`firewalld`](https://firewalld.org/)):
- `firewall-cmd --zone=public --add-port=1900/udp` for ssdp
- `firewall-cmd --zone=public --add-port=5353/udp` for mdns

---

Related links: 
- Docker on CentOS: https://docs.docker.com/engine/install/centos/#install-using-the-repository
- Compose plugin: https://docs.docker.com/compose/install/linux/
- ssdp: https://en.wikipedia.org/wiki/Simple_Service_Discovery_Protocol
- mdsn: https://en.wikipedia.org/wiki/Multicast_DNS