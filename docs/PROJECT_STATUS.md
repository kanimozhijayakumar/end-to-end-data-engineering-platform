# Project Status

This file distinguishes the implemented portfolio work from optional/advanced exercises in the reusable lab checklist.

## Implemented and validated

- Docker-based local platform scaffold
- MariaDB source and PostgreSQL warehouse connectivity
- MinIO buckets and Apache Hop MinIO connection
- `dim_date` pipeline
- `dim_product` pipeline
- SCD Type 2 `dim_customer` pipeline
- `fact_sales` pipeline
- Incremental lower watermark retrieval
- Captured source upper-bound pipeline
- Data-quality reject path
- ETL audit workflow
- Failure-safe watermark advancement
- Idempotent no-new-data rerun validation
- Raw sales extraction to MinIO (`raw/retail/sales_raw.csv`)
- Superset `dw.v_sales_detail` dataset
- Superset `control.v_etl_health` dataset
- Executive Sales dashboard
- Operations/Data Quality dashboard

## Validation evidence

- Controlled valid source record loaded to `dw.fact_sales`.
- Controlled invalid quantity record routed to `control.data_quality_rejects`.
- Failed runs did not advance the sales watermark.
- Successful run advanced `last_success_ts` to the captured source upper bound.
- Immediate rerun with no new source data created no duplicate fact or reject records.
- Raw MinIO pipeline wrote 249,419 rows successfully.

## Not claimed as complete

The following remain advanced/future exercises unless separately completed and evidenced:

- 500k-order scale test
- 1M-order scale test
- PostgreSQL `EXPLAIN (ANALYZE, BUFFERS)` tuning exercise
- Evidence-based index tuning
- Olist pipeline
- Large Parquet/MinIO exercise
- Automated CI/CD
