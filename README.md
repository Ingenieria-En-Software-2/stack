# stack

## Setup

Add .env in the root folder and add the following variables:

```bash
POSTGRES_USER=<user>
POSTGRES_PASSWORD=<password>
POSTGRES_DB=<db name>
```

## Run Stack with docker compose

```bash
docker-compose up --build -d
```

In localhost, frontend, backend and postgres services will be started at 9010 
and 5432 ports respectively
