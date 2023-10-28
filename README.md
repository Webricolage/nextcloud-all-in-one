# Nextcloud all-in-one (AIO)

A Docker Compose file to spin up a Nextcloud instance with everything ready-to-go.

See also: https://github.com/nextcloud/all-in-one

The container is connected to a Docker network to be used in a reverse proxy environment (Nginx Proxy Manager).

To restart the Docker container after a system reboot on a systemd system execute the following:

```sh
curl -fsSL https://techoverflow.net/scripts/create-docker-compose-service.sh | sudo bash /dev/stdin
```

More info: https://techoverflow.net/2020/10/24/create-a-systemd-service-for-your-docker-compose-project-in-10-seconds/
