---
description: >-
  GridGain 9.0.16 is a stability release that standardizes system view column
  names, adds the INDEX_COLUMNS system view, and updates DCR command syntax.
hidden: true
---

# GridGain 9.0.16 Release Notes

## Overview

GridGain 9.0.16 is a stability release that is dedicated to improving user experience and fixing usability issues.

## Major Changes

### DCR Syntax Changes

With this release, all [Data Center Replication](https://app.gitbook.com/s/BfPLkyMnD0BAfMCRhZKr/gridgain9-management/data-center-replication/configuring-replication) commands are updated to consistently use the `--name` parameter to specify the replication name. Previous behavior is temporarily supported for backwards compatibility, but is deprecated and will be removed at some point later.

### Standardized System Views

Prior to this release, different system views could have slightly different names for similar columns. This release includes an extensive update for column naming scheme across system views, making system view columns more consistent.

Old system view names remain temporarily available for backwards compatibility, but are deprecated and will be removed at some point later.

Refer to the [System Views](https://app.gitbook.com/s/BfPLkyMnD0BAfMCRhZKr/reference/monitoring/system-views) documentation for current system views. The [System View Changes in GridGain 9.0.16](release-notes_9.0.16.md#system-view-changes-in-gridgain-9.0.16) section provides information on system view changes in this release.

## New Features

### New INDEX\_COLUMNS System View

A new INDEX\_COLUMNS system view allows for quick access to information about all index columns across the cluster.

## Improvements and Fixed Issues

| Issue ID  | Category                            | Description                                                                            |
| --------- | ----------------------------------- | -------------------------------------------------------------------------------------- |
| IGN-27054 | SQL                                 | Fixed incorrect type coercion for quantify operators.                                  |
| IGN-27046 | SQL                                 | Fixed an issue that caused SQL ORDER BY command to return unsorted results.            |
| IGN-27018 | General                             | Improves logging in cases of CMG disaster recovery.                                    |
| IGN-26982 | SQL                                 | Fixed an issue that caused sql queries to hang when using MergeJoin\[type=RIGHT].      |
| IGN-26961 | General                             | Fixed an issue that could cause a negative error code.                                 |
| IGN-26906 | SQL                                 | Improved consistency of execution for single-statement scripts.                        |
| IGN-26897 | SQL                                 | Names of similar columns in system views are now more consistent.                      |
| IGN-26848 | Platforms and Clients               | Improved logging of client connections.                                                |
| IGN-26797 | SQL                                 | Improved error message that is sent when attempting to use unsupported SQL statements. |
| IGN-26643 | SQL                                 | Added a new INDEX\_COLUMNS system view.                                                |
| IGN-26493 | SQL                                 | VARBINARY and VARCHAR types now support up to 2147483648 precision.                    |
| GG-42391  | Cluster Data Snapshots and Recovery | Fixed an issue that prevented snapshot restoration after data rebalancing.             |
| GG-42230  | Platforms & Clients                 | You can now use python DB API client from pip.                                         |
| GG-42224  | CLI Tool                            | All DCR commands now use --name parameter to specify replication name.                 |
| GG-42117  | General                             | Default user in Docker images in now not root.                                         |

## Known Limitations

### Data Restoration After Data Rebalance

Currently, data rebalance may cause partition distribution to change and cause issues with snapshots and data recovery. In particular:

* It is currently not possible to restore a `LOCAL` snapshot if data rebalance happened after snapshot creation. This will be addressed in one of the upcoming releases.
* It is currently not possible to perform point-in-time recovery if data rebalance happened after table creation. This will be addressed in one of the upcoming releases.

### Data Center Replication with Multiple Data Centers

Complex Data Center Replication topologies (for example, the ones involving cycles) of 3 or more data centers are not supported. This will be addressed in an upcoming releases.

### GridGain 8 Features

The following features of GridGain 8 are not available in this version, and will be added in upcoming versions:

* Rack-Awareness
* Tracing
* Service Grid

### SQL Performance in Complex Scenarios

There are known issues with the performance of SQL read-write transactions in complex read-write scenarios. These issues will be addressed in an upcoming releases.

## Installation and Upgrade Information

### System View Changes in GridGain 9.0.16

In GridGain 9.0.16 we made a polishing pass on naming of system view columns. A large number of columns were renamed to improve clarity and consistency across all system views. Old column names are temporarily available for backwards compatibility, but are deprecated and will be removed in a later release.

The table below includes the changes you need to do to continue using system views:

| System View               | Old Name               | New Name                    |
| ------------------------- | ---------------------- | --------------------------- |
| COMPUTE\_TASKS            | ID                     | COMPUTE\_TASK\_ID           |
| COMPUTE\_TASKS            | STATUS                 | COMPUTE\_TASK\_STATUS       |
| COMPUTE\_TASKS            | CREATE\_TIME           | COMPUTE\_TASK\_CREATE\_TIME |
| COMPUTE\_TASKS            | START\_TIME            | COMPUTE\_TASK\_START\_TIME  |
| COMPUTE\_TASKS            | FINISH\_TIME           | COMPUTE\_TASK\_FINISH\_TIME |
| GLOBAL\_PARTITION\_STATES | STATE                  | PARTITION\_STATE            |
| INDEXES                   | TYPE                   | INDEX\_TYPE                 |
| INDEXES                   | IS\_UNIQUE             | IS\_UNIQUE\_INDEX           |
| INDEXES                   | COLUMNS                | INDEX\_COLUMNS              |
| INDEXES                   | STATUS                 | INDEX\_STATE                |
| LICENSES                  | ID                     | LICENSE\_ID                 |
| LICENSES                  | EDITION                | LICENSE\_EDITION            |
| LICENSES                  | INFOS                  | LICENSE\_COMMON\_INFO       |
| LICENSES                  | LIMITS                 | LICENSE\_LIMITS             |
| LICENSES                  | FEATURES               | LICENSE\_FEATURES           |
| LOCKS                     | TRANSACTION\_ID        | TX\_ID                      |
| LOCKS                     | LOCK\_MODE             | MODE                        |
| SEQUENCES                 | ID                     | SEQUENCE\_ID                |
| SEQUENCES                 | NAME                   | SEQUENCE\_NAME              |
| SEQUENCES                 | DATA\_TYPE             | SEQUENCE\_DATA\_TYPE        |
| SEQUENCES                 | INCREMENT              | SEQUENCE\_INCREMENT         |
| SEQUENCES                 | MINIMUM\_VALUE         | SEQUENCE\_MINIMUM\_VALUE    |
| SEQUENCES                 | MAXIMUM\_VALUE         | SEQUENCE\_MAXIMUM\_VALUE    |
| SEQUENCES                 | START\_VALUE           | SEQUENCE\_START\_VALUE      |
| SEQUENCES                 | CACHE\_VALUE           | SEQUENCE\_CACHE\_VALUE      |
| SQL\_QUERIES              | ID                     | QUERY\_ID                   |
| SQL\_QUERIES              | PHASE                  | QUERY\_PHASE                |
| SQL\_QUERIES              | TYPE                   | QUERY\_TYPE                 |
| SQL\_QUERIES              | SCHEMA                 | QUERY\_DEFAULT\_SCHEMA      |
| SQL\_QUERIES              | START\_TIME            | QUERY\_START\_TIME          |
| SQL\_QUERIES              | PARENT\_ID             | PARENT\_QUERY\_ID           |
| SQL\_QUERIES              | STATEMENT\_NUM         | QUERY\_STATEMENT\_ORDINAL   |
| SYSTEM\_VIEWS             | ID                     | VIEW\_ID                    |
| SYSTEM\_VIEWS             | SCHEMA                 | SCHEMA\_NAME                |
| SYSTEM\_VIEWS             | NAME                   | VIEW\_NAME                  |
| SYSTEM\_VIEWS             | TYPE                   | VIEW\_TYPE                  |
| SYSTEM\_VIEW\_COLUMNS     | NAME                   | VIEW\_NAME                  |
| SYSTEM\_VIEW\_COLUMNS     | TYPE                   | COLUMN\_TYPE                |
| SYSTEM\_VIEW\_COLUMNS     | NULLABLE               | IS\_NULLABLE\_COLUMN        |
| SYSTEM\_VIEW\_COLUMNS     | PRECISION              | COLUMN\_PRECISION           |
| SYSTEM\_VIEW\_COLUMNS     | SCALE                  | COLUMN\_SCALE               |
| SYSTEM\_VIEW\_COLUMNS     | LENGTH                 | COLUMN\_LENGTH              |
| TABLES                    | SCHEMA                 | SCHEMA\_NAME                |
| TABLES                    | NAME                   | TABLE\_NAME                 |
| TABLES                    | ID                     | TABLE\_ID                   |
| TABLES                    | PK\_INDEX\_ID          | TABLE\_PK\_INDEX\_ID        |
| TABLES                    | COLOCATION\_KEY\_INDEX | TABLE\_COLOCATION\_COLUMNS  |
| TABLES                    | ZONE                   | ZONE\_NAME                  |
| TABLE\_COLUMNS            | SCHEMA                 | SCHEMA\_NAME                |
| TABLE\_COLUMNS            | TYPE                   | COLUMN\_TYPE                |
| TABLE\_COLUMNS            | NULLABLE               | IS\_NULLABLE\_COLUMN        |
| TABLE\_COLUMNS            | PREC                   | COLUMN\_PRECISION           |
| TABLE\_COLUMNS            | SCALE                  | COLUMN\_SCALE               |
| TABLE\_COLUMNS            | LENGTH                 | COLUMN\_LENGTH              |
| TRANSACTIONS              | COORDINATOR\_NODE      | COORDINATOR\_NODE\_ID       |
| TRANSACTIONS              | STATE                  | TRANSACTION\_STATE          |
| TRANSACTIONS              | ID                     | TRANSACTION\_ID             |
| TRANSACTIONS              | START\_TIME            | TRANSACTION\_START\_TIME    |
| TRANSACTIONS              | TYPE                   | TRANSACTION\_TYPE           |
| TRANSACTIONS              | PRIORITY               | TRANSACTION\_PRIORITY       |
| ZONES                     | NAME                   | ZONE\_NAME                  |
| ZONES                     | PARTITIONS             | ZONE\_PARTITIONS            |
| ZONES                     | REPLICAS               | ZONE\_REPLICAS              |
| ZONES                     | CONSISTENCY\_MODE      | ZONE\_CONSISTENCY\_MODE     |

## We Value Your Feedback

Your comments and suggestions are always welcome. You can reach us here: http://support.gridgain.com/.
