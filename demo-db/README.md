# Working with Database
* PostgreSQL

## Create container
```
docker container run -d --name db \
 -e POSTGRES_DB=demo \
 -e POSTGRES_USER=myuser \
 -e POSTGRES_PASSWORD=pass \
 postgres:16.0
```

Access to database and check tables and data for testing
```
$docker container exec -it db bash
>psql -d demo -U myuser
// Change database
>\c postgres
// Show all tables
>\dt

// Get all data from tables
>select * from merchants;

// Quit
>\q
```