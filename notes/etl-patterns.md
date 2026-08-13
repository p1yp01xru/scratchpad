# ETL Patterns

Quick reference for common data pipeline shapes.

- **Full load**: Truncate and reload. Simple, fine for small tables.
- **Incremental by timestamp**: Keep `updated_at` column, filter on last run.
- **CDC via log**: Use database replication slots (Postgres) or binlog (MySQL).
- **Idempotency**: Design steps to be re-runnable without side effects.

## When to use what
- Small data / nightly batch → full load.
- Growing tables / streaming → timestamp or CDC.
- Always test with a sample before scaling.

## TODO
- Add pattern for handling late-arriving data.
- Note common pitfalls with timezone handling.