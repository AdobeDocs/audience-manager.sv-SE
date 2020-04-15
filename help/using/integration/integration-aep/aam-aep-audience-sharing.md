---
description: I den här artikeln beskrivs hur målgrupper delas mellan Audience Manager och Adobe Experience Platform.
seo-description: I den här artikeln beskrivs hur målgrupper delas mellan Audience Manager och Adobe Experience Platform.
seo-title: Målgruppsdelning mellan Audience Manager och Adobe Experience Platform
solution: Audience Manager
title: Målgruppsdelning mellan Audience Manager och Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: efc07cb0aacc31f3708c98e1c82c195c202c10ef

---


# Målgruppsdelning mellan Audience Manager och Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Kontakta din Adobe-återförsäljare för att få tillgång till den här funktionen.

## Översikt {#overview}

Tack vare funktionen för målgruppsdelning mellan Audience Manager och Adobe Experience Platform kan ni dela era egenskaper och segment i Audience Manager med Adobe Experience Platform och vice versa. Ni behöver [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html) för att kunna dela målgrupper mellan Audience Manager och Adobe Experience Platform.

Ni kan använda egenskaper och segment i Audience Manager i Experience Platform för att lägga till Audience Manager-data i era kundprofiler och dra nytta av Experience Platform- [segmenteringstjänsten](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md).

I Audience Manager kan ni använda Experience Platform-segment för datahanteringsplattformens användningsfall, till exempel:
* Lägg till [tredjepartsdata](/help/using/overview/data-types-collected.md#third-party-data) i era segment,
* [Algoritmisk modellering](/help/using/features/algorithmic-models/understanding-models.md).
* Aktivera era segment till mål som ännu inte stöds i Experience Platform- [målkatalogen](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Dessutom delas era Experience Platform-segment med andra Experience Cloud-lösningar via [bastjänsterna](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

Se tabellen nedan för en översikt över användningsfall för målgruppsdelning:

| **Användningsfall** | **Adobe Experience Platform** | **Audience Manager** | **Centrala tjänster** |
---------|----------|---------|---------
| **Målgruppsdelning** | <ul><li>Berika kundprofiler med data från Audience Manager</li><li>Använd data från Audience Manager i Experience Platform-segmentering</li></ul> | <ul><li>Lägg till data från tredje part i segment</li><li>Algoritmisk modellering</li><li>Aktivering till ytterligare destinationer</li></ul> | Använd Experience Platform-segment i andra Experience Cloud-lösningar, som Adobe Target eller Analytics. |

<br> 

## Audience Manager-segment och egenskaper i Adobe Experience Platform {#aam-segments-traits-in-aep}

Era egenskaper och segment i Audience Manager visas i Experience Platform som **målgrupper** i segmentarbetsflödet. Mer information om era Audience Manager-segment och egenskaper i Experience Platform finns i:

* [Översikt över segmenteringstjänsten](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Användarhandbok för Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/source-connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience Platform-segment i Audience Manager {#aep-segments-in-aam}

Segment som du skapar i Experience Platform visas i Audience Manager-gränssnittet som egenskaper och segment, med följande dispositionsregler:
* Fack: Regeln trait är ID:t för Experience Platform-segmentet.
* Segment: Segmentet består av den egenskap som beskrivs ovan.

### Traits {#aep-segments-as-aam-traits}

Audience Manager skapar automatiskt en egen mapp som heter **Experience Platform Traits** i ert egen varumärkesarkiv.

![Traits from Experience Platform Dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Du kan använda automatiskt skapade egenskaper i segment tillsammans med andra egenskaper. Ni kan till exempel blanda egenskaper som skapats från Experience Platform-segment med egenskaper från tredje part som förvärvats via [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

Ett exempel på ett trait som skapats automatiskt från ett Experience Platform-segment finns i skärmbilden nedan:

![Trait from Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Artikelnummer | Namn | Beskrivning |
---------|----------|---------
| 1 | Trait Type | Traits created from Experience Platform segments are created as onboard traits in Audience Manager. |
| 2 | Datakälla | Automatiskt skapat. Alla egenskaper och segment som skapas automatiskt från Experience Platform-segment lagras i datakällan **Adobe Experience Platform Audience Sharing**. |
| 3 | Integrationskod | Integrationskoden motsvarar segment-ID:t i Experience Platform. |
| 4 | Trait-uttryck | Uttrycket trait är `segID = segment ID in Experience Platform`. |
| 5 | Segment med detta fack | Ett automatiskt skapat segment som använder det här tecknet som komposition. |

<br> 

### Segment {#aep-segments-as-aam-segments}

Audience Manager skapar automatiskt en segmentmapp som kallas **Experience Platform Segments** i ert segmentlagringsutrymme.

![Skärmbild av instrumentpanelen](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ett exempel på ett segment som skapats automatiskt från ett Experience Platform-segment finns i skärmbilden nedan:

![Skärmbild av segment](/help/using/integration/integration-aep/assets/aep-segment.png)

| Artikelnummer | Namn | Beskrivning |
---------|----------|---------
| 1 | Integrationskod | Integrationskoden motsvarar segment-ID:t i Experience Platform. |
| 2 | Datakälla | Automatiskt skapat. Alla egenskaper och segment som skapas automatiskt från Experience Platform-segment lagras i datakällan **Adobe Experience Platform Audience Sharing**. |
| 3 | Sammanfogningsregel för profil | **Extern sammanfogningspolicy** anger att automatiskt skapade segment följer den sammanfogningspolicy som har konfigurerats i Experience Platform. |
| 4 | Segmentregel | Segmentet består av det trait som beskrivs i avsnittet [](#aep-segments-as-aam-traits)Traits. |
