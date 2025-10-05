This is a list of all environment variables supported by the container. Each item in the list includes whether or not the variable is required, a description of its function in the container, an example value, and a default value (where applicable). These values are vital to proper configuration of your container.

***

### `QBT_LEGAL_NOTICE`
  * Required
  * Required by qBittorrent itself, indicates that you accept their [legal notice](https://github.com/qbittorrent/qBittorrent/blob/56667e717b82c79433ecb8a5ff6cc2d7b315d773/src/app/main.cpp#L320-L323).
  * Example value: `QBT_LEGAL_NOTICE=confirm`
  * Default value: n/a

***

### `LAN_NETWORK`
  * Required (at least one)
  * Comma delimited list of local networks with CIDR notation
  * Example value: `LAN_NETWORK=192.168.0.0/24,10.10.0.0/24`
  * Default value: n/a

***

### `ENABLE_SSL`
  * Not required
  * Enable SSL automatically (yes), disable it automatically (no), or ignore it so it can be managed by the user (ignore).
  * Example value: `ENABLE_SSL=yes`
  * Default value: `ignore`

***

### `NAME_SERVERS`
  * Not required
  * Comma-delimited name servers
  * Example value: `NAME_SERVERS=1.1.1.1,1.0.0.1`
  * Default value: `1.1.1.1,1.0.0.1`

***

### `PUID`
  * Required
  * This is the UID used to run the qBittorrent process and is applied to /config and /downloads inside the container. You can get this value by running the following on your host machine (not inside the container) where username is the username to get the UID for: `id username`
  * Example value: `PUID=99`
  * Default value: n/a

***

### `PGID`
  * Required
  * This is the GID used to run the qBittorrent process and is applied to /config and /downloads inside the container. You can get this value by running the following on your host machine (not inside the container) where username is the username to get the GID for: `id username`
  * Example value: `PGID=100`
  * Default value: n/a

***

### `HEALTH_CHECK_HOST`
  * Not required
  * Can be a hostname (ex: one.one.one.one) or IP (1.1.1.1). This is the host or IP that the healthcheck script will ping to confirm whether the network is up.
  * Example value: `HEALTH_CHECK_HOST=one.one.one.one`
  * Default value: `one.one.one.one`

***

### `HEALTH_CHECK_INTERVAL`
  * Not required
  * This is the time in seconds that the container waits to see if the internet connection still works (checking to see if the VPN tunnel died).
  * Example value: `HEALTH_CHECK_INTERVAL=300`
  * Default value: `300`

***

### `HEALTH_CHECK_SILENT`
  * Not required
  * Set to `1` to suppress the 'Network is up' message during each iteration of the healthcheck loop. If set to `0`, this message will be displayed on each iteration. Useful for troubleshooting connection problems.
  * Example value: `HEALTH_CHECK_SILENT=1`
  * Default value: `1`

***

### `HEALTH_CHECK_AMOUNT`
  * Not required
  * The amount of pings that are sent when checking the connection. If any of the pings are successful, the network is considered healthy.
  * Example value: `HEALTH_CHECK_AMOUNT=10`
  * Default value: `1`

***

### `RESTART_CONTAINER`
  * Not required
  * Set to `no` to **disable** the automatic restart when the network is possibly down. Set to `yes` to **enable** the automatic restart.
  * Example value: `RESTART_CONTAINER=yes`
  * Default value: `yes`

***

### `ADDITIONAL_PORTS`
  * Not required
  * Adding a comma-delimited list of ports will allow these ports via the iptables script. This is just for if you want to statically allow extra ports beyond the default one.
  * Example value: `ADDITIONAL_PORTS=1234,8112`
  * Default value: n/a

***

### `ENABLEPROTONVPNPORTFWD`
  * Not required
  * Enables Proton VPN port forwarding logic. 1 to enable, 0 to disable.
  * Example value: `ENABLEPROTONVPNPORTFWD=1`
  * Default value: `0`

***

### `WEBUI_URL`
  * Required if port forwarding is enabled
  * The base URL for your web UI, used for API calls. Don't include a trailing `/`.
  * Example value: `WEBUI_URL=https://webui.domain.com` / `WEBUI_URL=http://192.168.1.17:8080`
  * Default value: n/a

***

### `WEBUI_USER`
  * Required if port forwarding is enabled
  * The user name for authenticating to your web UI's API. This is the username you use to access your web UI, which defaults to `admin`.
  * Example value: `WEBUI_USER=admin`
  * Default value: n/a

***

### `WEBUI_PASS`
  * Required if port forwarding is enabled
    * NOTE: You can either pass this as an environment variable, or you can create a secret in your .yml file called webui_pass. See the template Docker-Compose.yml file for an example.
  * The password for authenticating to your web UI's API. This is the password you use to access your web UI, which defaults to `adminadmin`.
  * Example value: `WEBUI_PASS=adminadmin`
  * Default value: n/a

***

### `TZ`
  * Not required
  * Sets the time zone in the container so that log date/time will match your local date/time.
  * Example value: `TZ=America/New_York`
  * Default value: n/a