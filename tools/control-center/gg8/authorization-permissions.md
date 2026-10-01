---
description: >-
  Cluster permissions required for Control Center actions on secured GridGain 8
  clusters — caches, queries, snapshots, compute, and more.
hidden: true
---

# Authorization and Permissions

You need an authorization to access the secured GridGain clusters via Control Center.

When you attempt to initiate a permission-protected action on a secured GridGain cluster, you are prompted to enter the cluster-specific user name and password.

![](../../.gitbook/assets/cc-gg8-secured-cluster-auth.png)

Control Center supports the following permissions.

## Baseline Actions

All [baseline topology](dashboard/my-cluster.md#viewing-cluster-health-details) actions require the ADMIN\_OPS permission.

## Binary Type Actions

The [binary type](caches/binary-types.md) actions that might affect the cluster state require the following permissions:

| Action              | Permission                          |
| ------------------- | ----------------------------------- |
| Update binary types | ADMIN\_METADATA\_OPS                |
| Remove binary type  | ADMIN\_METADATA\_OPS, TASK\_EXECUTE |

## Cache Actions

The [cache](caches/caches.md) actions that might affect the cluster state require the following permissions:

| Action                   | Permission                |
| ------------------------ | ------------------------- |
| Reset lost partitions    | ADMIN\_OPS                |
| Clear cache              | CACHE\_REMOVE             |
| Destroy cache            | CACHE\_DESTROY            |
| Rebalance caches         | ADMIN\_CACHE              |
| Load cache               | ADMIN\_OPS, TASK\_EXECUTE |
| Enable cache statistics  | ADMIN\_CACHE              |
| Disable cache statistics | ADMIN\_CACHE              |

## Cache DR Actions

All [cache DR](caches/caches.md) actions require the ADMIN\_OPS permission.

## Cluster Actions

The cluster actions require the following permissions:

| Action              | Permission                |
| ------------------- | ------------------------- |
| Activate cluster    | ADMIN\_OPS                |
| Deactivate cluster  | ADMIN\_OPS                |
| Change cluster tag  | ADMIN\_OPS                |
| Export cluster logs | ADMIN\_OPS, TASK\_EXECUTE |

## License Actions

The [upload license](../getting-started/adding-license.md) action requires the ADMIN\_OPS permission.

## Code Deployment Actions

If you using Gridgain 8, all [code deployment](code-deployment-gg8.md) actions require the ADMIN\_OPS permission.

## Compute Actions

The [compute task](compute-grid.md) actions that might affect the cluster state require the following permissions:

| Action                          | Permission   |
| ------------------------------- | ------------ |
| Cancel compute task             | TASK\_CANCEL |
| Change priority of compute task | ADMIN\_OPS   |

## Node Actions

The [node](dashboard/dashboard-overview.md) actions that might affect the cluster state require the following permissions:

| Action                     | Permission |
| -------------------------- | ---------- |
| Perform garbage collection | ADMIN\_OPS |
| Create thread dump         | ADMIN\_OPS |

## Query Actions

The [query](queries/querying.md) actions that might affect the cluster state require the following permissions:

| Action                                   | Permission                             |
| ---------------------------------------- | -------------------------------------- |
| Cancel query                             | KILL\_QUERY                            |
| Kill query                               | KILL\_QUERY                            |
| Execute SQL query                        | CACHE\_READ, CACHE\_CREATE, CACHE\_PUT |
| Execute scan query                       | CACHE\_READ                            |
| Show query history                       | GET\_QUERY\_VIEWS                      |
| Update configuration for running queries | ADMIN\_OPS                             |

## Snapshot Actions

The [snapshot](snapshots/snapshots.md) actions require the following permissions:

| Action                    | Permission                |
| ------------------------- | ------------------------- |
| Create snapshot           | ADMIN\_OPS                |
| Delete snapshot           | ADMIN\_CACHE              |
| Copy snapshot             | ADMIN\_CACHE              |
| Move snapshot             | ADMIN\_CACHE              |
| Check snapshot            | ADMIN\_OPS                |
| View snapshot list        | ADMIN\_VIEW               |
| Restore snapshot          | ADMIN\_CACHE              |
| Recover to snapshot       | ADMIN\_VIEW, ADMIN\_CACHE |
| Cancel snapshot operation | ADMIN\_OPS                |

## Snapshot Schedule Actions

The [snapshot schedule](snapshots/snapshot-schedules.md) actions require the following permissions:

| Action             | Permission  |
| ------------------ | ----------- |
| View schedule list | ADMIN\_VIEW |
| Create schedule    | ADMIN\_OPS  |
| Delete schedule    | ADMIN\_OPS  |
| Enable schedule    | ADMIN\_OPS  |
| Disable schedule   | ADMIN\_OPS  |

## Tracing Actions

The [change tracing configuration](tracing.md) action requires the TRACING\_CONFIGURATION\_UPDATE permission.
