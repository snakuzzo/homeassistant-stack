# Home Assistant Stack with Docker Compose

This is a docker compose to create an Home Assistant stack with:

- Home Assistant Core
- DuckDNS (to renew IP-DDNS)
- Caddy Server (to autorenew certificates)

## Installation steps

First, make a copy of `.env.dist` file as `.env` under main directory and edit its content. E.g.:

```bash
HOMEASSISTANT_CONFIGDIR=<Home Assistant Config Directory>
HOMEASSISTANT_LOCAL_URL=http://192.168.1.2:8123
HOMEASSISTANT_LOCAL_PORT=8123
HOMEASSISTANT_EXTERNAL_URL=https://example.duckdns.org:8124
HOMEASSISTANT_EXTERNAL_PORT=8124
DUCKDNS_SUBDOMAIN=example # if your DDNS is example.duckddns.org
DUCKDNS_TOKEN=<duckdns.org token>
```

### ./config/Caddyfile

set your external port

set your HA Server LAN IP and port

### ./docker-compose.yaml

set external port to expose Caddy

### router

Don't forget to portforward TCP ports 80 and HA external port to certificates autorenew

## Running stack

Run in foreground with...

`docker-compose up`

Run in background with...

`docker-compose up -d`
