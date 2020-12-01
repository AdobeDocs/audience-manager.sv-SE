---
description: Fortsätt här för information om hur du begär ett DCS-svar i ett /event-samtal. Det här avsnittet innehåller ett svarsexempel och definitioner för vanliga dataelement i ett svar.
seo-description: Fortsätt här för information om hur du begär ett DCS-svar i ett /event-samtal. Det här avsnittet innehåller ett svarsexempel och definitioner för vanliga dataelement i ett svar.
seo-title: Ta emot data från DCS
solution: Audience Manager
title: Ta emot data från DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 3%

---


# Ta emot data från DCS {#receive-data-from-the-dcs}

Fortsätt här för information om hur du begär ett [!DNL DCS]-svar i ett `/event`-anrop. Det här avsnittet innehåller ett svarsexempel och definitioner för vanliga dataelement i ett svar.

Innan du granskar innehållet ska du läsa [Skicka data till DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS-svarsparametrar: En granskning {#dcs-response-parameters}

Din [!DNL DCS]-begäran måste innehålla `d_rtbd=json` om du vill få ett svar från [!DNL DCS]. [!DNL DCS] returnerar inte data om du utelämnar den här parametern. Ett grundläggande anrop till [!DNL DCS] för att begära data använder den här syntaxen:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Samplingssvar {#sample-response}

Kom ihåg att från [Skicka data till DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)-dokumentationen gjorde det fiktiva företaget [!DNL Acme, Inc.] det här anropet:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Eftersom anropet innehåller den obligatoriska svarsparametern skickade [!DNL DCS] tillbaka [!DNL JSON]-objektet som visas nedan. Du kan vara mer komplex eller liknande.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Svarsparametrar {#response-parameters}

Tabellen nedan listar och definierar de vanligaste parametrarna som du kan se i ett svar från [!DNL DCS]. Detta gäller för händelseanrop eller andra [!DNL DCS] [!DNL API]-frågor som returnerar data.

| Parameter | Beskrivning |
|--- |--- |
| `c` | En URL som har angetts som [URL-mål](../../../features/destinations/create-url-destination.md). |
| `cn` | Namnet eller ID som angetts i fältet för cookie-namn för en [cookie-destination](../../../features/destinations/create-cookie-destination.md). |
| `cv` | De värden som skickas till målet som definieras av parametern &quot;cn&quot;:&quot; målnamn&quot;. |
| `dcs_region` | DCS-anropen för [server-till-server](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Det här objektet innehåller information för alla URL-mål som är konfigurerade i användargränssnittet. Objektets lista är dynamisk baserat på användarens åtgärder. |
| `dmn` | Det här är domänen som anges i cookie-domänfältet för en cookie-destination. Se [Valfria inställningar för cookie-mål](../../../features/destinations/cookie-destination-options.md).  För integreringar mellan server och server rekommenderar vi att du använder en domän som `aam-api.com`. |
| `e` | Den säkra URL som har angetts i ett URL-mål. |
| `stuff` | Det här objektet innehåller information för alla cookie-mål. Objektets lista är dynamisk baserat på användarens åtgärder. |
| `tid` | Transaktions-ID, som är ett unikt 12-tecken-ID som används för felsökning. Varje /event-anrop till DCS får en tid som du kan referera till i supportfrågor för att få ett bättre och snabbare svar. |
| `ttl` | Kakans värde för time-to-live i dagar. |
| `u` och  `uuid` | Unikt användar-ID som tilldelats av Audience Manager. Detta krävs om du gör [DCS-anrop från server till server](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Måltyp, iFrame (`iframe`) eller bild (`img`). |

>[!MORELIKETHIS]
>
>* [Nyckelvärdesprefix och variabler som stöds av DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

