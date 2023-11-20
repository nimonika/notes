# Handy docker commands

## docker run with port mapping and env vars

```
docker run -p 2080:2080 -e FRME_SPARQL_QUERY_ENDPOINT=http://host.docker.internal:7200/repositories/fpeData 023060cd6b51
```