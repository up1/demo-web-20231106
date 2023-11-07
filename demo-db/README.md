# Working with Database
* PostgreSQL

## Create container
```
docker container run --name db \
 -e POSTGRES_DB=demo \
 -e POSTGRES_USER=myuser \
 -e POSTGRES_PASSWORD=pass \
 postgres:16.0
```