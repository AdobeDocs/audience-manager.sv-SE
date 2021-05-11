---
description: En översikt över DIL och hur det fungerar.
seo-description: En översikt över DIL och hur det fungerar.
seo-title: Förstå Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Förstå Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: Implementering av DIL
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 16%

---

# Förstå [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Översikt, Komma igång och kodmetoder som finns i [!DNL Audience Manager DIL]-kodbiblioteket.

>[!IMPORTANT]
>
>Från och med version 8.0 (släppt augusti 2018) är [!UICONTROL DIL] beroende av [Adobe Experience Platform identitetstjänst](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html), version 3.3 eller senare. Den förlitar sig på [!DNL ID Service] för att utlösa ID-synkroniseringar och URL-mål. Ett fel uppstår om [!DNL ID Service] saknas, är gammal eller inte har konfigurerats.
>
>Vi rekommenderar att du använder [!DNL Adobe Experience Platform Launch] för att implementera och hantera dina [!DNL DIL]- och [!DNL Adobe Experience Platform Identity Service]-bibliotek.

Du kan även hämta de senaste Experience Cloud- och [!DNL DIL]-versionerna från vår GitHub-sida. Se nedladdningslänkar nedan:

* Hämta [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Hämta [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Syfte med DIL {#purpose-dil}

[!UICONTROL DIL] är ett API-bibliotek. Du kan tänka dig det som en brödtext med hjälpkod för [!DNL Adobe Audience Manager]. Du behöver inte använda [!DNL Audience Manager], men metoderna och funktionerna [!UICONTROL DIL] innebär att du inte behöver utveckla egen kod för att skicka data till [!DNL Audience Manager]. Dessutom skiljer sig [!UICONTROL DIL] från API:t som tillhandahålls av [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html). Den tjänsten är utformad för att hantera besökaridentitet över olika [!DNL Experience Cloud]-lösningar. [!UICONTROL DIL] är däremot utformat för att:

* Gör händelseanrop och skicka data till [datainsamlingsservern](../reference/system-components/components-data-collection.md).
* Skicka data till [mål](../features/destinations/destinations.md).

## Hämta och implementera DIL-kod {#get-implement-dil-code}

[!UICONTROL DIL] finns kod att ladda ned  **[här](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Observera att från och med version 8.0 (släppt augusti 2018) har [!UICONTROL DIL] ett svårt beroende av [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), version 3.3 eller senare. Den förlitar sig på [!DNL ID Service] för att aktivera ID-synk och [!DNL URL destinations]. Ett fel uppstår om [!DNL ID Service] saknas, är gammal eller inte har konfigurerats.

I stället för att arbeta med [!UICONTROL DIL] och konfigurera [!DNL Audience Manager] manuellt rekommenderar vi att du använder [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) i stället. [!DNL Adobe Experience Platform Launch] är det implementeringsverktyg som rekommenderas eftersom det förenklar koddistribution, placering och versionshantering. Läs mer om [Audience Manager-tillägget](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) i [!DNL Adobe Experience Platform Launch].

## Samtal {#sample-code}

[!UICONTROL DIL] skickar data till  [!DNL Audience Manager] i ett händelseanrop. Ett händelseanrop är en XML HTTP-begäran från din sida. Den använder en `POST`-metod för att skicka data i brödtexten för begäran.

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
