## Docker

-   Use the following images

## SQL

`Docker command sets up a PostgreSQL container with specific configurations and maps its ports and data volume to the host machine for persistence and easy access to the Postgres database.`

```
docker run -it \
  -e POSTGRES_USER="root" \
  -e POSTGRES_PASSWORD="root" \
  -e POSTGRES_DB="ny_taxi" \
  -v C:/Users/rsdam/Desktop/Projects/data-engineering/2_DOCKER_SQL/ny_taxi_postgres_data:/var/lib/postgresql/data \
  -p 5432:5432 \
  postgres:13
```

## Install pgcli in the host

`pgcli` is a command-line interface (CLI) tool for working with PostgreSQL databases.

-   Install pgcli via Git Bash at the project directory

    ```
    pip install pgcli
    ```

    `Note: You need to install Postgre Windows if you're using Windows`

## Test Connection to the PG Database

-   Execute the following command via Git Bash at the `2_DOCKER_SQL` folder

    ```
    pgcli -h localhost -p 5432 -u root -d ny_taxi
    ```

    Error Note: If password authentication fails:

    -   Winkey + R
    -   Type services.msc
    -   Search Postgres service based on version installed.
    -   Click Restart

## Use Jupyter Notebook for Uploading Data

https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
