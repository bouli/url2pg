# url2pg

This repository ingests data from a CSV/Parquet url into a Postgres table
overwirting the previous table if it exists.

Usage:
```shell
python3 ingestion-data.py \
    --user=<postgres_user:default=root> \
    --password=<postgres_password:default=root> \
    --host=<postgres_host:default=localhost> \
    --port=<postgres_port:default=5432> \
    --db=<*_db> \
    --table_name=<*_destiny_table> \
    --url_file=<*_source_url>
```

You can use as a Docker image as well:
```shell
docker run -it \
    --network=<*_destiny_network> \
    cesarbouli/url2pg \
    --user=<postgres_user:default=root> \
    --password=<postgres_password:default=root> \
    --host=<postgres_host:default=localhost> \
    --port=<postgres_port:default=5432> \
    --db=<*_db> \
    --table_name=<*_destiny_table> \
    --url_file=<*_source_url>
```

In your docker compose file:
```yaml
services:
  ingestion-data:
    image: cesarbouli/url2pg
    command: --db=<_db_> (...)
    (...)
```
Docker image: [https://hub.docker.com/r/cesarbouli/url2pg](https://hub.docker.com/r/cesarbouli/url2pg) \
More information: [https://github.com/bouli/data-engineering-carreer-2025-2026](https://github.com/bouli/data-engineering-carreer-2025-2026)
