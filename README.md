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

## Setup

1. Skapa konto på https://io.adafruit.com och logga in
2. Notera villkoren:

* 30 data points per minute
* 30 days of data storage
* 10 feeds
* 5 dashboards

3. Med exempelvis NodeMCU, anslut D5 --> LED --> 220R --> GND
4. Med Arduino IDE anslut rätt board
5. Installera följande Libraries: 

  * Adafruit IO
  * Adafruit MQTT Library
  * Arduino HTTP Client
  * Kanske någon mer?
  
6. Ladda in exempelsketch: ```adafruitio_07_digital_out```
7. Redigera ```config.h```
8. Hämta följande värden från io.adafruit.com:

  * AIO KEY - Username - IO_USERNAME
  * AIO KEY - Active Key - IO_KEY
  
9. Skriv in dessa och WiFi-parametrar i ```config.io```
10. OBS - Notera följande på rad 27 i filen ```adafruitio_07_digital_out```
  
  ```AdafruitIO_Feed *digital = io.feed("digital");```
  
  Detta betyder att topic är "digital"
  
11. Provkompilera, rätta eventuella fel och ladda upp
12. Med io.adafruit.com klicka _Feeds_ och skapa ett nytt _Feed_ med namnet "digital"
12. Med io.adafruit.com klicka _Dashboards_ och skapa nytt dashboard med exempelvis namnet LED5 och en beskrivning
13. Skapa ett nytt _Block_ med en _Toggle_ och sätt Botton On Text till ```1``` respektive ```0```
14. Funkar?
15. Vad ger detta dig för nya idéer?



