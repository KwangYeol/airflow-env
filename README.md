# Airflow Developer Environment

Minimal Airflow dags development environment in docker

- Using: https://github.com/puckel/docker-airflow

## Prepare

Install docker and docker-compose on your development machine.

- [Install Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/install/)
- [Install Docker Desktop for Windows](https://docs.docker.com/docker-for-windows/install/)

## Start

1. Clone this repository
2. Run `docker-compose up -d`
3. Open browser to [http://localhost:8080](http://localhost:8080)
4. Init connections
   - docker-compose exec webserver /bin/sh ./certs/connections
5. Airflow command with `docker-compose`
   - docker-compose exec webserver airflow list_dags
   - docker-compose exec webserver airflow list_tasks adam
   - docker-compose exec webserver airflow test adam apple 20190618
6. Print logs
   - docker-compose logs webserver

## Stop

```
docker-compose stop
```

## Remove docker-compose processes

```
docker-compose down
```

## Access docker process with bash

docker exec -i -t \$(docker ps -ql) /bin/bash

## To do

[] Add initial steps for connections in [entrypoint.sh](https://github.com/puckel/docker-airflow/blob/master/script/entrypoint.sh)
