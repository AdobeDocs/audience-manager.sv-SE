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
source-wordcount: '809'
ht-degree: 1%

---

# Referens för kvalificering av traits och segment {#trait-qualification-reference}

Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager, beroende på trait-typ. Se [Trait Qualification by Trait Type](#trait-type) om du vill ha mer information om kvalificering av trait-typ.

Mer information finns i [Population av realtidssegment och total segmentpopulation](#real-time-segment) om du vill ha information om segmentkvalificering.



## Trait Qualification by Trait Type {#trait-type}

| Trait Type | Kvalificeringsvillkor |
|---|---|
| Regelbaserade egenskaper | Trait-kvalificering sker i realtid när användare kvalificerar sig för en egenskap i sin webbläsare. Användarna börjar kvalificera sig för en regelbaserad trait ungefär 4 timmar efter att du gjort det [skapa EGENSKAPEN](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) i användargränssnittet. Med hjälp av regelbaserade egenskaper kan du använda [senaste och frekvenser](../segments/recency-and-frequency.md) kontroller för annonsfrekvenser och andra användningsfall. |
| Onboardtåg | Trait-kvalificering inträffar efter att en inkommande fil har bearbetats, dvs. den inkommande filen är [importerad till Audience Manager](../../faq/faq-inbound-data-ingestion.md) och det är när lärandekompetensen inträffar. Du bör vänta cirka 4 timmar efter att du har skapat en ny egenskap innan du överför en inkommande fil för bearbetning. För praktikanter är det högsta antalet kvalifikationer för en användarprofil 1. |
| Algoritmiska egenskaper | För algoritmiska egenskaper är det högsta antalet kvalifikationer för en användarprofil 1. |
| Mappegenskaper | En mappegenskap sammanfattar egenskaperna för de egenskaper den innehåller. Läs [Mappegenskaper: Om](about-folder-traits.md) för mer information. |
| Aktiva traits för målgrupp och traits som synkroniserats med datakälla | An [!UICONTROL Active Audience] trait innehåller alla enheter som hanteras i ditt Audience Manager-konto. [!UICONTROL Data Source Synced Traits] spåra alla användare som är associerade med en datakälla. Läs mer om [Synkroniserade egenskaper för aktiv målgrupp och datakälla](client-activity-synced-audience-traits.md). |

## Unika Trait-realiteter och total Trait-population {#unique-trait-realizations}

![unique-trait-realization](assets/trait-graph.png)

Beroende på vilken typ av resultat du vill att diagrammet ska visas (filtrerat efter [!UICONTROL Device ID] eller [!UICONTROL Cross-Device ID]) har mätvärdena olika betydelse:

Vid filtrering av resultaten med [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] är antalet anonyma enhetsbesökare som har lagt till egenskapen i sin profil inom olika tidsintervall.
* [!UICONTROL Total Trait Population] är antalet anonyma enhetsbesökare som har den här egenskapen i sin profil.

Vid filtrering av resultaten med [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] är antalet autentiserade besökare som har lagt till egenskapen i sin profil, inom olika tidsintervall.
* [!UICONTROL Total Trait Population] är antalet autentiserade besökare som har denna egenskap i sin profil.

Tänk på siffrorna på det här sättet. I bilden ovan går du till [Trait Details](../../features/traits/trait-details-page.md) 90 173 representerar antalet aktiva enheter som besökte dina egenskaper i går. The [!UICONTROL Total Trait Population] av 55 757 representerar det antal användare som för närvarande är kvalificerade för den här egenskapen. The [!UICONTROL Total Trait Population] illustrationen är avsedd att visa det totala antalet användare som kan användas för segmentering/målinriktning. Vanligtvis ingår användarna i ett spår i 120 dagar.

Eftersom vi utför två olika beräkningsjobb för att beräkna de två populationerna, [!UICONTROL Total Trait Population] alltid släpar efter [!UICONTROL Unique Trait Realizations] med 24 timmar. I diagrammet ovan ser du cirka 90 400 [!UICONTROL Unique Trait Realizations] och [!UICONTROL Total Trait Population] cirka 90 300 för 5 februari. Profilerna på 90 400 läggs till i [!UICONTROL Total Trait Population] följande dag.

Om du fick 10 000 besökare just nu skulle de dyka upp i morgondagens [!UICONTROL Unique Trait Realizations], men visas bara 24 timmar senare i [!UICONTROL Total Trait Population].

Alla förändringar i intäktsrealisationen återspeglas i segmentpopulationerna.

## Population av realtidssegment och total segmentpopulation {#real-time-segment}

![unique-trait-realization](assets/segment-graph.png)

The [!UICONTROL Real-time Segment Population] räknar antalet enheter som har kvalificerat sig för det valda segmentet och som har nått dina egenskaper inom det valda tidsintervallet.

The [!UICONTROL Total Segment Population] räknar antalet enheter som har kvalificerats för det valda segmentet inom det valda tidsintervallet. The [!UICONTROL 1 Day] rapporten representerar det senaste antalet segmentpopulationer.

Tänk på siffrorna på det här sättet. I bilden ovan går du till [Segmentinformation](../../features/segments/segment-summary-view.md) 9 993 representerar antalet aktiva enheter som besökte dina egenskaper i går och som är kvalificerade för segmentet. The [!UICONTROL Total Segment Population] av 699,532 representerar det totala antalet enheter som för närvarande är kvalificerade för detta segment. The [!UICONTROL Total Segment Population] illustrationen är avsedd att visa det totala antalet enheter som kan användas för segmentering/målinriktning.

Eftersom vi utför två olika beräkningsjobb för att beräkna de två populationerna, [!UICONTROL Total Segment Population] alltid släpar efter [!UICONTROL Real-time Segment Population] med 24 timmar. I diagrammet ovan visas 8 116 [!UICONTROL Real-time Segment Population] och [!UICONTROL Total Segment Population] av 742 000 för andra februari. 8 116-profilerna läggs till i [!UICONTROL Total Segment Population] följande dag.

Om du fick 10 000 besökare just nu skulle de dyka upp i morgondagens [!UICONTROL Real-time Segment Population], men visas bara 24 timmar senare i [!UICONTROL Total Segment Population].

## Trait Qualification Limit {#trait-qualification-limit}

Vi tillämpar en gräns på 150 000 praktikkvalifikationer för varje användarprofil, oavsett om det är en autentiserad profil ([DPUUID](../../reference/ids-in-aam.md)) eller ett enhets-ID ([UUID](../../reference/ids-in-aam.md)). Observera att även om DPUID:n är unika för en specifik instans av [!DNL Audience Manager], delas UUID:n i [!DNL Audience Manager] plattform. För [!UICONTROL UUID]Vi inför en rättvisepolicy när vi lagrar kvalifikationer. En algoritm säkerställer att en lika stor del av [!UICONTROL UUID] profilen är tillgänglig för alla instanser av [!DNL Audience Manager].
