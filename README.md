# Adafruit.IO

Grejen: Skicka data från webben till NodeMCU till Adafruit.IO med MQTT

## MQTT

* Message Queue Telemetry Transport
* Light weight
* Ligger ovan TCP/IP
* Bygger på principen publish/subscribe
* Enheter publicerar _Topic_ till central _Broker_
* Central _Broker_ sänder till enheter som _Subscribes_ på _Topic_
* Topic's är som en kanal
* En topic måste...
  * vara minst ett tecken långt
  * Case sensitive
  * kan innehålla <blanksteg>
  * vara UTF-8 enkodat
*


1. Skapa konto på https://io.adafruit.com och logga in
2. Notera villkoren:

30 data points per minute
30 days of data storage
10 feeds
5 dashboards

3. Med exempelvis NodeMCU, anslut D5 --> LED --> 220R --> GND
3. Med Arduino IDE anslut rätt board
4. Installera följande Libraries: 
  * Adafruit IO
  * Adafruit MQTT Library
  * Kanske någon mer?
5. Ladda in exempelsketch: ```adafruitio_07_digital_out```
6. Redigera ```config.h```
7. Hämta följande värden från io.adafruit.com:
  * IO_USERNAME
  * IO_KEY
  
8. Skriv in dessa och WiFi-parametrar i ```config.io```
9. OBS - Notera följande på rad 27 i filen ```adafruitio_07_digital_out```
  
  *AdafruitIO_Feed *digital = io.feed("digital");*
  
  Detta betyder att topic är "digital"
  
9. Provkompilera, rätta eventuella fel och ladda upp


