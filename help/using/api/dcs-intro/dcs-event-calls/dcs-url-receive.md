---
description: Fortsätt här för information om hur du begär ett DCS-svar i ett /event-samtal. Det här avsnittet innehåller ett svarsexempel och definitioner för vanliga dataelement i ett svar.
seo-description: Fortsätt här för information om hur du begär ett DCS-svar i ett /event-samtal. Det här avsnittet innehåller ett svarsexempel och definitioner för vanliga dataelement i ett svar.
seo-title: Ta emot data från DCS
solution: Audience Manager
title: Ta emot data från DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---


# Ta emot data från DCS {#receive-data-from-the-dcs}

Fortsätt här för information om hur du begär ett [!DNL DCS] svar i ett `/event` samtal. Det här avsnittet innehåller ett svarsexempel och definitioner för vanliga dataelement i ett svar.

Innan du granskar innehållet ska du läsa [Skicka data till DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS-svarsparametrar: En granskning {#dcs-response-parameters}

Din [!DNL DCS] förfrågan måste innehålla `d_rtbd=json` om du vill få ett svar från [!DNL DCS]. Data returneras inte [!DNL DCS] om du utelämnar den här parametern. Ett grundläggande anrop till användaren [!DNL DCS] för att begära data använder den här syntaxen:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Exempelsvar {#sample-response}

Kom ihåg att från [Skicka data till DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) -dokumentationen [!DNL Acme, Inc.] ringde det fiktiva företaget:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Eftersom det här anropet innehåller den obligatoriska svarsparametern [!DNL DCS] skickas objektet tillbaka som [!DNL JSON] visas nedan. Du kan vara mer komplex eller liknande.

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
| `c` | En URL som har angetts som ett [URL-mål](../../../features/destinations/create-url-destination.md). |
| `cn` | Namnet eller ID som angetts i fältet för cookie-namn för en [cookie-destination](../../../features/destinations/create-cookie-destination.md). |
| `cv` | De värden som skickas till målet som definieras av parametern &quot;cn&quot;:&quot; målnamn&quot;. |
| `dcs_region` | DCS-anrop [från server till server](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Det här objektet innehåller information för alla URL-mål som är konfigurerade i användargränssnittet. Objektets lista är dynamisk baserat på användarens åtgärder. |
| `dmn` | Det här är domänen som anges i cookie-domänfältet för en cookie-destination. Se [Valfria inställningar för cookie-mål](../../../features/destinations/cookie-destination-options.md).  För integreringar mellan servrar rekommenderar vi att du använder en domän som `aam-api.com`. |
| `e` | Den säkra URL som har angetts i ett URL-mål. |
| `stuff` | Det här objektet innehåller information för alla cookie-mål. Objektets lista är dynamisk baserat på användarens åtgärder. |
| `tid` | Transaktions-ID, som är ett unikt 12-tecken-ID som används för felsökning. Varje /event-anrop till DCS får en tid som du kan referera till i supportfrågor för att få ett bättre och snabbare svar. |
| `ttl` | Kakans värde för time-to-live i dagar. |
| `u` och `uuid` | Unikt användar-ID som tilldelats av Audience Manager. Detta är nödvändigt om du gör DCS-anrop [från](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)server till server. |
| `y` | Måltyp, iFrame (`iframe`) eller image (`img`). |

>[!MORELIKETHIS]
>
>* [Nyckelvärdesprefix och variabler som stöds av DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

