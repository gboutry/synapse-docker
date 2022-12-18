# Synapse Installation

The compose file expects the network `proxy` to exist, and a Traefik container is listening to this network.

> :warning: Purpose is only testing, don't use this in production environment 

##  Generate default config:

```bash
export SERVER_NAME=gboutry.lan
# Start only postgresql
docker compose up -d database
# Generate config
docker compose run --rm -it -v ./config/etc/synapse:/data -e SYNAPSE_SERVER_NAME=$SERVER_NAME -e SYNAPSE_REPORT_STATS=yes homeserver generate
```

## Start

```bash
docker compose up -d
```

## Destroy

```bash
docker compose down --volumes
```
