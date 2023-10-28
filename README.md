# Nextcloud all-in-one (AIO)

A Docker Compose file to spin up a Nextcloud instance with everything ready-to-go. Based on Nextcloud's official Docker project: https://github.com/nextcloud/all-in-one

## Usage

Create a Docker network if you haven't already:

```sh
docker network create docker-network
```

Make sure that you have the reverse-proxy running as a host on the same network. I use [Nginx Proxy Manager (NPM)](https://nginxproxymanager.com/); see my own config in [this repository](https://github.com/Webricolage/nginx-proxy-manager).

Spin up the main container and all it's children:

```sh
docker-compose up -d
```

## Modifications vis-a-vis the official Docker Compose file

The container is connected to a Docker network to be used in a reverse proxy environment (Nginx Proxy Manager). The internal Apache port and local IP have been adjusted accordingly. Also, a minor change has been made to point to where `docker.sock` is located on Arch Linux-based systems.

Carefully read all the [documentation and helpful user questions around Nextcloud all-in-one](https://github.com/nextcloud/all-in-one/) to get a better understanding of what's going on here.

## Automatically restart after a system reboot

To restart the Docker container after a system reboot on a systemd system execute the following:

```sh
curl -fsSL https://techoverflow.net/scripts/create-docker-compose-service.sh | sudo bash /dev/stdin
```

More info: https://techoverflow.net/2020/10/24/create-a-systemd-service-for-your-docker-compose-project-in-10-seconds/

