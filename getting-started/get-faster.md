# 🏎 Get faster

In order to speed up the DB queries, it's possible to enable ArangoDB's query cache. \
\
To do so:

-   Create a `conf` folder right beside the `docker-compose.prod.yml` with a `arangodb` folder in it.
-   Copy our [arangod.conf](https://github.com/leav-solutions/leav-engine/blob/master/docker/conf/arangodb/arangod.conf) file in it.
-   Mount this directory in the `arangodb` service, by adding this volume in the `docker-compose.prod.yml` file:

```
- ./conf/arangodb/arangod.conf:/etc/arangodb3/arangod.conf
```

Don't forget to re-launch your containers with _down / up_ commands. \
\
_More info about the cache on_ [_ArangoDB docs_](https://www.arangodb.com/docs/stable/aql/execution-and-performance-query-cache.html#global-configuration)_._
