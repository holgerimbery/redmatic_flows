# Auswertung von Amazon Dashbuttons mit Redmatic Boardmitteln
### die Dashbuttons müssen eingerichtet sein und in der Firewall geblockt werden, sonst lösen sie Bestellungen bei amazon aus

## Erstellung eins sub-flows "Dashbutton auswerten"


![flow](https://github.com/holgerimbery/redmatic_flows/raw/master/dashbutton_auswerten/pictures/subflow.png)

* zuerst den [subflow](https://raw.githubusercontent.com/holgerimbery/redmatic_flows/master/dashbutton_auswerten/subflow_dashbutton_auswerten.flow) importieren und 
* anschliessend im "switch node" die mac-Adressen (ohne "-" oder ":" ) der registrierten Dashbuttons einfügen

* ggf. weitere Ausgänge im "switch"- node anlegen und die "outputs" im sub-flow entsprechen erhöhen
![](https://github.com/holgerimbery/redmatic_flows/raw/master/dashbutton_auswerten/pictures/add_output_1.png)
![](https://github.com/holgerimbery/redmatic_flows/raw/master/dashbutton_auswerten/pictures/add_output_2.png)

# Nutzung des sub-flows "Dashbutton auswerten"

* den "sub-flow" in einen beliebigen flow ziehen und die "outputs" mit Aktionen versehen, die beim Drücken eines Buttons ablaufen sollen. 
Siehe Beispielscreenshot (hier Schaltstati invertieren)
![beispielflow](https://github.com/holgerimbery/redmatic_flows/raw/master/dashbutton_auswerten/pictures/dashbutton_beispiel.png)










