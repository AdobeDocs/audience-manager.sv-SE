---
description: En översikt över DIL och hur det fungerar.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l,
solution: Audience Manager
title: Förstå Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 11%

---

# Förstå [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Översikt, Komma igång och kodmetoder finns i [!DNL Audience Manager DIL] kodbibliotek.

>[!IMPORTANT]
>
>Från och med version 8.0 (släppt augusti 2018), [!UICONTROL DIL] är beroende av [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 eller senare. Det bygger på [!DNL ID Service] att avfyra ID-synk och URL-mål. Ett fel inträffar om [!DNL ID Service] saknas, är gammal eller har inte konfigurerats.
>
>Vi rekommenderar att du använder [!DNL Adobe Experience Platform Tags] implementera och hantera [!DNL DIL] och [!DNL Adobe Experience Platform Identity Service] bibliotek.

Du kan även hämta de senaste Experience Cloud och [!DNL DIL] från vår GitHub-sida. Se nedladdningslänkar nedan:

* Ladda ned [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Hämta [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL syfte {#purpose-dil}

[!UICONTROL DIL] är ett API-bibliotek. Du kan tänka dig det som en massa hjälpkod för [!DNL Adobe Audience Manager]. Det är inte nödvändigt att använda [!DNL Audience Manager], men metoderna och funktionerna [!UICONTROL DIL] innebär att du inte behöver utveckla egen kod för att skicka data till [!DNL Audience Manager]. Dessutom [!UICONTROL DIL] skiljer sig från API:t i [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). Den tjänsten är utformad för att hantera besökaridentitet över olika [!DNL Experience Cloud] lösningar. I motsats till [!UICONTROL DIL] har utformats för att

* Ring eventsamtal och skicka data till [Datainsamlingsserver](../reference/system-components/components-data-collection.md).
* Skicka data till [mål](../features/destinations/destinations.md).

## Hämta och implementera DIL-kod {#get-implement-dil-code}

[!UICONTROL DIL] koden finns tillgänglig för hämtning **[här](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Observera att från och med version 8.0 (släppt augusti 2018) [!UICONTROL DIL] är beroende av [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 eller senare. Det bygger på [!DNL ID Service] avfyrar ID-synk och [!DNL URL destinations]. Ett fel inträffar om [!DNL ID Service] saknas, är gammal eller har inte konfigurerats.

I stället för att arbeta med [!UICONTROL DIL] och konfigurera [!DNL Audience Manager] rekommenderar vi att du använder [Adobe Experience Platform-taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) i stället. [!DNL Adobe Experience Platform Tags] är det implementeringsverktyg som rekommenderas eftersom det förenklar koddistribution, placering och versionshantering. Läs mer om [Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Exempel på samtal {#sample-code}

[!UICONTROL DIL] skickar data till [!DNL Audience Manager] i ett event call. Ett händelseanrop är en XML HTTP-begäran från din sida. Den använder en `POST` metod för att skicka data i begärans innehåll.

| Element för händelseanrop | Beskrivning |
|--- |--- |
| URL | DIL-händelseanrop använder följande syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Brödtext | Som visas i exemplet nedan skickar DIL data som nyckelvärdepar. Specialprefixtecken identifierar nyckelvärdepar som Audience Manager eller partnervariabler.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Se även:
* [Prefixkrav för nyckelvariabler](../features/traits/trait-variable-prefixes.md)
* [Attribut som stöds för DCS API-anrop](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Relaterade länkar

* [DIL-användningsexempel och kodexempel](/help/using/dil/dil-use-cases.md)
* [DIL-metoder på klassnivå ](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-metoder på instansnivå](/help/using/dil/dil-instance-methods.md)
* [DIL-moduler](/help/using/dil/dil-modules.md)
* [DIL-verktyg](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
