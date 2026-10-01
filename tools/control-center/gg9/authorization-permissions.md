---
description: >-
  Cluster permissions required for Control Center actions on secured GridGain 9
  clusters — queries, code deployment, tables, and snapshots.
hidden: true
---

# Authorization and Permissions

You need an authorization to access the secured GridGain clusters via GridGain Control Center.

When you attempt to initiate a permission-protected action on a secured GridGain cluster, you are prompted to enter the cluster-specific username and password.

![](../../.gitbook/assets/cc-gg8-secured-cluster-auth.png)

GridGain Control Center supports the following permissions.

## Queries Actions

To work with [queries](querying-gg9.md) some of the following permissions are required:

| Action                               | Permission          |
| ------------------------------------ | ------------------- |
| Use the `CREATE TABLE` SQL statement | CREATE\_TABLE       |
| Use the `SELECT` SQL statement       | SELECT\_FROM\_TABLE |
| Use the `DROP TABLE` SQL statement   | DROP\_TABLE         |
| Use the `INSERT` SQL statement       | INSERT\_INTO\_TABLE |
| Use the `ALTER TABLE` SQL statement  | ALTER\_TABLE        |
| Use the `DELETE` SQL statement       | DELETE\_FROM\_TABLE |
| Use the `UPDATE SQL` statement       | UPDATE\_TABLE       |
| Use the `CREATE INDEX` SQL statement | CREATE\_INDEX       |
| Use the `DROP INDEX SQL` statement   | DROP\_INDEX         |
| Use the index in SQL statements      | USE\_INDEX          |

To get status of [Running Queries](querying-gg9.md#queries-log) and stop them the following permissions are required:

| Action                        | Permission             |
| ----------------------------- | ---------------------- |
| Get status of running queries | GET\_SQL\_QUERY\_STATE |
| Stop running queries          | KILL\_SQL\_QUERY       |

To be able to create,alter and drop Distribution Zone the following permissions are required:

| Action                        | Permission                 |
| ----------------------------- | -------------------------- |
| Create new distribution zones | CREATE\_DISTRIBUTION\_ZONE |
| Alter distribution zones      | ALTER\_DISTRIBUTION\_ZONE  |
| Delete distribution zones     | DROP\_DISTRIBUTION\_ZONE   |

You can find list of the Distribution Zones on [Tables page](tables.md)

## Code Deployment Actions

Deploy and Remove [Code Deployment Unit](deployment/code-deployment-gg9.md) actions require the following permissions:

| Action                      | Permission     |
| --------------------------- | -------------- |
| Deploy code deployment unit | DEPLOY\_UNIT   |
| Remove deployment unit      | UNDEPLOY\_UNIT |

## Tables actions

Restart and Reset partition actions require the following permissions:

| Action            | Permission          |
| ----------------- | ------------------- |
| Reset partition   | RESET\_PARTITIONS   |
| Restart partition | RESTART\_PARTITIONS |

## Snapshot Actions

The [snapshot](snapshots/snapshots-gg9.md) actions require the following permissions:

| Action           | Permission        |
| ---------------- | ----------------- |
| Create snapshot  | CREATE\_SNAPSHOT  |
| Remove snapshot  | DELETE\_SNAPSHOT  |
| Restore snapshot | RESTORE\_SNAPSHOT |
