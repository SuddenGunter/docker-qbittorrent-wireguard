This is a list of docker volumes that I highly recommend using when spinning up your container. Each item includes the name of the volume, the path in the container, a description of its function, and an example mapping. These volumes are not required, but without them you will lose anything stored in each location when you remove the container.

### `config`
  * Path in container: `/config`
  * This is where configuration files are stored for qBittorrent and Wireguard.
  * Example mapping (left of : is the path on host, right is path in container): `/your/config/path/:/config`

***

### `downloads`
  * Path in container: `/downloads`
  * This is the default download path where files are downloaded.
  * Example mapping (left of : is the path on host, right is path in container): `/your/downloads/path/:/downloads`