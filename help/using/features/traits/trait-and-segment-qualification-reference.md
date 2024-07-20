---
description: Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager, beroende på trait-typ. Se tabellen nedan för detaljerad information om kvalificering av trait.
keywords: Trait-kvalificering,Trait Realization,Unique Trait Realizations,UTR,Total Trait Population,TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Referens för dragningskvalitet
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Referens för egenskaper för trait och segment {#trait-qualification-reference}

Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager, beroende på trait-typ. Mer information om kvalificering av trait-typ finns i [Trait Qualification by Trait Type](#trait-type).

Mer information om segmentkvalificering finns i [Population för realtidssegment och populering av totalt segment](#real-time-segment) .



## Trait Qualification by Trait Type {#trait-type}

| Trait Type | Kvalificeringsvillkor |
|---|---|
| Regelbaserade egenskaper | Trait-kvalificering sker i realtid när användare kvalificerar sig för en egenskap i sin webbläsare. Dina användare kvalificerar sig för en regelbaserad trait ungefär 4 timmar efter att du [har skapat trait](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) i gränssnittet. Regelbaserade egenskaper gör att du kan använda [nyligen använda- och frekvensreglage](../segments/recency-and-frequency.md) för annonsfrekvenser och andra användningsfall. |
| Onboardtåg | Trait-kvalificering inträffar efter att en inkommande fil har bearbetats, dvs. den inkommande filen [importeras till Audience Manager](../../faq/faq-inbound-data-ingestion.md) och det är när trait-kvalificeringen inträffar. Du bör vänta cirka 4 timmar efter att du har skapat en ny egenskap innan du överför en inkommande fil för bearbetning. För praktikanter är det högsta antalet kvalifikationer för en användarprofil 1. |
| Algoritmiska egenskaper | För algoritmiska egenskaper är det högsta antalet kvalifikationer för en användarprofil 1. |
| Mappegenskaper | En mappegenskap sammanfattar egenskaperna för de egenskaper den innehåller. Läs [Mappegenskaper: Om](about-folder-traits.md) om du vill ha mer information. |
| Aktiva målgrupper och Source Synced Traits (datakunskaper) | En [!UICONTROL Active Audience]-egenskap innehåller alla enheter som hanteras i ditt Audience Manager-konto. [!UICONTROL Data Source Synced Traits] spårar alla användare som är associerade med en datakälla. Läs mer om [Active Audience Traits och Data Source Synced Traits](client-activity-synced-audience-traits.md). |

## Unika Trait-realiteter och total Trait-population {#unique-trait-realizations}

![unique-trait-realization](assets/trait-graph.png)

Beroende på vilken typ av resultat du vill att diagrammet ska visa (filtreras med [!UICONTROL Device ID] eller [!UICONTROL Cross-Device ID]) har måtten olika innebörd:

Vid filtrering av resultaten efter [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] är antalet anonyma enhetsbesökare som har lagt till egenskapen i sin profil inom olika tidsintervall.
* [!UICONTROL Total Trait Population] är antalet anonyma enhetsbesökare som har den här egenskapen i sin profil.

Vid filtrering av resultaten efter [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] är antalet autentiserade besökare som har lagt till egenskapen i sin profil, inom olika tidsintervall.
* [!UICONTROL Total Trait Population] är antalet autentiserade besökare som har den här egenskapen i sin profil.

Tänk på siffrorna på det här sättet. I bilden ovan visar vyn [Anpassa detaljer](../../features/traits/trait-details-page.md) 90 173 antalet aktiva enheter som besökte dina egenskaper i går. [!UICONTROL Total Trait Population] på 55 757 representerar det antal användare som för närvarande är kvalificerade för den här egenskapen. Siffran [!UICONTROL Total Trait Population] är avsedd att visa det totala antalet användare som kan användas för segmentering/målinriktning. Vanligtvis ingår användarna i ett spår i 120 dagar.

Eftersom vi kör två olika beräkningsjobb för att beräkna de två populationerna släpar [!UICONTROL Total Trait Population] alltid efter [!UICONTROL Unique Trait Realizations] med 24 timmar. I diagrammet ovan ser du cirka 90 400 [!UICONTROL Unique Trait Realizations] och [!UICONTROL Total Trait Population] cirka 90 300 för 5 februari. 90 400 profiler läggs till i [!UICONTROL Total Trait Population] följande dag.

Om du vill flytta fram poängen till nästa gång skulle de dyka upp i morgondagens [!UICONTROL Unique Trait Realizations] om du fick en topp på 10 000 besökare just nu, men bara skulle visas 24 timmar senare i [!UICONTROL Total Trait Population].

Alla förändringar i intäktsrealisationen återspeglas i segmentpopulationerna.

## Population av segment i realtid och total segmentpopulation {#real-time-segment}

![unique-trait-realization](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population] räknar antalet enheter som har kvalificerats för det valda segmentet och som har nått dina egenskaper inom det valda tidsintervallet.

[!UICONTROL Total Segment Population] räknar antalet enheter som har kvalificerats för det valda segmentet inom det valda tidsintervallet. Rapporten [!UICONTROL 1 Day] representerar det senaste antalet segmentpopulationer.

Tänk på siffrorna på det här sättet. I bilden ovan representerar 9 993 antalet aktiva enheter från vyn [Segmentdetaljer](../../features/segments/segment-summary-view.md), som besökte dina egenskaper i går och som är kvalificerade för segmentet. [!UICONTROL Total Segment Population] av 699,532 representerar det totala antalet enheter som är kvalificerade för det här segmentet. Siffran [!UICONTROL Total Segment Population] är avsedd att visa det totala antalet enheter som kan användas för segmentering/målinriktning.

Eftersom vi kör två olika beräkningsjobb för att beräkna de två populationerna släpar [!UICONTROL Total Segment Population] alltid efter [!UICONTROL Real-time Segment Population] med 24 timmar. I diagrammet ovan visas 8 116 [!UICONTROL Real-time Segment Population] och [!UICONTROL Total Segment Population] 742 000 för andra februari. De 8 116 profilerna läggs till i [!UICONTROL Total Segment Population] följande dag.

Om du vill flytta fram poängen till nästa gång skulle de dyka upp i morgondagens [!UICONTROL Real-time Segment Population] om du fick en topp på 10 000 besökare just nu, men bara skulle visas 24 timmar senare i [!UICONTROL Total Segment Population].

## Trait Qualification Limit {#trait-qualification-limit}

Vi tillämpar en begränsning på 150 000 trait-kvalifikationer för varje användarprofil, oavsett om det är en autentiserad profil ([DPUID](../../reference/ids-in-aam.md)) eller ett enhets-ID ([UID](../../reference/ids-in-aam.md)). Observera att även om DPUUID:n är unika för en specifik instans av [!DNL Audience Manager], delas UUID:n över [!DNL Audience Manager]-plattformen. För [!UICONTROL UUID]-talet tillämpar vi en rättvisepolicy när vi lagrar praktikkvalifikationer. En algoritm ser till att en lika stor del av profilen [!UICONTROL UUID] är tillgänglig för varje instans av [!DNL Audience Manager].
