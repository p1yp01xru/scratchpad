# Parquet Notes

- Use `snappy` compression for interactive jobs; `zstd` for storage savings.
- Row group size: aim for 512 MB–1 GB for large scans.
- Clustering columns on partitioned Hive tables can reduce metadata overhead.
- Watch out for nested `list`/`map` schemas: they can explode memory in pandas.
- `pyarrow.parquet.write_to_dataset` with `partition_cols` is handy for quick pipelines.
