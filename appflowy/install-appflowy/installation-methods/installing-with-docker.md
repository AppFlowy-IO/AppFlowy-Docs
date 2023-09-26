# Docker

A simple way of running AppFlowy is with the use of a Docker container. And we have one for you at [Docker Hub](https://hub.docker.com/r/appflowyio/appflowy\_client)!

```
docker run --rm \
  -v $HOME/.Xauthority:/root/.Xauthority:rw \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  -v /dev/dri:/dev/dri \
  -v /var/run/dbus/system_bus_socket:/var/run/dbus/system_bus_socket \
  -v appflowy-data:/home/appflowy \
  -e DISPLAY=${DISPLAY} \
  appflowyio/appflowy_client:main
```

Using the `main` tag you will run the latest Appflowy version (from the `main` branch). You can also use specific releases using the tags (such as `0.0.5.3`). Check out the [available tags](https://hub.docker.com/r/appflowyio/appflowy\_client/tags).

**Note:** Appflowy inside docker needs access to your X server. In case of lack of permissions, it's recommended to build the docker image yourself. The least recommended option is running `xhost +` before running the container, but this command is [considered dangerous](https://stackoverflow.com/questions/63884968/why-is-xhost-considered-dangerous)! So make sure you run `xhost -` after it.

## Building the docker image

## First thing to do

Make sure you already have Docker and docker-compose fully working before attempting this procedure.

For more information, check out:

* [Docker official documentation](https://docs.docker.com/engine/install/)
* [Docker Arch linux docs](https://wiki.archlinux.org/title/Docker)

In order to run Docker without `sudo` you must add your username to the docker group. To do this use the following command and then logout and login for it to take effect.

```bash
sudo usermod -aG docker yourusername
```

## Building without cloning the repository

There is no need to clone the whole repository. You can simply create a directory and download the required Docker files into that directory.

```bash
wget https://raw.githubusercontent.com/AppFlowy-IO/appflowy/main/frontend/scripts/docker-buildfiles/Dockerfile
wget https://raw.githubusercontent.com/AppFlowy-IO/appflowy/main/frontend/scripts/docker-buildfiles/docker-compose.yml
```

Now you are ready to build the docker image (this can take some time)

```bash
docker-compose build --build-arg uid=$(id -u) --build-arg gid=$(id -g)
```

Lastly, run the docker container

```bash
docker-compose up
```

## Building with the repository installed

If you already have the repository installed then you're halfway there!

```bash
cd ./frontend/scripts/docker-buildfiles
docker-compose build --build-arg uid=$(id -u) --build-arg gid=$(id -g)
```

Lastly, run the docker container

```
docker-compose up
```
