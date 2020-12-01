---
description: Skicka data till DCS API med GET- eller POST-metoder.
seo-description: Skicka data till DCS API med GET- eller POST-metoder.
seo-title: DCS API-metoder
solution: Audience Manager
title: DCS API-metoder
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 5%

---


# [!DNL DCS] [!DNL API] Metoder  {#dcs-api-methods}

Skicka data till [!DNL DCS] [!DNL API] med metoderna `GET` eller `POST`.

Du kan skicka data till [!DNL DCS] med någon av metoderna `GET` eller `POST`. Ta en titt på exempelsamtalen nedan med [curl](https://curl.haxx.se/). I alla tre exempelanropen lägger vi till signalerna `c_likes = famous popstar` och `c_loves = famous actress` till enhetsprofilen `12345678901234567890123456789012345678`.

## Skicka data via [!DNL GET] {#send-data-via-get}

Observera att den största tillåtna storleken för `GET`-anrop är 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Skicka data via [!DNL POST] {#send-data-via-post}

Observera kraven för att skicka data med metoden `POST`:

* Den största tillåtna storleken är 32 kB.
* Ange innehållstypen till `application/x-www-form-urlencoded`.

### Exempel på samtal

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
