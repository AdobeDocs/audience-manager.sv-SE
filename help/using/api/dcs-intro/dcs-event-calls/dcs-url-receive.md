---
description: Fortsätt här för information om hur du begär ett DCS-svar i ett /event-samtal. Det här avsnittet innehåller ett svarsexempel och definitioner för vanliga dataelement i ett svar.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Ta emot data från DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 2%

---

# Ta emot data från DCS {#receive-data-from-the-dcs}

Fortsätt här för information om hur du begär en [!DNL DCS] svar i `/event` ring. Det här avsnittet innehåller ett svarsexempel och definitioner för vanliga dataelement i ett svar.

Innan du granskar det här innehållet, se [Skicka data till DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS-svarsparametrar: En granskning {#dcs-response-parameters}

Dina [!DNL DCS] begäran måste innehålla `d_rtbd=json` om du vill få ett svar från [!DNL DCS]. The [!DNL DCS] returnerar inte data om du utelämnar den här parametern. Ett grundläggande samtal till [!DNL DCS] för att begära data använder denna syntax:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Exempelsvar {#sample-response}

Återkalla det från [Skicka data till DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) dokumentation, det fiktiva företaget [!DNL Acme, Inc.] ringde:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Eftersom det här anropet innehåller den obligatoriska svarsparametern [!DNL DCS] skickas tillbaka [!DNL JSON] objektet som visas nedan. Du kan vara mer komplex eller liknande.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Svarsparametrar {#response-parameters}

Tabellen nedan listar och definierar de vanligaste parametrarna som du kan se i ett svar från [!DNL DCS]. Detta gäller för händelseanrop eller andra [!DNL DCS] [!DNL API] frågor som returnerar data.

| Parameter | Beskrivning |
|--- |--- |
| `c` | En URL som har angetts som en [URL-mål](../../../features/destinations/create-url-destination.md). |
| `cn` | Namnet eller ID som angetts i fältet för cookie-namn för en [cookie-mål](../../../features/destinations/create-cookie-destination.md). |
| `cv` | De värden som skickas till målet som definieras av parametern &quot;cn&quot;:&quot; målnamn&quot;. |
| `dcs_region` | The [DCS-anrop från server till server](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Det här objektet innehåller information för alla URL-mål som är konfigurerade i användargränssnittet. Objektets lista är dynamisk baserat på användarens åtgärder. |
| `dmn` | Det här är domänen som anges i cookie-domänfältet för en cookie-destination. Se [Valfria inställningar för cookie-mål](../../../features/destinations/cookie-destination-options.md).  För integreringar mellan server och server rekommenderar vi att du använder en domän som `aam-api.com`. |
| `e` | Den säkra URL som har angetts i ett URL-mål. |
| `stuff` | Det här objektet innehåller information för alla cookie-mål. Objektets lista är dynamisk baserat på användarens åtgärder. |
| `tid` | Transaktions-ID, som är ett unikt 12-tecken-ID som används för felsökning. Varje /event-anrop till DCS får en tid som du kan referera till i supportfrågor för att få ett bättre och snabbare svar. |
| `ttl` | Kakans värde för time-to-live i dagar. |
| `u` och `uuid` | Unikt användar-ID som tilldelats av Audience Manager. Detta är nödvändigt om du tänker göra [DCS-anrop från server till server](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Måltyp, iFrame (`iframe`) eller bild (`img`). |

>[!MORELIKETHIS]
>
>* [Nyckelvärdesprefix och variabler som stöds av DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

