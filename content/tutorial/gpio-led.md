+++
title = "Simple LED"
hasexamplecode = true
+++

# Voraussetzungen

* [Pi Setup/Installation]({{< ref "setup/rpi-installation.md" >}})
* [SSH Verbindung]({{< ref "setup/ssh.md" >}})


# Setup

In diesem Tutorial geht es um eine LED, die mittels des Raspberry Pi's angesteuert und zum blinken gebracht werden soll. Um dies physikalisch zu ermöglichen, muss zunächst eine Verbindung des Pi's mit der LED geschlossen werden. Hierfür benutzen wird ein Schaltboard, auf das die Led gesteckt wird. Der Pi wird nun so mit zwei Kabeln über zwei GPIO-Pins mit dem Schaltboard verbunden, dass ein Stromkreis gebildet wird. Zudem benötigen wir einen in Reihe geschalteten Widerstand, um die Stromstärke zu senken.

{{< figure src="/raspidocs/img/schaltboard_simple_led.png" title="LED Setup Schaltboard" >}}

# Setup-Check

Wenn ihr euer Schaltboard mit den aufgezählten Elementen versehen habt, könnt ihr euer Setup testen, indem ihr die Kabel die nun vom Schaltboard ausgehen mit dem Dauerstrompin(3,3v, Pin 1) des Pi's und der Erdung(Pin 25) verbindet (siehe Grafik). Achtet darauf, dass eine LED-Diode nur bei einer Stromrichtung den Stromkreislauf schließt. Kommt es daraufhin zu einem Dauerleuchten euer LED, wisst ihr, dass alle Komponenten intakt sind.

{{< figure src="/raspidocs/img/pi_simple_led.png" title="Pin Setup" >}}

# Das Programm

Nun soll die Led vom Raspberry aus gesteuert werden und nicht durchleuchten, sondern Phasenweise für jeweils 0,5s an und aus sein. Um dies überhaupt zu ermöglichen, muss noch eine kleine Änderung an eurer Hardware vorgenommen werden. Die Verbindung am Dauerstrompin muss aufgelöst werden und das Kabel muss mit an einen der GPIO-Pins verbunden werden. Wir nutzen für dieses Programm den GPIO Pin 15 (siehe Grafik). Diesen Pin könnt ihr mit dem Raspberry Pi ansteuern und an- bzw. ausschalten, also eine Spannung anlegen oder nicht anlegen.
Schreibt nun ein Programm, welches die LED 10 mal für 0,5s leuchten lässt.

# Tipps

{{< collapse "Tipp 1" >}} Die Gpio-Klasse erleichtert das Arbeiten mit den Pins erheblich. Erfindet also das Rad nicht neu und importiert diese zu Anfang (#include "gpio.h). Es ist jetzt möglich Input- und Output-Pins allein mit der Übergabe der Pinnummer zu definieren. Ihr braucht außerdem eine Hauptmethode "int main()". Diese wird bei Programmstart ausgeführt. In ihr könnt ihr die Syntax für euer Programm implementieren.  {{< /collapse >}}
{{< collapse "Tipp 2" >}} Zuerst muss der Pin 15 als Output-Pin definiert werden. Erzeugt also ein Pin-Objekt über die "output_pin" Methode in der Gpio-Klasse.   {{< /collapse >}}
{{< collapse "Tipp 3" >}} Das zehnfache aufleuchten könnt ihr mir einer for-Schleife umsetzen. {{< /collapse >}}
{{< collapse "Tipp 4" >}} Den Pin-Status kann mit der Methode "set_state" verändert werden.  {{< /collapse >}}
{{< collapse "Tipp 5" >}} Mit der Methode "delay()" wird das Programm für die Zeitdauer der übergebenden Zahl in ms pausiert. {{< /collapse >}}
