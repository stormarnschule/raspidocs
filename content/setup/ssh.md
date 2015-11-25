+++
date = "2015-11-23T09:41:32+01:00"
title = "SSH Verbindung"
+++

# Konzept

Das Herstellen einer SSH-Verbindung zum Rasperry Pi ist sehr nützlich zum
Ausführen von Befehlen. Man kann sich dann das anschließen von Monitor und
Tastatur an den Pi sparen und vom eigenem Laptop oder Schulrecher aus den
Pi steuern.

Je nach Betriebsystem ist das Verbinden zum Pi unterschiedlich. Dise Anleitung
gilt für Linux, OSX und Windows.

# Verbinden mit Pi

## Linux, OSX

OSX basiert auf Linux und da Linux einen SSH-Klienten mitbringt, gelten diese
Schritte auch für OSX.

1. Öffne das Terminal
2. Führe folgenden Befehl aus:

    ```
    ssh pi@<ip>
    ```
    __\<ip>__ ist durch die IP-Addresse oder den Hostnamen des Raspberry Pis zu
    ersetzten.
3. Du bist nun auf dem Raspberry Pi und die Befehle, die du schreibt, werden
   direkt auf dem Pi ausgeführt
4. Um zu Beenden, schließe entweder einfach das Terminal oder sende `exit` an
   den Pi, um zum Terminal deines PCs zurückzukehren
   
## Windows

Anders als vorher hat Windows keinen eigenen SSH-Klienten, deshalb müssen wir
uns einen herunterladen und installieren.

1. Lade [Putty](the.earth.li/~sgtatham/putty/latest/x86/putty.exe) herunter und
    ziehen es an einen geeigneten Ort, z.B. den Desktop
2. Starte Putty
3. Gib in das Feld `Host Name (or IP Address)` folgendes ein: `pi@<ip>`.  
__\<ip>__ ist durch die IP-Addresse oder den Hostnamen des Raspberry Pis zu
ersetzten
4. Drücke Enter oder klicke auf __Open__ unten rechts
5. Du bist nun auf dem Raspberry Pi und die Befehle, die du schreibt, werden
   direkt auf dem Pi ausgeführt
6. Zum Beenden kannst du einfach das Putty-Fenster schließen