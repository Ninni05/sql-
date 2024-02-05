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

Q 5: Find the county with the highest number of all other personnel (full-time and part-time combined).
```sql
SELECT
  h.county_name
FROM
  `bigquery-public-data.covid19_aha.staffing` s
JOIN
  `bigquery-public-data.covid19_aha.hospital_beds` h
ON
  s.county_fips_code = h.county_fips_code
ORDER BY
  s.all_other_personnel_ft + s.all_other_personnel_pt DESC
LIMIT
  1;
```
![Screenshot 2024-02-05 100906](https://github.com/Ninni05/sql-/assets/158822578/81c75060-b391-4715-a7b0-4da503736d85)

Q 6: Finding the county name and state name where the total number of registered nurses (full-time equivalent) is greater than the total number of respiratory therapists (full-time equivalent).
```sql
SELECT
  hb.county_name,
  hb.state_name
FROM
  `bigquery-public-data.covid19_aha.staffing` hb
INNER JOIN
  `bigquery-public-data.covid19_aha.staffing` s
ON
  hb.county_name = s.county_name
WHERE
  s.registered_nurses_ft > s.respiratory_therapists_ft;
```
![Screenshot 2024-02-05 111225](https://github.com/Ninni05/sql-/assets/158822578/c61e7558-36f6-46c0-9134-fbd4d89cc39d)

Q 7: 

Q 8: Finding the county with the highest number of skilled nursing care beds.
```sql
SELECT
  h.county_name
FROM
  `bigquery-public-data.covid19_aha.hospital_beds`h
ORDER BY
  h.skilled_nursing_care_beds DESC
LIMIT
  1;
```
![Screenshot 2024-02-05 112704](https://github.com/Ninni05/sql-/assets/158822578/a479688c-b9c8-4793-8a9e-0d0959aa875b)

Q 9:Finding the country with highest number of psychiatric beds and total number of laboratory technicians.
```sql
SELECT
  h.county_name,
  h.state_name,
  h.psychiatric_care_beds,
  s.laboratory_technicians_ft
FROM
  `bigquery-public-data.covid19_aha.hospital_beds`h
INNER JOIN
  `bigquery-public-data.covid19_aha.staffing`s
ON
  h.county_name = s.county_name
ORDER BY
  h.psychiatric_care_beds DESC
LIMIT
  1;
```
![Screenshot 2024-02-05 115711](https://github.com/Ninni05/sql-/assets/158822578/5c2aabce-e9df-493f-9d4e-c38fefc5d605)


Q 10: Finding the state with the highest number of physicians and dentists (full-time equivalent).
```sql
SELECT
  state_name,
  MAX(physicians_and_dentists_ft) AS max_phys_dent_ft
FROM
  `bigquery-public-data.covid19_aha.staffing`
GROUP BY
  state_name
ORDER BY
  max_phys_dent_ft DESC
LIMIT
  1;
```
![Screenshot 2024-02-05 114841](https://github.com/Ninni05/sql-/assets/158822578/d2dc4587-90ae-4d16-a04e-4bc105ce3091)





