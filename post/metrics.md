+++
title= "Metrics"
date= 2019-10-03T23:13:07+02:00
tags= ["metrics", "grafana", "telegraf"]
description="grafana, telegraf"
+++

# InfluxDB line protocol

The output of **s3mon** is the [InfluxDB line protocol](https://docs.influxdata.com/influxdb/v1.7/write_protocols/line_protocol_tutorial/), for example:

    $ s3mon -c config.yml
    s3mon,bucket=backup,prefix=backup error=0i,exist=1i,size_mismatch=1i
    s3mon,bucket=random,prefix=abc error=0i,exist=1i,size_mismatch=0i
    s3mon,bucket=foo,prefix=bar error=0i,exist=1i,size_mismatch=0i
    s3mon,bucket=test,prefix=backup error=0i,exist=0i,size_mismatch=0i
    s3mon,bucket=images,prefix=img error=0i,exist=1i,size_mismatch=0i

# telegraf

**s3mon** could be called periodically from telegraf using this configuration:

    [[inputs.exec]]
      command = "/path/to/s3mon -c /path/to/config.yml"
      interval = "1h"
      data_format = "influx"

# grafana

You could use this dashboard and configure custom alerts: https://grafana.com/grafana/dashboards/11008

![grafana](/img/grafana.png)
