# Accessing the Web UI
The web UI can be accessed from a browser on the same local network as the container by opening `http(s)://IPADDRESS:PORT` (for example: `https://192.168.0.90:8080`).

The default credentials to log in are:
* Username: `admin`
* Password: `adminadmin`

For the sake of your own security, make sure you change these values immediately upon logging into the web UI for the first time. You can do so from the web UI by going to `Tools -> Options -> Web UI`. From there, in the `Authentication` section, change your username and password and click `Save` at the bottom. Be sure to use a strong, random password.

The default credentials are set by the default config file included with this repo. If you have a config file in place already, these defaults do not apply and you would use whatever you have previously set your username and password to.

# Using VueTorrent
If you'd like to use the [VueTorrent](https://github.com/VueTorrent/VueTorrent) alternate web UI, do the following in your web UI once it's up and running:

- Click the "Settings" gear icon.
- Click the "Web UI" tab.
- Check the box for "Use alternative Web UI".
- Set the "Files location" text box to: `/etc/vuetorrent`
- Click "Save".
- The page will refresh and load the VueTorrent web UI. 
- Log in with your normal web UI credentials.