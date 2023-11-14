# ☀ Deployment


## ☀ Deployment

## Background

* This deployment architecture is designed to make self-hosting AppFlowy-Cloud as easy as possible.
* Deployment can be done in a single machine which only needs `docker` to be installed.
* [Cloud Deployment Guide](https://github.com/AppFlowy-IO/AppFlowy-Cloud/blob/main/doc/deployment.md)

## Deployment Architecture

![img.png](img.png)

### Routing

* After `docker compose up -d` is ran, AppFlowy-Cloud will be serving in [localhost](http://localhost) at both port 80 and 443
* Host Machine should expose either HTTP(80) or HTTPS(443) port.
* AppFlowy Native Application should then be configured to connect to Host Machine through IP or hostname.
* `/gotrue` → GoTrue Auth Server
* `/api` → AppFlowy-Cloud HTTP
* `/ws` → AppFlowy-Cloud Web Socket
* `/web` → AppFlowy User Admin Frontend
* `/pgadmin` → Postgres database control panel
* `/minio` → Minio Web UI
* `/portainer` → Container Management
