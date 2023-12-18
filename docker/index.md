# Handy docker commands

## docker run with port mapping and env vars

```shell
docker run -p 2080:2080 -e FRME_SPARQL_QUERY_ENDPOINT=http://host.docker.internal:7200/repositories/fpeData 023060cd6b51
```

## prune everything

```
docker system prune -a
```

## pull and run an image

```
docker run -d -p 7201:7200 --name graphdb docker.io/ontotext/graphdb:10.5.0
```
