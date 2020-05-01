---
description: En översikt över DIL och hur det fungerar.
seo-description: En översikt över DIL och hur det fungerar.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Understanding the Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Översikt, komma igång och kodmetoder som finns i Audience Manager DIL-kodbiblioteket.

>[!IMPORTANT]
>
>Från och med version 8.0 (släppt augusti 2018) är [!UICONTROL DIL] Adobe Experience Platform Identity Service [](https://docs.adobe.com/content/help/en/id-service/using/home.html), version 3.3 eller senare, beroende av varandra. Den förlitar sig på ID-tjänsten för att utlösa ID-synkroniseringar och URL-mål. Ett fel inträffar om ID-tjänsten saknas, är gammal eller inte har konfigurerats.
>
>Vi rekommenderar att du använder Adobe Experience Platform Launch för att implementera och hantera dina DIL- och Adobe Experience Platform Identity Service-bibliotek.

Du kan även hämta de senaste Experience Cloud- och DIL-versionerna från vår GitHub-sida. Se nedladdningslänkar nedan:

* Ladda ned [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Hämta [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Syfte med DIL {#purpose-dil}

[!UICONTROL DIL] är ett API-bibliotek. Du kan tänka dig det som en massa hjälpkod för [!DNL Adobe Audience Manager]. Du behöver inte använda det [!DNL Audience Manager], men metoderna och funktionerna [!UICONTROL DIL] innebär att du inte behöver utveckla egen kod för att skicka data till [!DNL Audience Manager]. Dessutom [!UICONTROL DIL] skiljer sig detta från det API som tillhandahålls av [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html). Tjänsten är avsedd att hantera besökaridentitet över olika [!DNL Experience Cloud] lösningar. Den [!UICONTROL DIL] är däremot utformad för att

* Anropa händelser och skicka data till [datainsamlingsservern](../reference/system-components/components-data-collection.md).
* Skicka data till [mål](../features/destinations/destinations.md).

## Hämta och implementera DIL-kod {#get-implement-dil-code}

[!UICONTROL DIL] finns kod att ladda ned **[här](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Observera att från och med version 8.0 (släppt augusti 2018)[!UICONTROL DIL]är det svårt beroende av[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), version 3.3 eller senare. Den förlitar sig på ID-tjänsten för att utlösa ID-synkroniseringar och URL-mål. Ett fel inträffar om ID-tjänsten saknas, är gammal eller inte har konfigurerats.

I stället för att arbeta med [!UICONTROL DIL] och konfigurera [!DNL Audience Manager] manuellt rekommenderar vi att du använder [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) i stället. [!DNL Adobe Experience Platform Launch] är det implementeringsverktyg som rekommenderas eftersom det förenklar koddistribution, placering och versionshantering. Läs mer om [Audience Manager-tillägget](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) i Adobe Experience Platform Launch.

Adobe Experience Platform Launch är en efterföljare till [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Exempel på samtal {#sample-code}

[!UICONTROL DIL] skickar data till [!DNL Audience Manager] i ett händelseanrop. Ett händelseanrop är en XML HTTP-begäran från din sida. Den använder en `POST` metod för att skicka data i brödtexten för begäran.

| Element för händelseanrop | Beskrivning |
|--- |--- |
| URL | DIL-händelseanrop använder följande syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Brödtext | Som visas i exemplet nedan skickar DIL data som nyckelvärdepar. Specialprefixtecken identifierar nyckelvärdepar som Audience Manager eller partnervariabler.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Se även:
* [Prefixkrav för nyckelvariabler](../features/traits/trait-variable-prefixes.md)
* [Attribut som stöds för DCS API-anrop](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Relaterade länkar

* [DIL-användningsexempel och kodexempel](/help/using/dil/dil-use-cases.md)
* [DIL-metoder på klassnivå](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-metoder på förekomstnivå](/help/using/dil/dil-instance-methods.md)
* [DIL-moduler](/help/using/dil/dil-modules.md)
* [DIL Tools](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)