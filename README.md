# Knock Case Study

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


