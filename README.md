# Home Assistant Stack with Docker Compose

This is a docker compose to create an Home Assistant stack with:

Home Assistant Core
DuckDNS (to renew IP-DDNS)
Caddy Server (to autorenew certificates)

## Installation steps

First create an `.env` file under main directory with this content

```bash
HOMEASSISTANT_CONFIGDIR=<Home Assistant Config Directory>
DUCKDNS_SUBDOMAIN=<duckdns.org subdomain>
DUCKDNS_TOKEN=<duckdns.org token>
```

## ./config/Caddyfile

set your external port

set your HA Server LAN IP and port

### ./docker-compose.yaml

set external port to expose Caddy

### router

Don't forget to portforward TCP ports 80 and HA external port to certificates autorenew

### Running stack

Run in foreground with...

`docker-compose up`

Run in background with...

`docker-compose up -d`
