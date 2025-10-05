# How to use Wireguard 
Drop a .conf file from your VPN provider into `/config/wireguard` and start the container. The file must have the name `wg0.conf`, or it will fail to start. In the qBittorrent web UI, go to `Tools -> Options -> Advanced` and set `Network Interface` to `wg0`. This instructs qBittorrent to only use the Wireguard network connection. This is important to prevent IP leaks.

# Wireguard IPv6 issues
If you use Wireguard and also have IPv6 enabled, it is necessary to add the IPv6 range to the `LAN_NETWORK` environment variable.  
Additionally the parameter `--sysctl net.ipv6.conf.all.disable_ipv6=0` also must be added to the `docker run` command.
