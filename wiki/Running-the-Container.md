# Docker Run
The container is available from the Docker Hub and this is the simplest way to get it. Alternatively, you can clone this repo and build the image yourself if you want.
The following is a run command with the minimum required arguments. You'll need to edit the environment variables, ports, and volumes values to work with your environment. See the wiki pages [Environment Variables](https://github.com/tenseiken/docker-qbittorrent-wireguard/wiki/Environment-Variables), [Ports](https://github.com/tenseiken/docker-qbittorrent-wireguard/wiki/Ports), and [Volumes](https://github.com/tenseiken/docker-qbittorrent-wireguard/wiki/Volumes) for more info about configuring your container.

```
docker run  -d \
              -v /your/config/path/:/config \
              -v /your/downloads/path/:/downloads \
              -e "QBT_LEGAL_NOTICE=confirm" \
              -e "PUID=1234" \
              -e "PGID=123" \
              -e "LAN_NETWORK=192.168.0.0/24" \
              -p 8080:8080 \
              --privileged \
              --cap-add NET_ADMIN \
              --sysctl "net.ipv4.conf.all.rp_filter=2" \
              --sysctl "net.ipv4.conf.all.src_valid_mark=1" \
              --sysctl "net.ipv6.conf.all.disable_ipv6=1" \
              --restart unless-stopped \
              --name qbittorrent-wireguard \
              tenseiken/qbittorrent-wireguard:latest
```

# Docker-Compose
If you prefer to use docker-compose instead of docker run, you can use the Docker-Compose.yml file to get started. It only has the required configuration (as with the docker run command above), but it will get you started. You'll need to edit the environment variables, ports, and volumes values in the .yml file to work in your environment.