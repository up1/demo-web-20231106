# Workshop
* Frontend
  * ReactJS
* Backend
  * NodeJS
  * PostgreSQL

## Step 1 :: Create database with PostgreSQL
```
$docker compose up -d db
$docker compose ps
NAME       IMAGE           COMMAND                  SERVICE   CREATED         STATUS         PORTS
postgres   postgres:16.0   "docker-entrypoint.s…"   db        3 seconds ago   Up 2 seconds   0.0.0.0:5432->5432/tcp
```

Access to database and check tables and data for testing
```
$docker container exec -it postgres bash
>psql -d postgres -U postgres
// Change database
>\c postgres
// Show all tables
>\dt

// Get all data from tables
>select * from merchants;

// Quit
>\q
```

## Step 2 :: Build and create container of Backend
```
$docker compose build backend
$docker compose up -d backend
$docker compose ps
$docker compose logs --follow
```

CAll API with URLs
*