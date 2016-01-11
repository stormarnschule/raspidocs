+++
date = "2015-10-26T11:50:32+01:00"
title = "GPIO - Taster"
hasexamplecode = true
+++

# Vorrausetzungen

* [Gertboard Grundwissen]({{< ref "tutorial/gertboard.md" >}})

# Setup

Da in diesem Turorial zum ersten Mal die Taster auf dem Gertboard eingebunden
werden sollen und diese eine Eingabe darstellen werden, muss die Verkabelung
der Pins erneut verändert werden.  
Auf die Output Pins B1-B3 müssen Jumper gesetzt werden. Dies ermöglicht eine
Ausgabe des Gertboardboard ausgelöst durch die Taster. Außerdem müssen die GPIO
Pins 25 mit B1, 24 mit B2 und 23 mit B1 verbunden werden.

# Das Programm

Euer Programm soll nun den Status der Buttons anzeigen. Hierbei sollt ihr alle
drei Buttons einbinden und eine Ausgabe formulieren, über die dem Nutzer
mitgeteilt wird, ob ein Button gedrückt ist oder nicht.

# Tipps

{{< collapse "Tipp 1" >}}
Es muss eine Liste der Pins angelegt werden, über die die Buttons angesteuert werden, bzw. über die deren Signal geleitet wird. Diese soll gleichzeitig die Pins als button_pin deklarieren. Ihr erstellt also eine Liste von den button_pins. Mit dieser Liste könnt ihr dann im folgenden arbeiten.
{{< /collapse >}}

{{< collapse "Tipp 2" >}}
Die Liste muss durchgegangen werden und von jedem Pin soll der Status ermittelt werden. Diesen könnt ihr in einer Variablen Speichern und ausgeben lassen.
{{< /collapse >}}

{{< collapse "Tipp 3" >}}
Um immer den aktuellen Status eines Buttons ermitteln, müssen sich eure Statusabfragen und Ausgaben in einer while-Schleife befinden.
{{< /collapse >}}

{{< collapse "Tipp 4" >}}
Der Übersichtlichkeit halber solltet ihr die ausgegebene Zeile zu Beginn der Schleife wieder löschen.
{{< /collapse >}}