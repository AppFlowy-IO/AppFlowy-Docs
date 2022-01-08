# Docker

A simple way of running AppFlowy is with the use of a Docker container. And we have one for you!

**Notes:**

* This Docker container is based on Arch linux.
* Any Linux/Mac machine should work, because you need to `xhost local:root`. I'm not sure if Windows support this.
* You only have to build the docker image once. After that, simply run `docker-compose up` from the directory.

## First thing to do

* Make sure you already have Docker and docker-compose fully working before attempting this procedure. For Arch you can read here [Docker Arch linux docs](https://wiki.archlinux.org/title/Docker)
* In order to run Docker without `sudo` you must add your username to the docker group. To do this on Arch use the following command and then logout and login for it to take effect.

```bash
sudo usermod -aG docker yoursername
```

## Building without cloning the repository

There is no need to clone the whole repository. You can simply create a directory and download the required Docker files into that directory.

### Steps

These steps are identical on all operating systems.

* Step 1: Download the Docker file.

```bash
wget https://raw.githubusercontent.com/AppFlowy-IO/appflowy/main/frontend/scripts/docker-buildfiles/Dockerfile
```

* Step 2: Download the docker-compose file.

```bash
wget https://raw.githubusercontent.com/AppFlowy-IO/appflowy/main/frontend/scripts/docker-buildfiles/docker-compose.yml
```

* Step 3: Provide access of appflowy to X session

```
xhost local:root
```

* Step 4: build the docker image (this can take some time)

```
docker-compose build
```

* Step 5: run the docker container

```
docker-compose up
```

## Building with the repository installed

If you already have the repository installed then you're halfway there!

### Steps:

These steps are identical on all operating systems.

* Step 1: cd into docker-buildfiles

```
cd ./appflowy/doc/docker-buildfiles
```

* Step 2: Provide access of appflowy to X session

```
xhost local:root
```

* Step 3: build the docker image (this can take some time)

```
docker-compose build
```

* Step 4: run the docker container

```
docker-compose up
```
