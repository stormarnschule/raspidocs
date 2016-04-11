+++
title = "Snake Game"
+++

# Voraussetzungen

* [Pi Setup/Installation]({{< ref "setup/rpi-installation.md" >}})
* [SSH Verbindung]({{< ref "setup/ssh.md" >}})
* [Single LED Tutorial]({{< ref "tutorial/simple_LED.md" >}})
* [LCD Display]({{< ref "">}})
//weiter refs (refs überarbeiten)

# Setup

Um ein Spiel über euren Raspberry Pi umzusetzen benötigt ihr nicht nur Verbindungen eines Displays zum Pi, sondern auch Eingabegeräte, 
in diesem Fall Buttons, die auf einem Schaltboard angebracht werden. Das gleiche gilt für das Display. Auch dieses muss über das Schaltboard mit dem Pi verbunden werden.

//weiter Details ...

# Das Programm

Euer Spiel, welches ihr im folgenden programmieren sollt, muss folgende Eigenschaften erfüllen:

Es soll ein standart Snake Spiel, wie es von früher Mobiltelefonen bekannt ist über den Pi realisiert werden.

* Eine Schlange mit einer bestimmten Anfangsgröße, die mittels zweier Buttons vom Spieler gesteuert werden kann und sich mit konstanter      Geschwindikeit vorwärts bewegt
* Zufällig erscheinendes Futter, welches die Schlange vergrößert, wenn sie es frisst (über den Punkt läuft)
* Abbruch des Spiel, wenn die Schlange gegen sich selbst läuft
* Grafisch festgehaltenes Spielfeld mit einer Anzeige für den Score
// Beispielbild
//weiter Programmdetails



# Tipps

{{< collapse "Tipp 1" >}} Geht in logischen Schritten an das Projekt. Überlegt, wie in der OOP, welche Eigenschaften die Snake eigentlich haben soll (obwohl ihr keine eigene Klasse für diese anlegen müsst). Legt darauf basiert Methoden fest, die diese Eigenschaften definieren. Des weiteren könnt ihr das gesamte Progeamm in Methoden aufteilen, die den Spielablauf wiederspiegeln. Methoden könnten sein:
*init() //gameStart()
*move()
*input()
*draw_header()
*render()
{{< /collapse >}}



