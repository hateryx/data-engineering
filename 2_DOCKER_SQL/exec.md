services:
postgres:
image: postgres:13
environment:
POSTGRES_USER: airflow
POSTGRES_PASSWORD: airflow
POSTGRES_DB: airflow
volumes: - './var/lib/postgresql/data \postgres:13'
healthcheck:
test: ['CMD', 'pg_isready', '-U', 'airflow']
interval: 5s
retries: 5
restart: always

docker run -it \
 -e POSTGRES_USER="root" \
 -e POSTGRES_PASSWORD="root" \
 -e POSTGRES_DB="ny_taxi" \
 -v C:/Users/rsdam/Desktop/Projects/data-engineering/2_DOCKER_SQL/ny_taxi_postgres_data:/var/lib/postgresql/data \
 -p 5432:5432 \
 postgres:13
