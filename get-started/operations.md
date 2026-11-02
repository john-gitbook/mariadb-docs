---
title: Operations
description: >-
  Keep MariaDB fast, safe, and available in production. Back up and restore your
  data, run clustered and routed topologies, and measure performance.
icon: gauge-high
---

# Operations

Operations is the work that keeps a deployed database fast, recoverable, and available: backups on a schedule, a cluster and proxy you stand up once and then watch, and tuning driven by measurement. The pages below reach each of those across MariaDB Server, Galera Cluster, MaxScale, and MariaDB Cloud, so you do not need to know which space documents which procedure.

For a first production deployment, the order below is deliberate: get recoverable, get redundant, then get fast. Each stage depends on the one before it, and tuning a database whose backups are unproven optimizes the wrong risk.

**Back up and restore.** Build this routine first. The backup and restore overview covers the available tools and when each fits, from logical dumps to physical backups. Work through the quickstart to take a backup and restore it by hand, because a backup you have never restored is an untested assumption. Have this working before any real data lands.

**Stay available.** To survive node loss, replicate the data and route around the failure. Galera Cluster maintains a synchronous copy on every node, so any node can accept writes, and its use cases guide covers the topologies it suits. MaxScale sits in front, routing queries, balancing reads, and hiding failover from the application. Run them together and a single node failure stops being an outage. On MariaDB Cloud, a replicated topology gives you the same protection as a managed setting.

**Tune with numbers.** Measure before changing anything. The benchmarking guide covers putting a realistic load on the database so that a configuration change is judged against a baseline, which is the only way to tell an improvement from a regression. Measure, change one variable, measure again.

Start with a restore you have performed yourself, then add availability, then tune.

## Back Up and Restore

{% content-ref url="{server}/server-management/backing-up-and-restoring-databases/" %}
[backing-up-and-restoring-databases]({server}/server-management/backing-up-and-restoring-databases/)
{% endcontent-ref %}

{% content-ref url="{server}/mariadb-quickstart-guides/mariadb-backup-guide/" %}
[mariadb-backup-guide]({server}/mariadb-quickstart-guides/mariadb-backup-guide/)
{% endcontent-ref %}

{% content-ref url="{server}/mariadb-quickstart-guides/mariadb-restore-guide/" %}
[mariadb-restore-guide]({server}/mariadb-quickstart-guides/mariadb-restore-guide/)
{% endcontent-ref %}

## Run a Highly Available Topology

{% content-ref url="{galera}/galera-cluster-quickstart-guides/mariadb-galera-cluster-guide/" %}
[mariadb-galera-cluster-guide]({galera}/galera-cluster-quickstart-guides/mariadb-galera-cluster-guide/)
{% endcontent-ref %}

{% content-ref url="{galera}/galera-use-cases/" %}
[galera-use-cases]({galera}/galera-use-cases/)
{% endcontent-ref %}

{% content-ref url="{maxscale}/maxscale-quickstart-guides/maxscale-beginner-guide/" %}
[maxscale-beginner-guide]({maxscale}/maxscale-quickstart-guides/maxscale-beginner-guide/)
{% endcontent-ref %}

{% content-ref url="{mariadb-cloud}/high-availability-dr/ha-and-replicated-topology/" %}
[ha-and-replicated-topology]({mariadb-cloud}/high-availability-dr/ha-and-replicated-topology/)
{% endcontent-ref %}

## Tune Performance

{% content-ref url="{server}/ha-and-performance/benchmarking/" %}
[benchmarking]({server}/ha-and-performance/benchmarking/)
{% endcontent-ref %}
