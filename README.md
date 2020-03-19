# InfluxDb SQL commands

## Database 

SHOW DATABASES - List of databases

CREATE DATABASE [database name] - create new database

CREATE RETENTION POLICY [retention policy name] ON "[database name]" DURATION [duration, ex. 3d, min 1 hour] REPLICATION 1 - Create a retention policy. 

DROP DATABASE "[db_name]" - Drop database

SHOW RETENTION POLICIES on [database name] - Show retention policies

SHOW MEASUREMENTS ON [database name] - Show measurements

SHOW FIELD KEYS FROM "[database name]"."[Retention Policy]"."[Measurement]" - Show fields for a measurement

## Get time series

SELECT [field names, or * to all] FROM "[database name]"."[Retention Policy]"."[Measurement]" WHERE time > [time in nanosecond, ex. 1552395358000000000] AND time < [time in nanosecond, ex. 1615553758000000000] - Get data between a time interval

SELECT * INTO "[database name]"."[Retention Policy]"."[Measurement]" from "[database name]"."[Retention Policy]"."[Measurement]" GROUP BY [field names] - Copy time series from one measurement to another

SELECT [field names, or * to all] FROM "[database name]"."[Retention Policy]"."[Measurement]" ORDER BY desc LIMIT 1 - Get the last value

SELECT [field name] FROM "[database name]"."[Retention Policy]"."[Measurement]" where time >  [time in nanosecond, ex. 1552395358000000000] ORDER BY asc LIMIT 1 - Get the first value after a timstamp



