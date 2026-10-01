---
title: GridGain 9
description: >-
  Install, configure, and operate GridGain 9 for existing GridGain 9
  deployments.
icon: bolt
---

# GridGain 9

GridGain 9 is an in-memory data platform documented for existing GridGain 9 deployments. It holds a distributed store across a cluster of nodes and serves data from memory, so hot reads do not reach the database of record. It is built on Apache Ignite 3.

**Install and connect.** GridGain 9 runs as a cluster your application connects to as a client. Install the nodes, initialize the cluster, then connect and confirm the cluster answers.

**Configure and secure it.** The settings that matter most govern how tables are distributed and replicated across nodes and how the cluster loads from and writes back to the database of record. Secure the cluster as you would the database, because it holds a copy of the data.

**Understand the architecture.** The concepts pages cover the cluster and storage model, how SQL is executed across nodes, and the transactional guarantees on offer, which is what tells you which read and write paths are safe to route through it.

Start from the overview to see how the cluster, SQL engine, and transaction model fit together before you change a deployment.

## Get Started

{% content-ref url="{gridgain9}/gridgain9-management/installation" %}
[Installation]({gridgain9}/gridgain9-management/installation)
{% endcontent-ref %}

{% content-ref url="{gridgain9}/gridgain9-get-started/start-cluster" %}
[Start a GridGain 9 Cluster]({gridgain9}/gridgain9-get-started/start-cluster)
{% endcontent-ref %}

## Tutorials

{% content-ref url="{gridgain9}/gridgain9-get-started/quick-start" %}
[Quick Start]({gridgain9}/gridgain9-get-started/quick-start)
{% endcontent-ref %}

## How-To Guides

{% content-ref url="{gridgain9}/reference/configuration" %}
[Configuration Parameters]({gridgain9}/reference/configuration)
{% endcontent-ref %}

{% content-ref url="{gridgain9}/security" %}
[Security]({gridgain9}/security)
{% endcontent-ref %}

## Concepts

{% content-ref url="{gridgain9}" %}
[What Is GridGain 9]({gridgain9})
{% endcontent-ref %}

{% content-ref url="{gridgain9}/architecture" %}
[Architecture]({gridgain9}/architecture)
{% endcontent-ref %}

## Reference

{% content-ref url="{gridgain9}/reference" %}
[Reference]({gridgain9}/reference)
{% endcontent-ref %}

{% content-ref url="{release-notes}/gridgain-9" %}
[GridGain 9 Release Notes]({release-notes}/gridgain-9)
{% endcontent-ref %}
