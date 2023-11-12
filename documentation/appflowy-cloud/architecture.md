# 🌈 Architecture

## 🌈 Architecture

* This articles goes through self-host AppFlowy Cloud's architecture after deployment.
* For the rest of the article, we will `myhost` as the hostname/ip of the machine where AppFlowy Cloud is deployed in.

![img\_1.png](img\_1.png)

From the diagram, there are 5 entrypoints for end user usage, we categorized them into the following

* Client Usage
* Observability Tools

## Client Usage

This is where regular AppFlowy Cloud users should spend most of their time in.

### AppFlowy Native Application

* Dependencies: GoTrue, AppFlowy-Cloud
* Client Application specific to various Operating System(Windows, Mac, Linux)

### User Admin Web UI

* Dependency: GoTrue, Redis
* Account management for both Admin and Non-Admin users.
* Accessible at https://hostname/web
* Admin capabilities
  * User creation, deletion, password change
  * Generating sign in link for users
* Non-Admin capabilities
  * Password Change
  * User Invitation (via email)

## Observability Tools

Strictly speaking, the following are not essentially for cloud functionality, but recommended to have for various reasons including:

* Resource Usage
* Database performance

Usernames and password are generated during the initialization phase. Kindly refer to environmental variables for login credentials.

### PgAdmin

* Dependency: Postgres
* Postgres database administration tool
* Accessible at [https://myhost/pgadmin](https://myhost/web)

### Minio Web UI

* Depdency: None
* File storage management
* Accessible at [https://myhost/minio](https://myhost/web)

### Portainer

* Depdency: None
* Docker container management
* Accessible at https://myhost/portainer

## Services

Core services that AppFlowy Native Application would need

### AppFlowy-Cloud

* Dependencies: GoTrue, Postgres, Redis, Minio
* Provides core functionalities to AppFlowy Native Application

### GoTrue

* Dependencies: Postgres
* Authentication Server for Native Application, User Admin, and AppFlowy-Cloud
* Source of truth for user creation/deletion/verification

## Data Storage

### Postgres

* Essential data storage for AppFlowy Cloud and Gotrue

### Redis

* Used as cache for AppFlowy Cloud and User Admin Web for session management.

### Minio

* S3 API Compatible File Storage
* Refer to deployment guide if you want to configure to switch to your S3 Storage instead
