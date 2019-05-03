A self contained network monitoring system
==========================================

This is a simple network monitoring system using the stack
Telegraf-Influx-Grafana.

System runs on docker containers managed by docker-composer.

Influxdb setup
==============

Using given configuration Telegraf will create its database on influxdb server.

If you need to customize influxdb this is the docker way:

```
server1$ docker run --rm \
  -e INFLUXDB_ADMIN_USER=admin \
  -e INFLUXDB_ADMIN_PASSWORD=supersecretpassword \
  -e INFLUXDB_USER=telegraf -e INFLUXDB_USER_PASSWORD=secretpassword \
  -e INFLUXDB_DB=telegraf \
  -v influxdb-vol:/var/lib/influxdb \
  influxdb /init-influxdb.sh
```

Resources
=========

* [Docker Official Images - Influxdb](https://hub.docker.com/_/influxdb)

* [Docker Official Images - Telegraf](https://hub.docker.com/_/telegraf)


Credits
======

* [Get system metrics for 5 min with Docker, Telegraf, Influxdb and Grafana](https://towardsdatascience.com/get-system-metrics-for-5-min-with-docker-telegraf-influxdb-and-grafana-97cfd957f0ac)
* [Monitoring your home network with InfluxDB on Raspberry Pi with Docker](https://medium.com/@petey5000/monitoring-your-home-network-with-influxdb-on-raspberry-pi-with-docker-78a23559ffea)
