This is a list of ports that are exposed by the container by default. Each item includes the port number, the protocol used, whether or not the port must be exposed, a description of the function of the port, and an example mapping.

### `8080`
  * Protocol: TCP
  * Required
  * This is the listen port for the qBittorrent web UI.
  * Example mapping: `8080:8080`

***

### `8999`
  * Protocol: TCP
  * Not required
  * This is the qBittorrent listen port for incoming connection requests. 8999 is the default port, but you can use whatever you like. If you use port forwarding through Proton VPN, you do not need to specify a listen port here at all.
  * Example mapping: `8999:8999`

### `8999`
  * Protocol: UDP
  * Not required
  * This is the qBittorrent listen port for incoming connection requests. 8999 is the default port, but you can use whatever you like. If you use port forwarding through Proton VPN, you do not need to specify a listen port here at all.
  * Example mapping: `8999:8999/udp`