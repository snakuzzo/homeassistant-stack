First create an `.env` file under main directory with this content

```
HOMEASSISTANT_CONFIGDIR=<Home Assistant Config Directory>
DUCKDNS_SUBDOMAIN=<duckdns.org subdomain>
DUCKDNS_TOKEN=<duckdns.org token>
```

On ./config/Caddyfile...

* Set your external port
* Set your HA Server LAN IP and port

On docker-compose.yaml...

* Set external port to expose Caddy

Don't forget to portforward TCP ports 80 and HA external port to certificates autorenew

Run in foreground with...

`docker-compose up`

Run in background with...

`docker-compose up -d`