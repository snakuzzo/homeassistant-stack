# Home Assistant Stack with Docker Compose

This is a docker compose to create an Home Assistant stack with:

- Home Assistant Core
- Caddy Server (to autorenew certificates)
- Eclipse Mosquitto MQTT broker
- Zigbee2Mqtt
- Portainer

## Installation steps

Make a copy of `mosquitto/config/mosquitto.example.conf` file as `mosquitto/config/mosquitto.conf`

Make a copy of `zigbee2mqtt/config/configuration.example.yaml` file as `zigbee2mqtt/config/configuration.yaml`
(if you are restoring a backup copy your entire zigbee2mqtt config directory under `zigbee2mqtt/config` dir)

Make a copy of `.env.dist` file as `.env` under main directory and edit its content. E.g.:

```bash
HOMEASSISTANT_CONFIGDIR=/home/user/docker-compose/homeassistant
HOMEASSISTANT_LOCAL_URL=http://192.168.1.2:8123
HOMEASSISTANT_LOCAL_PORT=8123
HOMEASSISTANT_EXTERNAL_URL=https://example.duckdns.org:8124
HOMEASSISTANT_EXTERNAL_PORT=8124
MOSQUITTO_PORT=1883
Z2M_DEVICE_PORT=/dev/ttyUSB0
PORTAINER_PORT=9000
```

## Running stack

Run in foreground with...

`docker-compose up`

Run in background with...

`docker-compose up -d`

## Warning

Don't forget to portforward TCP ports 80 or 443 (to allow certificates autorenew) and HA external port
