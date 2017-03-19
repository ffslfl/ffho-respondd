respondd Status for Servers
---------------------------------

A gluon compatible status script for respondd in python.

## Dependencies

 * lsb_release
 * ethtool
 * python3.3
 * python3-netifaces
 * batman-adv

## Setup

### config.json
Startparameter for ext-respondd.
Copy `config.json.example` to `config.json` and change it to match your server configuration.
(`cp config.json.example config.json`)

 * `batman` (string) (Needed: typical bat0)
 * `bridge` (string) (Needed: typical br-client)
 * `mesh-wlan` (array of string) (Optional: Ad-Hoc batman-Mesh)
 * `mesh-vpn` (array of string) (Optional: fastd, GRE, L2TP batman-Mesh)
 * `fastd_socket` (string) (Optional: needed for uplink-flag)


### respondd.service
Register respondd as a systemd service

```
cp respondd.service.example /lib/systemd/system/respondd.service
# modify the path inside of the respondd.service if needed
systemctl daemon-reload
systemctl enable respondd
systemctl start respondd
```

## Related projects

Collecting data from respondd:
* [yanic](https://github.com/FreifunkBremen/yanic) from Freifunk Bremen written in Go
* [HopGlass Server](https://github.com/hopglass/hopglass-server) written in Node.js

Respondd for servers:
* [ext-respondd](https://github.com/ffggrz/ext-respondd) from Freifunk Gera-Greiz
* [ffnord-alfred-announce](https://github.com/ffnord/ffnord-alfred-announce) from FreiFunkNord
* [py-respondd](https://github.com/descilla/py-respondd)
* [respondd](https://github.com/FreifunkBremen/respondd) from Freifunk Bremen (just a proof of concept)

