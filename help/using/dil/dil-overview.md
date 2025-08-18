---
description: En översikt över DIL och hur det fungerar.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Förstå Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# Förstå [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av tillägget [!DNL Data Integration Library (DIL)] och [!DNL DIL].
>
>Befintliga kunder kan fortsätta använda sin [!DNL DIL]-implementering. Adobe kommer dock inte att utveckla [!DNL DIL] efter den här punkten. Kunder uppmuntras att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för sin långsiktiga datainsamlingsstrategi.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

Översikt, Komma igång och kodmetoder som är tillgängliga i kodbiblioteket [!DNL Audience Manager DIL].

>[!IMPORTANT]
>
>Från och med version 8.0 (släppt augusti 2018) är [!UICONTROL DIL] beroende av [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 eller senare. Den förlitar sig på [!DNL ID Service] för att utlösa ID-synkroniseringar och URL-mål. Ett fel inträffar om [!DNL ID Service] saknas, är gammal eller inte har konfigurerats.
>
>Vi rekommenderar att du använder [!DNL Adobe Experience Platform Tags] för att implementera och hantera dina [!DNL DIL]- och [!DNL Adobe Experience Platform Identity Service]-bibliotek.

Du kan även hämta de senaste Experience Cloud- och [!DNL DIL]-versionerna från vår GitHub-sida. Se nedladdningslänkar nedan:

* Hämta [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Hämta [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL syfte {#purpose-dil}

[!UICONTROL DIL] är ett API-bibliotek. Du kan tänka dig det som en samling hjälpkod för [!DNL Adobe Audience Manager]. Det är inte nödvändigt att använda [!DNL Audience Manager], men metoderna och funktionerna i [!UICONTROL DIL] innebär att du inte behöver utveckla din egen kod för att skicka data till [!DNL Audience Manager]. Dessutom skiljer sig [!UICONTROL DIL] från API:t som tillhandahålls av [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). Tjänsten är utformad för att hantera besökaridentitet över olika [!DNL Experience Cloud]-lösningar. [!UICONTROL DIL] är däremot utformat för att:

* Gör händelseanrop och skicka data till [datainsamlingsservern](../reference/system-components/components-data-collection.md).
* Skicka data till [mål](../features/destinations/destinations.md).

## Hämta och implementera DIL Code {#get-implement-dil-code}

Koden [!UICONTROL DIL] kan hämtas **[här](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Observera att från och med version 8.0 (släppt augusti 2018) har [!UICONTROL DIL] ett svårt beroende av [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 eller senare. Den förlitar sig på [!DNL ID Service] för att utlösa ID-synkroniseringar och [!DNL URL destinations]. Ett fel inträffar om [!DNL ID Service] saknas, är gammal eller inte har konfigurerats.

I stället för att arbeta med [!UICONTROL DIL] och konfigurera [!DNL Audience Manager] manuellt rekommenderar vi att du använder [Adobe Experience Platform-taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) i stället. [!DNL Adobe Experience Platform Tags] rekommenderas som implementeringsverktyg eftersom det förenklar koddistribution, placering och versionshantering. Läs mer om [Audience Manager-tillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) i [!DNL Adobe Experience Platform Tags].

## Exempel på samtal {#sample-code}

[!UICONTROL DIL] skickar data till [!DNL Audience Manager] i ett händelseanrop. Ett händelseanrop är en XML HTTP-begäran från din sida. Den använder en `POST`-metod för att skicka data i brödtexten för begäran.

| Element för händelseanrop | Beskrivning |
|--- |--- |
| URL | DIL-händelseanrop använder följande syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Brödtext | Som framgår av exemplet nedan skickar DIL data som nyckelvärdepar. Specialprefixtecken identifierar nyckelvärdepar som Audience Manager- eller partnervariabler.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Se även:
* [Prefixkrav för nyckelvariabler](../features/traits/trait-variable-prefixes.md)
* [Attribut som stöds för DCS API-anrop](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Relaterade länkar

* [DIL Användningsexempel och kodexempel](/help/using/dil/dil-use-cases.md)
* [DIL-metoder på klassnivå](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-metoder på instansnivå](/help/using/dil/dil-instance-methods.md)
* [DIL Modules](/help/using/dil/dil-modules.md)
* [DIL Tools](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
