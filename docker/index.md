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

## mount a local directory and store the data from graphdb to persist it

```
docker run -d -p 7201:7200 -v $(pwd)/graphdb-data:/opt/graphdb/home/data --name graphdb docker.io/ontotext/graphdb:10.5.0
```

## make a docker volume and mount that instead of the local directory

```
docker volume create graphdb-data
```
```
docker run -d -p 7202:7200 -v graphdb-data:/opt/graphdb/home/data --name graphdb001 docker.io/ontotext/graphdb:10.5.0
```
## stop a container

```
docker rm -f graphdb001
```

## remove a volume
```
docker volume remove graphdb-data
```

