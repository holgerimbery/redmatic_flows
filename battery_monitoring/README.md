## Monitoring der Batteriespannung von Aktoren (hier: HM-CC-RT-DN)
#### Diese Anleitung setzt eine "InfluxDB" & ein funktionierendes "grafana" voraus. Ein docker-compose File mit armhf kompatiblen images [liegt bei](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/grafana_stack.yml). Hiermit kann auf einem 2ten RaspberryPi mittels Docker mosquitto, grafana, chronograf, telegraf, kapacitor und influxdb gestartet werden


![grafana](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/pictures/graphana_battery_heating.PNG)
![flow](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/pictures/flow_battery_heating.PNG)

## Monitoring flow erstellen
* "rpc event node" konfigurieren
![rpc_event_node](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/pictures/rpc_event_node_battery_heating.png)

* "function node" konfigurieren
![function_node](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/pictures/function_node_battery_heating.png)
der function node schreibt den Namen des zu monitorenden Device mit der prefix battery_ in msg.measurement, somit kann der "influxdb out node" universell eingesetzt werden (ohne manuelle Konfiguration vom Measurement)

```
msg = {"measurement" : "battery_" + msg.topic,
       "topic" : msg.topic,
       "payload" : msg.payload};
return msg;
```

* "influxdb out node" konfigurieren, vorher über "manage palette" installieren
![influxdb_out](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/pictures/influxdb_out_node_battery_heating.png)
Datenbank konfigurieren

## grafana konfigurieren
* dashboards in grafana anlegen

* ggf. alert, alert notification, sowie alert notification channel (hier pushover) anlegen, damit bei zu niedrigen Batteriespannung eine Pushnachricht ausgelöst wird
![alert](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/pictures/graphana_alert_battery_heating.png)
![alert_notification_channel](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/pictures/graphana_notification_channel.png)
![alert_nofification](https://github.com/holgerimbery/redmatic_flows/raw/master/battery_monitoring/pictures/graphana_alert_notification_battery_heating.png)
