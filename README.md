# Knock Case Study
## Workflow
#### 1. Clear staging area
Have a clean staging table every ETL execution.
#### 2. Initial load and append
Load data from `the_source.fake_appointments` into a Pandas Dataframe. 
Load data from `the_source.data_to_append` into a Pandas Dataframe.
Merge the 2 Dataframes and write into the `home_tests.appointments_stg`. 
#### 3. Merge stg data
Load data from `the_source.data_to_upsert`  into a dataframe. Merge with the previous staging table.

#### 4. Merge final table
Merge the staging table with the final `home_test.fact_appointments` table .

## Transformations

### Table *the_source.fake_appointments*

| Column  | Transformation |
| ------------- |:-------------:|
| created_at | Convert String > Timestamp |
| updated_at | Convert String > Timestamp |
| finished_at | Convert String > Timestamp |
| start_time | Convert String > Timestamp |
| end_time | Convert String > Timestamp |
| started_at | Convert String > Timestamp |
| project_id | Convert String > Integer AND Replace 'None' with -9999 |
| project_enrollment_event_id | Convert String > Integer AND Replace 'None' with -9999 |

### Table *the_source.data_to_append*
| Column  | Transformation |
| ------------- |:-------------:|
| created_at | Convert String > Timestamp |
| updated_at | Convert String > Timestamp |
| finished_at | Convert String > Timestamp |
| start_time | Convert String > Timestamp |
| end_time | Convert String > Timestamp |
| started_at | Convert String > Timestamp |
| session_id | Convert String > Integer AND Replace '' with -9999 |
| project_id | Convert String > Integer AND Replace '' with -9999 |
| project_enrollment_event_id | Convert String > Integer AND Replace '' with -9999 |

### Table *the_source.data_to_upsert*
| Column  | Transformation |
| ------------- |:-------------:|
| created_at | Convert String > Timestamp |
| updated_at | Convert String > Timestamp |
| finished_at | Convert String > Timestamp |
| start_time | Convert String > Timestamp |
| end_time | Convert String > Timestamp |
| started_at | Convert String > Timestamp |
| session_id | Replace NULL with -9999 |
| project_id | Convert String > Integer AND Replace '' with -9999 |
| project_enrollment_event_id | Convert String > Integer AND Replace '' with -9999 |

