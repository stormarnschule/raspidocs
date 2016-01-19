+++
title = "Snake Game"
+++

# Voraussetzungen

// Gertboard tutorials ??
* [Single LED Tutorial]({{< ref "tutorial/simple_LED.md" >}})
* [LCD Display]({{< ref "">}})
//weitere refs (refs überarbeiten)

# Setup

Um ein Spiel über euren Raspberry Pi umzusetzen benötigt ihr nicht nur die Verbindung eines Displays zum Pi ([LCD Display]({{< ref "">}})), sondern auch eine Verbindung zu Eingabegeräten, in diesem Fall Buttons, die auf einem Schaltboard angebracht werden. Von den Buttons aus muss eine Verbindung zu jeweils einem  Gpio Pin geschlossen werden, über den dann der Status später abgefragt werden soll (viele Möglichkeiten des Anschlusses gilt es nicht, da die meisten Pins bereits durch das LCD Display belegt sind, in unserem Beispiel für das Programm wurden die Pins 24 und 25 benutzt). Um den Button auch tatsächlich in einen Stromkreislauf einzubauen, muss ein Kabel vom Grund zum Button und ein weiteres vom Button weg zu dem gewünschten Gpio-Pin laufen, sodass dieser mit einem Tastendruck den Kreislauf schließt und ein Potentialunterschied erfasst werden kann.

# Das Programm

Es soll ein Standart Snake Spiel, wie es früher auf Mobiltelefonen lief, über den Pi realisiert werden.
Folgende Eigenschaften und Elemente sollen enthalten sein:

* Eine Schlange mit einer bestimmten Anfangsgröße, die mittels zweier Buttons vom Spieler gesteuert werden kann und sich mit konstanter Geschwindikeit vorwärts bewegt
* Zufällig erscheinendes Futter, welches die Schlange vergrößert, wenn sie es frisst (über den Punkt läuft)
* Abbruch des Spiel, wenn die Schlange gegen sich selbst läuft
* Ein grafisch festgehaltenes Spielfeld mit einer Anzeige für den Score
// Beispielbild



# Tipps

{{< collapse "Tipp 1" >}} Geht in logischen Schritten an das Projekt. Überlegt, wie in der OOP, welche Eigenschaften die Snake eigentlich haben soll (obwohl ihr keine eigene Klasse für diese anlegen müsst). Legt darauf basiert Methoden fest, die diese Eigenschaften definieren. Des weiteren könnt ihr das gesamte Progeamm in Methoden aufteilen, die den Spielablauf wiederspiegeln. Methoden könnten sein:
* init() oder gameStart() - deklariert die Startbedingungen
* move() - beschreibt das Bewegen der Snake
* input() - setzt die Eingaben um
* draw_header() - beschreibt das Spielfeld
* render() - aktualisiert das Spiel auf dem Display
{{< /collapse >}}
{{< collapse "Tipp 2" >}} Ignoriert zunächst, dass ihr etwas grafisches programmiert. Beschreibt das Verhalten der Schlange anhand von Koordinaten, die ihr als Punkt in einem X- und einem Y-Wert (Startpunkt + konstante Änderung der Koordinaten für eine gleichförmige Bewegung). Beschreibt erstmal eine gradlinige Bewegung und kümmert euch erst später um Inputs. Dies setzt voraus, dass die Schlange nach dem passieren des rechten Bildschirmrandes wieder links eintritt.
{{< /collapse >}}

//weitere tipps, die jeden schritt vorgeben aber den code nicht beschreiben
