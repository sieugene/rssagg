
## Postgres

Running docker compose

```bash
  docker-compose up -d
```

./scl/schema
goose postgres DB_URL up
goose postgres DB_URL down

sqlc generate -> sqlc.yaml
[sql/queries, sql,schema]