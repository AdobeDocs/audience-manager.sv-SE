---
description: I den här artikeln beskrivs hur målgrupper delas mellan Audience Manager och Adobe Experience Platform.
seo-description: I den här artikeln beskrivs hur målgrupper delas mellan Audience Manager och Adobe Experience Platform.
seo-title: Målgruppsdelning mellan Audience Manager och Adobe Experience Platform
solution: Audience Manager
title: Målgruppsdelning mellan Audience Manager och Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: 36c820de5ccb68da6d0e519467edc869064b6e81
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 0%

---


# Målgruppsdelning mellan Audience Manager och Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Kontakta din Adobe-återförsäljare för att få tillgång till den här funktionen.

## Översikt {#overview}

Tack vare funktionen för målgruppsdelning mellan Audience Manager och Adobe Experience Platform kan ni dela med er av era Audience Manager och segment till Adobe Experience Platform och vice versa. Du behöver [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) för att kunna dela målgrupper mellan Audience Manager och Adobe Experience Platform.

Ni kan använda Audience Manager-egenskaper och segment i Experience Platform för att lägga till Audience Manager-data i era kundprofiler och dra nytta av Experience Platform:s [segmenteringstjänst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md).

I Audience Manager kan du använda Experience Platform-segment för datahantering i Platform-fall, till exempel:
* Lägg till [tredjepartsdata](/help/using/overview/data-types-collected.md#third-party-data) i era segment,
* [Algoritmisk modellering](/help/using/features/algorithmic-models/understanding-models.md).
* Aktivera dina segment för mål som ännu inte stöds i Experience Platform- [målkatalogen](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Dessutom delas era Experience Platform-segment med andra Experience Cloud-lösningar via [bastjänsterna](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Se tabellen nedan för en översikt över användningsfall för målgruppsdelning:

| **Användningsfall** | **Adobe Experience Platform** | **Audience Manager** | **Centrala tjänster** |
---------|----------|---------|---------
| **Målgruppsdelning** | <ul><li>Förbättra kundprofiler med data från Audience Manager</li><li>Använd data från Audience Manager i segmenteringen Experience Platform</li></ul> | <ul><li>Lägg till data från tredje part i segment</li><li>Algoritmisk modellering</li><li>Aktivering till ytterligare destinationer</li></ul> | Använd Experience Platform-segment i andra Experience Cloud-lösningar, som Adobe Target eller Analytics. |

<br> 

## Audience Manager segment och egenskaper i Adobe Experience Platform {#aam-segments-traits-in-aep}

Dina Audience Manager-egenskaper och -segment visas i Experience Platform som **målgrupper** i segmentarbetsflödet. Mer information om segment och egenskaper för Audience Manager i Experience Platform finns i:

* [Översikt över segmenteringstjänsten](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Användarhandbok för Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience Platform segment i Audience Manager {#aep-segments-in-aam}

Segment som du skapar i Experience Platform visas i Audience Manager som egenskaper och segment, med följande dispositionsregler:
* Fack: Regeln trait är Experience Platform-segmentets ID.
* Segment: Segmentet består av den egenskap som beskrivs ovan.

### Traits {#aep-segments-as-aam-traits}

Audience Manager skapar automatiskt en trait-mapp som heter **Experience Platform Traits** i ditt trait-lagringsutrymme.

![Traits from Experience Platform dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Du kan använda automatiskt skapade egenskaper i segment tillsammans med andra egenskaper. Du kan till exempel blanda egenskaper som skapats från Experience Platform-segment med egenskaper från tredje part som förvärvats via [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Ett exempel på ett trait som skapats automatiskt från ett Experience Platform-segment finns i skärmbilden nedan:

![Fälla från Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Artikelnummer | Namn | Beskrivning |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Traits created from Experience Platform segments are created as onboard traits in Audience Manager. |
| 2 | [!UICONTROL Data Source] | Automatiskt skapat. Alla egenskaper och segment som skapas automatiskt från Experience Platform-segment lagras i datakällan **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Integrationskoden motsvarar segment-ID:t i Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | Uttrycket trait är `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Ett automatiskt skapat segment som använder det här tecknet som komposition. |

<br> 

### Segment {#aep-segments-as-aam-segments}

Audience Manager skapar automatiskt en segmentmapp som kallas **Experience Platform Segments** i segmentlagringen.

![Skärmbild av instrumentpanelen](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ett exempel på ett segment som skapats automatiskt från ett Experience Platform-segment finns i skärmbilden nedan:

![Skärmbild av segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Artikelnummer | Namn | Beskrivning |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | Integrationskoden motsvarar segment-ID:t i Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatiskt skapat. Alla egenskaper och segment som skapas automatiskt från Experience Platform-segment lagras i datakällan **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** anger att automatiskt skapade segment följer den sammanfogningsprincip som har konfigurerats i Experience Platform. |
| 4 | [!UICONTROL Segment Rule] | Segmentet består av det trait som beskrivs i avsnittet [](#aep-segments-as-aam-traits)Traits. |

## Stöd för dataexportkontroll i Audience Manager i Experience Platform {#aam-data-export-control-in-aep}

För att se till att dataanvändningen efterlevs i Experience Platform måste alla tillämpliga datauppsättningar och fält förses med lämpliga [dataanvändningsetiketter](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html). Dessutom måste [dataanvändningsprinciper](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) aktiveras för specifika marknadsföringsåtgärder mot dessa etiketter, enligt riktlinjerna i [ramverket](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)för märkning och verkställighet av dataanvändning (DULE).

I målgruppsdelningsprocessen mellan Audience Manager och Experience Platform översätts alla dataexportkontroller som har tillämpats på Audience Manager-segment till likvärdiga etiketter och marknadsföringsåtgärder som har godkänts av Experience Platform Data Governance, och vice versa.

>[!NOTE] Mer allmän information om dataexportkontroller finns i dokumentationen [för](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)dataexportkontroller.
Det här dokumentet innehåller en referens för hur specifika dataexportkontroller för Audience Manager mappas till dataanvändningsetiketter och marknadsföringsåtgärder i Platform.

### Dataexportkontroller till dataanvändningsetiketter

I följande tabell visas hur specifika dataexportkontroller mappas till kända dataanvändningsetiketter:

| Dataexportkontroll | Dataanvändningsetikett |
| --- | --- |
| Kan inte användas med personligt identifierbar information | C3: Data kan inte kombineras eller på annat sätt användas med direkt identifierbar information |
| Kan inte användas för annonsanpassning utanför webbplatsen | C5: Data kan inte användas för intressebaserad, övergripande målinriktning av innehåll eller annonser |
| Kan inte användas för annonsanpassning på plats | C6: Data kan inte användas för annonsanpassning på plats |
| Kan inte användas för anpassning på plats | C7: Data kan inte användas för målanpassning av innehåll på plats |

### Dataexportkontroller för marknadsföringsåtgärder

Följande tabell visar hur specifika dataexportetiketter mappas till kända marknadsföringsåtgärder:

| Dataexportetikett | Marknadsföringsåtgärd |
| --- | --- |
| Denna destination kan möjliggöra en kombination med personligt identifierbar information (PII) | Kombinera med PII |
| Den här destinationen kan användas för annonsinriktning utanför webbplatsen | Målgruppsövergripande |
| Det här målet kan användas för annonsinriktning på plats | Annonsering på plats |
| Det här målet kan användas för anpassning av annonser på plats | Personalisering på plats |

## Förstå skillnaderna i segmentbefolkning mellan Audience Manager och Experience Platform

Antalet segmentpopulationer kan variera mellan Audience Manager och Experience Platform. Segmentnummer för liknande eller identiska målgrupper bör vara nära, men skillnaderna i populationer kan bero på:

* Körtider för segmenteringsjobb. Audience Manager kör ett segmenteringsjobb som uppdaterar siffrorna i gränssnittet en gång om dagen. Det här jobbet är sällan anpassat till segmenteringsjobben i Experience Platform.
* [Regler](/help/using/features/profile-merge-rules/merge-rules-overview.md) för profilsammanslagning i Audience Manager och [sammanfogningsprinciper](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) i Experience Platform fungerar olika, och det identitetsdiagram som används för varje regel varierar. På grund av detta förväntas vissa skillnader mellan segmentpopulationerna.

>[!MORELIKETHIS]
>
>* [Översikt över segmenteringstjänsten](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Användarhandbok för Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)