---
description: Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager, beroende på trait-typ. Se tabellen nedan för detaljerad information om kvalificering av trait.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager, beroende på trait-typ. Se tabellen nedan för detaljerad information om kvalificering av trait.
seo-title: Referens för dragningskvalitet
solution: Audience Manager
title: Referens för dragningskvalitet
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 0%

---


# Referens för egenskaper för trait och segment {#trait-qualification-reference}

Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager, beroende på trait-typ. Se [Trait Qualification by Trait Type](#trait-type) för mer information om kvalificering av trait-typ.

Mer information om segmentkvalificering finns i Population i [realtidssegment och Population](#real-time-segment) i totalt segment.



## Trait Qualification by Trait Type {#trait-type}

| Trait Type | Kvalificeringsvillkor |
|---|---|
| Regelbaserade egenskaper | Trait-kvalificering sker i realtid när användare kvalificerar sig för en egenskap i sin webbläsare. Användarna börjar kvalificera sig för en regelbaserad trait ungefär 4 timmar efter att du [har skapat egenskapen](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) i användargränssnittet. Regelbaserade egenskaper gör att du kan använda [kontroller för senaste](../segments/recency-and-frequency.md) och frekventa annonser och andra användningsfall. |
| Onboardtåg | Trait-kvalificering inträffar efter att en inkommande fil har bearbetats, dvs. den inkommande filen [importeras till Audience Manager](../../faq/faq-inbound-data-ingestion.md) och det är när trait-kvalificeringen inträffar. Du bör vänta cirka 4 timmar efter att du har skapat en ny egenskap innan du överför en inkommande fil för bearbetning. För praktikanter är det högsta antalet kvalifikationer för en användarprofil 1. |
| Algoritmiska egenskaper | För algoritmiska egenskaper är det högsta antalet kvalifikationer för en användarprofil 1. |
| Mappegenskaper | En mappegenskap sammanfattar egenskaperna för de egenskaper den innehåller. Läser [mappegenskaper: Om](about-folder-traits.md) du vill ha mer information. |
| Synkroniserade egenskaper för aktiv målgrupp och datakälla | En [!UICONTROL Active Audience] egenskap innehåller alla enheter som hanteras i ditt Audience Manager-konto. [!UICONTROL Data Source Synced Traits] spåra alla användare som är associerade med en datakälla. Läs mer om [Active Audience Traits och Synced Traits](client-activity-synced-audience-traits.md)för datakälla. |

## Unika Trait-realiteter och total Trait-population {#unique-trait-realizations}

![unique-trait-realization](assets/trait-graph.png)

Beroende på vilken typ av resultat du vill att diagrammet ska visa (filtreras efter [!UICONTROL Device ID] eller [!UICONTROL Cross-Device ID]) har måtten olika innebörd:

Vid filtrering av resultaten med [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] är antalet anonyma enhetsbesökare som har lagt till egenskapen i sin profil inom olika tidsintervall.
* [!UICONTROL Total Trait Population] är antalet anonyma enhetsbesökare som har den här egenskapen i sin profil.

Vid filtrering av resultaten med [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] är antalet autentiserade besökare som har lagt till egenskapen i sin profil, inom olika tidsintervall.
* [!UICONTROL Total Trait Population] är antalet autentiserade besökare som har denna egenskap i sin profil.

Tänk på siffrorna på det här sättet. I bilden ovan representerar 90 173 antalet aktiva enheter från vyn [Trait Details](../../features/traits/trait-details-page.md) (Trait Details) som besökte dina egenskaper i går. Värdet [!UICONTROL Total Trait Population] på 55 757 representerar det antal användare som för närvarande är kvalificerade för den här egenskapen. Bilden är avsedd att visa det totala antalet användare som kan användas för segmentering/målinriktning. [!UICONTROL Total Trait Population] Vanligtvis ingår användarna i ett spår i 120 dagar.

Eftersom vi utför två olika beräkningsjobb för att beräkna de två populationerna släpar de [!UICONTROL Total Trait Population] alltid efter [!UICONTROL Unique Trait Realizations] med 24 timmar. I diagrammet ovan ser du cirka 90 400 [!UICONTROL Unique Trait Realizations] och cirka 90 300 [!UICONTROL Total Trait Population] för 5 februari. Profilerna på 90 400 läggs till [!UICONTROL Total Trait Population] följande dag.

För att ytterligare driva hem poängen skulle de dyka upp i morgondagens [!UICONTROL Unique Trait Realizations]om du fick 10 000 besökare, men skulle bara dyka upp 24 timmar senare på [!UICONTROL Total Trait Population].

Alla förändringar i intäktsrealisationen återspeglas i segmentpopulationerna.

## Population av segment i realtid och total segmentpopulation {#real-time-segment}

![unique-trait-realization](assets/segment-graph.png)

Antalet enheter [!UICONTROL Real-time Segment Population] som är kvalificerade för det valda segmentet och som har nått dina egenskaper inom det valda tidsintervallet.

Antalet enheter [!UICONTROL Total Segment Population] som är kvalificerade för det valda segmentet inom det valda tidsintervallet räknas. Rapporten visar det senaste antalet [!UICONTROL 1 Day] segmentpopulationer.

Tänk på siffrorna på det här sättet. I bilden ovan visar vyn [Segmentdetaljer](../../features/segments/segment-summary-view.md) 9 993 antalet aktiva enheter som besökte dina egenskaper i går och som är kvalificerade för segmentet. Värdet [!UICONTROL Total Segment Population] på 699 532 representerar det totala antalet enheter som för närvarande är kvalificerade för det här segmentet. Bilden är avsedd att visa det totala antalet enheter som kan användas för segmentering/målinriktning. [!UICONTROL Total Segment Population]

Eftersom vi utför två olika beräkningsjobb för att beräkna de två populationerna släpar de [!UICONTROL Total Segment Population] alltid efter [!UICONTROL Real-time Segment Population] med 24 timmar. I diagrammet ovan ser du 8 116 [!UICONTROL Real-time Segment Population] [!UICONTROL Total Segment Population] och 742 000 som den andra februari. De 8 116 profilerna läggs till [!UICONTROL Total Segment Population] följande dag.

För att ytterligare driva hem poängen skulle de dyka upp i morgondagens [!UICONTROL Real-time Segment Population]om du fick 10 000 besökare, men skulle bara dyka upp 24 timmar senare på [!UICONTROL Total Segment Population].

## Trait Qualification Limit {#trait-qualification-limit}

Vi tillämpar en gräns på 150 000 trait-kvalifikationer för varje användarprofil, oavsett om det är en autentiserad profil ([DPUUID](../../reference/ids-in-aam.md)) eller ett enhets-ID ([UID](../../reference/ids-in-aam.md)). Observera att även om DPUUID:n är unika för en specifik instans av [!DNL Audience Manager], delas UUID:n över [!DNL Audience Manager] plattformen. För [!UICONTROL UUID]övrigt inför vi en rättvisepolicy när vi lagrar kvalifikationer. En algoritm säkerställer att en lika stor del av [!UICONTROL UUID] profilen är tillgänglig för alla instanser av [!DNL Audience Manager].

