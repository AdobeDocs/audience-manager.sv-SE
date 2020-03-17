---
description: Skicka data till DCS API med GET- eller POST-metoder.
seo-description: Skicka data till DCS API med GET- eller POST-metoder.
seo-title: DCS API-metoder
solution: Audience Manager
title: DCS API-metoder
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# DCS API-metoder {#dcs-api-methods}

Skicka data till [!UICONTROL DCS] med hjälp av [!DNL API] eller `GET` `POST` metoder.

Du kan skicka data till [!UICONTROL DCS] med någon av `GET` metoderna eller `POST` . Ta en titt på exempelsamtalen nedan med [vändning](https://curl.haxx.se/). I alla tre samplingsanropen lägger vi till signalerna `c_likes = famous popstar` och `c_loves = famous actress` till enhetsprofilen `12345678901234567890123456789012345678`.


## Skicka data via GET {#send-data-via-get}

Observera att den största tillåtna storleken för `GET` anrop är 8 kB.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Skicka data via POST {#send-data-via-post}

Observera kraven för att skicka data med `POST` metoden:

* Den största tillåtna storleken är 32 kB.
* Ange innehållstypen till `application/x-www-form-urlencoded`.

### Exempel på samtal

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
