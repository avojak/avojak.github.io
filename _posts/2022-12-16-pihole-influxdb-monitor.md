---
title:  "Pi-hole InfluxDB Monitor"
description: "Export Pi-hole statistics to InfluxDB 2.x"
author: avojak
image: https://s3.amazonaws.com/avojak.com/2022-12-15-pihole-influxdb-monitor/dashboard.png
tags:
  - Docker
  - InfluxDB
  - Grafana
  - evergreen
---

# Easily monitor one or more Pi-hole instances

Monitor your Pi-holes and export statistics to InfluxDB 2.x.

```bash
docker run -d \
    -e PIHOLE_ALIAS="pihole" \
    -e PIHOLE_ADDRESS="http://pi.hole" \
    -e PIHOLE_TOKEN="pihole_api_token" \
    -e INFLUXDB_ADDRESS="http://influxdb:8086" \
    -e INFLUXDB_ORG="my-org" \
    -e INFLUXDB_TOKEN="super_secret_token" \
    -e INFLUXDB_BUCKET="pihole" \
    avojak/pihole-influxdb:latest
```

Then display all the metrics in a Grafana dashboard:

<figure class="constrained" markdown=1>
![Grafana dashboard](https://s3.amazonaws.com/avojak.com/2022-12-15-pihole-influxdb-monitor/dashboard-full.png)
</figure>

Check out the full source over on my GitHub:

{% include github-card.html
  user="avojak"
  repository="pihole-influxdb-monitor"
%}