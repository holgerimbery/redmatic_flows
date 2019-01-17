# Monitoring des Batteriespannung von Akoren (hier: HM-CC-RT-DN)
#### Diese Anleitung setzt eine "InfluxDB" & ein funktionierendes "grafana" voraus, ein docker-compose File mit armhf kompatiblen images liegt in diesem repository. Hiermit kann auf einem 2ten Raspberry mittels Docker mosquitto, grafana, chronograf, telegraf, kapacitor und influxdb gestartet werden 

## Monitoring flow erstellen
[grafana]()
[flow]()
* rpc event node konfigurieren
[rpc_event_node]()
* function node konfigurieren
[function_node]()
der function node schreibt die das zu monitorende Device mit der prefix battery_ in msg.measurement, damit der der influxdb out node universell eingesetzt werden kann (ohne manuelle Konfiguration vom Measurement)
* influxdb out node konfigurieren
[influxdb_out]()
Datenbank konfigurieren

## grafana konfigurieren
* dashboards in grafana anlegen
* ggf. alert, alert notification, sowie alert notification channel (hier pushover) anlegen, bei zu niedrigen Batteriespannung wird dann eine Pushnachricht ausgelöst
[alert]()
[alert_nofification]()
[alert_notification_channel]()
