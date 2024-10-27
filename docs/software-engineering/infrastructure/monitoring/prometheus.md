---
sidebar_position: 1
---

# Prometheus

[Prometheus](https://prometheus.io/) is an open source system monitoring and alerting product.

## How it works

Prometheus is a time series database which can be used to store metric data for analysis, monitoring, and alerting. In order to be used, you need to create metrics with a unique key and type, and then set data to it at continuous time intervals.

In order to use Prometheus, two parts are needed.

1. A Prometheus server running on the network.
2. One or more targets of prometheus metric data. This data could come from a node service, or a plain text file.

## Exporters

[Exporters](https://prometheus.io/docs/instrumenting/exporters/) are used to get data from existing software into the Prometheus metric format so it can be consumed by the Prometheus server. For example the [RabbitMQ exporter](https://github.com/apache/rocketmq-exporter) to get queue information.

## Metrics

Possible metric types are defined on the [documentation website](https://prometheus.io/docs/concepts/metric_types/).

## What to do with metric data

Once you have a prometheus server which is collecting metrics on a regular basis, it can be connected to someting like [Kibana](kibana) to visualize the metrics and create dashboards.

## How to's

### Monitoring cron jobs with prometheus

https://janikvonrotz.ch/2020/09/07/monitor-cron-jobs-with-prometheus-grafana-and-node-exporter/
