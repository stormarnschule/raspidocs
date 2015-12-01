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

Die Bereiche, die für uns von Bedeutung sind, werden hier in den Farben schwarz, rosa und rot gekennzeichnet. Um die Bereiche für Lichter und Buttons(rot) oder die Motorsteuerung(rosa) nutzen zu können, sprich diese mit dem Pi zu adressieren muss eine Verbindung zu den GPIO Pins(schwarz) geschlossen werden. Um diese Blöcke miteinander zu verbinden braucht ihr Kabel (weiblich auf weiblich). Des weiteren müssen innerhalb dieser Bereiche teilweise Verbindungen gestetzt werden, um entsprechende Funktionalität zu erhalten. Diese Verbindung können zum Beispiel bestimmten, ob es sich bei einem Element um eine Input oder Output handelt. Sog. Jumper dienen zum Aktivieren dieser Bereiche. Mit ihnen kann z.B. festgelegt werden ob eine Ausgabe oder Eingabe an bestimmter Stelle erfolgen soll.

{{< figure src="/raspidocs/img/Kable.png" title="Verbindungselemente" >}}

Das blaue Schaubild ist ein Abbild eures Gertboards. Auf diesem sind die Beschriftungen und Zusammenhänge besser nachzuvollziehen, als auf einer Farbfotografie:

{{< figure src="/raspidocs/img/GertboardSkizze.png" title="Schaltskizze Gertboard" >}}

Die GP-Pins(unten auf der Abbildung) bilden die Verbindung zum Pi, mit der Reihe der B1-B12 Pins kann auf die LEDs und die Buttons auf dem Gertboard zugegriffen werden und MOTA und MOTB werden bei der Motorsteuerung genutzt. 
Ein Buffer der immer gesetzt werden muss liegt bei der 3v3 Kennzeichnung auf dem Board. Hier müssen die oberen der drei Pins miteinander verbunden sein. Dies stellt eine Stromversorgung des Pi mit einer Spannung von 3,3V sicher, weshalb dieser Buffer immer gesetzt sein muss, um die Funktionalität des Gertboards zu gewährleisten.
Des weiteren interessieren uns die B-input und die B-output Pins im rot gekennzeichneten Bereich auf der Photografie des Boards. Hierbei sind die Pins stets aus der Sicht des Gertboards zu betrachten. Ein Output gesetzter Pin übermittelt so jegliche Information, die das Gertboard verlassen, während ein Input die Informationen betrachtet, die an das Board geschickt werden. Da wir unsere Programme auf dem Raspberry Pi erstellen werden, müssen wir hier umdenken. Ein output des Pi's ist ein Input beim Gertboard und umgekehrt. Um z.B. die Buttons zu nutzen, muss auf dem Gerboard eine Output-Verbindung gesetzen werden. Für die LEDs müssen die Puffer als Input gesteckt sein.
Auch bei den GPIO Pins gibt es einiges zu beachten. Die Pin

//link pinout.xyz

