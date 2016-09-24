# A Dockerized Prometheus Image for Raspberry Pi 2/3

Prometheus is a systems and service monitoring system. It collects metrics from configured targets at given intervals, evaluates rule expressions, displays the results, and can trigger alerts if some condition is observed to be true.

In case you are Raspberry Pi user and want to try it, check this out !

Features
-------------

Prometheus's main features are:

   -  a multi-dimensional data model (time series identified by metric name and key/value pairs)
   - a flexible query language to leverage this dimensionality
   - no reliance on distributed storage; single server nodes are autonomous
   - time series collection happens via a pull model over HTTP
   - pushing time series is supported via an intermediary gateway
   - targets are discovered via service discovery or static configuration
   - multiple modes of graphing and dashboarding support

To learn more, refer : https://prometheus.io/docs/introduction/overview/

Tested Platform
--------------------

Raspberry Pi 2/3


How to run this Docker Image?
----------------------------------------

```sh
$ docker build -t prometheus-armv7 .
$ docker run -d --net=host -v `pwd`/prometheus.yml:/etc/prometheus/prometheus.yml prometheus-armv7
```

Changelog
---------------

* Removed golden binaries
* Added curl to fetch prometheus
* Fixed README file instructions

[Alex Ellis](https://twitter.com/alexellisuk/)
