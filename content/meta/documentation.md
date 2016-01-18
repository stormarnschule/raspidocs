+++
title = "Entstehung Dokumentation"
+++

Auf dieser Seite wird erläutert, wie diese Dokumentation entsteht. Es wird
dabei hauptsächlich auf technische Details eingegangen, die zeigen sollen,
wie aus einer Markdown-Datei eine vollständige HTML-Webseite wird.

# Schreiben

Die gesamte Dokumentation besteht aus mehreren [Markdown](http://markdown.de)-Dateien,
welche von einem Programm nach HTML übersetzt werden.

Markdown enthält einige Anweisungen, die für die Formatierung von Text verwendet
werden. Ein Beispiel:

```markdown
# Titel
## Untertitel

Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod
tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At
vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd
gubergren, no sea takimata sanctus est.

Auflistung

* Punkt 1
* Punkt 2

**fett** und *kursiv*
```

Dieser Code wird in folgendes HTML kompiliert:

```html
<h1>Titel</h1>
<h2>Untertitel</h2>

<p>
    Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
    eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
    voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet
    clita kasd gubergren, no sea takimata sanctus est.
</p>

<p>Auflistung</p>

<ul>
    <li>Punkt 1</li>
    <li>Punkt 2</li>
</ul>

<strong>fett</strong> und <em>kursiv</em>
```

Wann genau dies geschieht, seht ihr weiter unten im Punkt **Übersetzen nach HTML**.

# Hosting

Die Markdown-Datein sind auf [GitHub](https://github.com) in einem
[Git-Repository](http://rogerdudler.github.io/git-guide/index.de.html)
gespeichert. GitHub ist eine Plattform, wo Entwickler ihren Code kostenlos
für andere zu Verfügung stellen können.

Das Repository, wo man die Markdown-Dokumentation sehen kann, 
[findet man hier](https://github.com/stormarnschule/raspidocs). 

# Übersetzen nach HTML

Da Webbrowser Webseiten in HTML lesen und dann darstellen, wird der Markdown-Code
nach HTML kompiliert. Dies geschieht jedesmal, wenn ein neuer Commit hochgeladen wird,
also der Code geändert wurde.

Die Tatsache, dass wir direkt nach HTML übersetzen, wenn es neuen Markdown-Code gibt,
anstatt ihn bei jedem Aufruf unserer Seite zu kompilieren, hat den Vorteil, das
dies viel schneller ist. Ohnehiin kann GitHub nur statische HTML-Dateien
bereitstellen, es läuft kein dynamisches Serverskript, welches die Seiten beim Laden
anpasst oder erstellt.

Diese Methode wird häufig für Blogs oder Dokumentationen angewendet, um geringe
Ladezeiten zu ermöglichen. Diese Aufgabe übernimmt bei uns das Programm
[hugo](https://gohugo.io). Es rendert den Markdown-Code unter Verwendung eines
Themes zu HTML-Code. Das Theme bestimmt dabei Farben, Schriftgröße und Layout
der fertigen Webseite. Es gibt also an, auf welche Art das Markdown, welches
bloß zur Strukturierung des Textes dient, dargestellt wird.

# Automatisches Übersetzen

Damit wir nicht jedes Mal, wenn wir etwas verändert haben, Hugo lokal ausführen
und dann den HTML-Code hochladen müssen, gibt es etwas, was sich
**Continuous Delivery** nennt.  
Wir benutzen hierfür [Wercker](http://wercker.com/about). Das ist eine Web-App,
die bei jedem Commit eines GitHub-Repository ein Shell-Skript ausführt.
Dieses Skript startet dann Hugo mit dem Code aus dem Repository und dem Theme,
welches sich ebenfalls in dem Repos befindet.

Wenn das Übersetzen erfolgreich war, lädt Wercker das Ergebnis in den Zweig
[gh-pages](https://github.com/stormarnschule/raspidocs/tree/gh-pages) hoch.

Wenn mann nun auf die Webseite **stormarnschule.github.io/raspidocs** geht,
liefert GitHub die HTML-Dateien aus dem **gh-pages** Zweig des **raspidocs**
Repositories.

# Fazit des Workflows

Markdown bietet den großen Vorteil, dass es sich um reine Textdateien ohne
komplizierte Syntax, wie HTML sie hat, handelt. Dies erhöht die Lesbarkeit
und die Geschwindigkeit beim Schreiben.

Dadurch, dass ein Theme das Layout übernimmt, muss man beim Verfassen der
Inhalte nicht auf das Layout acht geben. Außerdem kann man durch einfaches
Austauschen des Themes die gesamte Webseite umgestalten, ohne in jeder
Datei HTML-Code anpassen zu müssen.

Zuletzt ist das Hosting über GitHub eines der zuverlässigsten und schnellsten
die es gibt. Dazu ist es kostenlos, sorgt also für ein langes Fortbestehen
der Webseite.

So muss man sich nach einer kleinen Einrichtung, die auch noch schneller
als bei klassischen Methoden von statten geht, nur noch um den Inhalt kümmern.
Alles Weitere übernehmen ab dann GitHub und Wercker.