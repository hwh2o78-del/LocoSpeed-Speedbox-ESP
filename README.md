LocoSpeed Speedometer ESP-Version
=================================

Sketch:
  LocoSpeed_Speedometer_ESP.ino

Unterstuetzte Boards:
  - ESP8266 D1 mini
  - ESP32-S2 mini

Serielle Verbindung:
  9600 Baud
  Gleiches Protokoll wie die Nano-Version und speedbox_pc.py.

ESP8266 WLAN-Betrieb mit Powerbank:
  WLAN-Name     -> LocoSpeed
  Passwort      -> 12345678
  Browser       -> http://192.168.4.1
  USB/Serial bleibt parallel aktiv.
  WLAN-Option   -> Eigenes WLAN oder Heim-WLAN.
  Heim-WLAN     -> Im Browser eintragen, speichern, ESP neu starten.
  Rueckfall     -> Wenn Heim-WLAN nicht erreichbar ist, startet wieder LocoSpeed.
  Massstab      -> Z 1:220, N 1:160, TT 1:120, H0 1:87, 0 1:45
  Anzeige       -> Ziffer oder Zeiger im Browser waehlbar.
  LED-Modus     -> Aus, Start, Messung oder Fehler im Browser waehlbar.

ESP8266 D1 mini Verdrahtung:
  Sensor links   -> D5 / GPIO14
  Sensor rechts  -> D6 / GPIO12
  Radar Ausgang  -> D7 / GPIO13
  OLED SDA       -> D2 / GPIO4
  OLED SCL       -> D1 / GPIO5
  OLED VCC       -> 3V3
  OLED GND       -> GND

ESP32-S2 mini Verdrahtung:
  Sensor links   -> GPIO1
  Sensor rechts  -> GPIO2
  Radar Ausgang  -> GPIO3
  OLED SDA       -> GPIO8
  OLED SCL       -> GPIO9
  OLED VCC       -> 3V3
  OLED GND       -> GND

Hinweise:
  - Sensoren werden mit INPUT_PULLUP betrieben und muessen bei Ausloesung gegen GND schalten.
  - Die Anzeige springt 5 Sekunden nach einer Messung wieder auf Bereit.
  - Einstellungen werden im ESP-EEPROM-Bereich gespeichert.
  - Firmware-Version meldet sich als 1.1.0-ESP.
  - Der ESP8266 stellt ein eigenes WLAN bereit, damit er ohne Router per Powerbank nutzbar ist.
  - Die blaue LED ist standardmaessig aus und kann ueber die Webseite als Statusanzeige genutzt werden.
