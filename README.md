# sql-

```sql
SELECT
  h.county_name
FROM
  `bigquery-public-data.covid19_aha.hospital_beds`h
ORDER BY
  h.gen_medical_surgical_pediatric_beds DESC
LIMIT
  1;
```
![q1](https://github.com/Ninni05/sql-/assets/158822578/04dcb32c-7c55-4c2b-8846-6e47b5f774ba)
