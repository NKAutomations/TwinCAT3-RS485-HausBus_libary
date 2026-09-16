# TwinCAT3-RS485-HausBus_libary
Twincat Lib für die Kommunikation mit Haus-Bus Geräten über RS485

Implementierte und getestete Geräte:
- 6F Bus Taster
- 8 Kanal Rollomodul
- 4 Kanal (24/48V) Led Dimmermodul
- 4 Kanal Temperatursensor (DIY ESP Projekt mit Hausbus Ascii Tempegrammen und DS18B20 Sensoren)

## RS485 FIFO Master

Der `fb_RS485FiFoMaster` verwaltet das Senden und Empfangen der HausBus-Telegramme ueber RS485. Die vorhandenen Geraetebausteine koennen unveraendert weiterverwendet werden.

Enthaltene Funktionen:
- Verarbeitung des Empfangs auch waehrend eines aktiven Sendevorgangs
- RX- und TX-Kollisionsueberwachung
- Automatische Wiederholung fehlerhafter Telegramme bis zu drei Mal
- Wiederholungsverzoegerung von 20 ms
- Retry-Unterstuetzung fuer automatische Ping-Telegramme
- Bestehende FIFO-Sende- und Done-Signale bleiben kompatibel

Die Retry-Logik schuetzt vor kurzzeitigen Stoerungen auf dem Bus. Empfangene Telegramme werden weiterhin durch die aufrufende Anwendung ausgewertet. Eine vollstaendige Pruefung sollte mit der verwendeten RS485-Hardware und realer Buslast erfolgen.




