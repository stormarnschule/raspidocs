+++
title = "GPIO - Lichtorgel"
hasexamplecode = true
+++

# Voraussetzungen

* [Gertboard Grundwissen]({{< ref "tutorial/gertboard.md" >}})

# Setup

Nun zum ersten Tutorial mit dem Gertboard. Deine Aufgabe ist es nun die
eingebaute LED-Reihe in eine Lichtorgel zu verwandeln. Da bei der Lichtorgel
alle LEDs angesteuert werden sollen und diese eine Ausgabe des Pi bzw. des
Gertbords ist, müssen alle Buffer auf dem Gertboard ebenfalls als output
gesetzt sein. Dies betrifft als output Buffer B1 – B12 (siehe Gertboardgrafik).  

Habt ihr die Buffer richtig definiert, kann erstmal gar nichts passieren. Es
gibt keine leitende Verbindung zwischen dem funktionellem Block der Buffer und
dem Pi. Diese Verbindung muss nun geschaffen werden. Hierzu müssen die GP Pins
mit den Buffer Pins verbunden werden.  
Um die LED wie gewünscht ansteuern zu können sind die GP25–GP17 mit den Buffern
B1-B7 zu verbinden und GP11-GP7 mit B8-B12. GP15 und GP 14 werden ausgelassen,
da diese eine andere Funktion abdecken, die zu diesem Zeitpunkt nicht benötigt
wird. Nach dem verkabeln des Gertboards sollte dieses aussehen wie auf der
Grafik und den Bildern unten auf der Seite.

{{< figure src="/raspidocs/img/Gertboardgrafik.png" title="Gertboard Schema" >}}
{{< figure src="/raspidocs/img/GertboardBild1.png" title="Gertboard GPIO Header" >}}
{{< figure src="/raspidocs/img/GertboardBild2.png" title="Gertboard Übersicht" >}}


# Das Programm

Nun haben wir bereits die “Hardware”-Vorraussetzungen für unsere Lichtorgel
geschaffen. Wichtig ist, dass ihr die GPIO-Steuerung in euer Programm
inkludiert:

```c
#include <gpio.h>
```
Kommen wir nun zum Code, der die Lichtorgel
antreibt. Wichtig ist, dass die Api (gpio.h), also die Schnittstelle
eingebunden ist, die den Zugriff auf das Gertboard ermöglicht. Diese hält
Methoden bereit, die ihr nun nutzen könnt um die LEDs auf dem Board an und aus
zu schalten.

Euer Programm soll die LEDs auf dem Gerdboard der Reihe nach aufleuchten lassen.
Nachdem eine Richtung komplett durchlaufen wurde, soll dies erneut in die
andere Richtung geschehen. So entsteht eine nicht aufhörende Kette von
aufleutenden Lampen.

# Tipps

{{< collapse "Tipp 1" >}}
Zuerst muss eine Liste von gpio Pins erstellt werden. Diese sollte alle Pins enthalten die in Verbindung mit den LEDs stehen und diese als Output Pins deklarieren.
{{< /collapse >}}

{{< collapse "Tipp 2" >}}
Um das aufleuchten der Lampen zu einer Lichtorgel zu verbinden benötigt ihr 3 Schleifen.
Davon dient zwei nur zum Aufleuchten einer Reihe in jeweils verschiedene Richtungen. Die dritte dient dazu, dass dieser Vorgang wieder von vorne beginnt.
{{< /collapse >}}

{{< collapse "Tipp 3" >}}
Funktionen die genutzt werden sollten sind: begin(), end(), state(), delay().
{{< /collapse >}}

{{< collapse "Tipp 4" >}}
Mit der Funktion state() kann sowohl ein Wert abgefragt, mit der set_state(bool) übergegen werden.
{{< /collapse >}}
