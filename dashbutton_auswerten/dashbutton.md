# Auswertung von Amazon Dashbuttons mit Redmatic Boardmitteln

## Erstellung eins sub-flows "Dashbutton auswerten"
### die dashbuttons müssen eingerichtet und in der Firewall geblockt sein, sonst lösen sie Bestellungen bei amazon aus


![flow](https://github.com/holgerimbery/redmatic_flows/raw/master/dashbutton_auswerten/pictures/subflow.png)

* zuerst den [subflow](https://raw.githubusercontent.com/holgerimbery/redmatic_flows/master/dashbutton_auswerten/subflow_dashbutton_auswerten) importieren und 
* anschliessend im "switch node" die mac-Adressen (ohne "-" oder ":" ) der registrierten Dashbuttons einfügen

* ggf. weitere Ausgänge im switchnode anlegen und outputs im supbflow entsprechen erhöhen
![](https://github.com/holgerimbery/redmatic_flows/raw/master/dashbutton_auswerten/pictures/add_output_1.png)
![](https://github.com/holgerimbery/redmatic_flows/raw/master/dashbutton_auswerten/pictures/add_output_2.png)

# Nutzung des sub-flows "Dashbutton auswerfen"

* den subflow in einen beliebigen flow ziehen und die outputs mit Aktionen versehen die beim Drücken eines Buttons ablaufen sollen. siehe Beispielscreenshot











