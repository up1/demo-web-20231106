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

$docker compose logs --follow
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

Call API with URLs
* List all merchants => GET http://127.0.0.1:3000
* Create a new merchant => POST http://127.0.0.1:3000/merchants
```
{
    "name": "new name",
    "email": "new@email.com"
}
```

Delete all services
```
$docker compose down
```

## Step 3 :: Build and create container
* Start database
  * Database instance
  * Tables and Constraints
  * Data for testing
* Start backend

```
$docker compose up -d backend --build
$docker compose ps
NAME                    IMAGE                 COMMAND                  SERVICE   CREATED         STATUS                   PORTS
postgres                postgres:16.0         "docker-entrypoint.s…"   db        2 minutes ago   Up 2 minutes (healthy)   0.0.0.0:5432->5432/tcp
workshop-02-backend-1   workshop-02-backend   "docker-entrypoint.s…"   backend   2 minutes ago   Up 2 minutes             0.0.0.0:3000->3000/tcp
```

Test API again ...

Delete all services
```
$docker compose down
```
