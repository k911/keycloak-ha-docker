# Keycloak HA

Configured using docker and docker-compose

## Running

```sh
docker-compose up -d coredns
docker-compose up -d db
docker-compose up -d keycloak-a keycloak-b

# goto: http://localhost:8080 or http://localhost:9090
```

Now you can try breaking stuff

```sh
docker-compose restart keycloak-b
```

..and checking logs

```sh
docker-compose logs -f keycloak-a
```

## Debuging DNS

```sh
docker-compose build runner
docker-compose run --rm runner bash

dig keycloak.service-discovery.local

# on 2nd tab:
docker-compose logs -f coredns
```
