+++
title = "Gertboard Grundwissen"
+++

# Voraussetzungen
* [Raspberry Pi Grundwissen]({{< ref "setup/rpi-installation" >}})

# Einführung

Das Gertboard erweitert euren Raspberry Pi und ermöglicht euch schnelle und einfachere Konfigurationen von Ein- und Ausgabegeräten, mit denen ihr im weiteren arbeitet. Das Gertboard muss auf die GPIO Pins des Raspberry Pi gesteckt werden. Herbei sollen beide Pinreihen abgedeckt sein. Rasperry Pi's neuerer Generationen besitzen mehr Pins als das Gertboard Kontaktstellen hat. In diesem Fall müssen nur die ersten 26 Pins abgedeckt sein. Folgendes Bild zeigt einen korrekten Anschluss des Boards:

{{< figure src="/raspidocs/img/GertboardSetup.png" title="Gertboard Anschluss" >}}

Das Gertboard lässt sich in sechs verschiedene funktionelle Blöcke einteilen. Diese Blöcke haben keine Verbindungen untereinander. Nur über die Pins auf dem Board können Verbindungen zwischen einzelnen Blöcken hergestellt werden. Für uns sind erstmal nur drei der sechs Blöcke interessant. Der Block mit den gepufferten I/O, die GPIO-Pins sowie der Motor-Controller:

{{< figure src="/raspidocs/img/GertboardBereiche.png" title="Gertboard Bereiche" >}}

Um diese Blöcke miteinander zu verbinden braucht ihr Kabel (weiblich auf weiblich). Sog. Jumper dienen zum Aktivieren einiger Bereiche. Mit ihnen kann z.B. festgelegt werden ob eine Ausgabe oder Eingabe an bestimmter Stelle erfolgen soll.

{{< figure src="/raspidocs/img/Kable.png" title="Verbindungselemente" >}}

Das blaue Schaubild ist ein Abbild eures Gertboards. Auf diesem sind die Beschriftungen und Zusammenhänge besser nachzuvollziehen, als auf einer Farbfotografie:

{{< figure src="/raspidocs/img/GertboardSkizze.png" title="Schaltskizze Gertboard" >}}


