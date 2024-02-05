# sql-
Q 1: Find the county with the highest number of medical-surgical pediatric beds.
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

Q 2: Determine the total number of personnel in each state.
```sql
SELECT
  state_name,
  SUM(total_personnel_ft + total_personnel_pt) AS total_personnel
FROM
  `bigquery-public-data.covid19_aha.staffing`
GROUP BY
  state_name;
```
![Screenshot 2024-02-05 094146](https://github.com/Ninni05/sql-/assets/158822578/13a36185-8940-4d5c-8bd3-0fb8d9547321)

Q 3: Calculate the average number of other intensive care unit beds per county.
```sql
  SELECT
  AVG(other_intensive_care_beds) AS avg_other_icu_beds
FROM
  `bigquery-public-data.covid19_aha.hospital_beds`
```

![Screenshot 2024-02-05 094523](https://github.com/Ninni05/sql-/assets/158822578/4b4093f6-c9ef-4087-8f5c-7661c4342a5c)

Q 4: Find the total number of hospital beds available in each state.
```sql
SELECT
  state_name,
  SUM(total_hospital_beds) AS total_beds
FROM
  `bigquery-public-data.covid19_aha.hospital_beds`
GROUP BY
  state_name;
```
![Screenshot 2024-02-05 100244](https://github.com/Ninni05/sql-/assets/158822578/34373099-5fec-47e7-974f-4be7695acca7)


