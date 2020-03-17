---
description: Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager beroende på trait-typ. Se tabellen nedan för detaljerad information om kvalificering av trait.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager beroende på trait-typ. Se tabellen nedan för detaljerad information om kvalificering av trait.
seo-title: Referens för dragningskvalitet
solution: Audience Manager
title: Referens för dragningskvalitet
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 2f8662aba70254e550bc15417463c3c06492a9d5

---


# Referens för dragningskvalitet {#trait-qualification-reference}

Trait-kvalificering, eller trait-implementering, behandlas annorlunda i Audience Manager beroende på trait-typ. Se tabellen nedan för detaljerad information om kvalificering av trait.

## Trait Qualification by Trait Type {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Trait-typ </th> 
   <th colname="col2" class="entry"> Kvalificeringskriterier </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Regelbaserade egenskaper </p> </td> 
   <td colname="col2"> <p>Trait-kvalificering sker i realtid när användare kvalificerar sig för en egenskap i sin webbläsare. Användarna börjar kvalificera sig för en regelbaserad egenskap cirka 4 timmar efter att du har <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> skapat egenskapen</a> i användargränssnittet. </p> <p>Regelbaserade egenskaper gör att du kan använda <a href="../../features/segments/recency-and-frequency.md"> frekvenskontroller</a> för annonsfrekvenser och andra användningsfall. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Onboardtåg </p> </td> 
   <td colname="col2"> <p>Trait-kvalificering inträffar efter att en inkommande fil har bearbetats, dvs. den inkommande filen <a href="../../faq/faq-inbound-data-ingestion.md"> importeras till Audience Manager</a> och det är när trait-kvalificeringen inträffar. Du bör vänta cirka 4 timmar efter att du har skapat en ny egenskap innan du överför en inkommande fil för bearbetning.  </p> <p> För praktikanter är det högsta antalet kvalifikationer för en användarprofil 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algoritmiska egenskaper </p> </td> 
   <td colname="col2"> <p>För algoritmiska egenskaper är det högsta antalet kvalifikationer för en användarprofil 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappegenskaper </p> </td> 
   <td colname="col2"> <p>En mappegenskap sammanfattar egenskaperna för de egenskaper den innehåller. </p> <p>Läser <a href="../../features/traits/about-folder-traits.md"> mappegenskaper: Om</a> du vill ha mer information. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Synkroniserade egenskaper för aktiv målgrupp och datakälla </p> </td> 
   <td colname="col2"> <p>En <span class="wintitle"> Active Audience</span> -egenskap innehåller alla enheter som hanteras i ditt <span class="wintitle"> Audience Manager</span> -konto. </p> <p><span class="wintitle"> Synkroniserade egenskaper</span> för datakälla spårar alla användare som är associerade med en datakälla. </p> <p>Läs mer om Active Audience Traits och Synced Traits (Synkroniserade egenskaper för <a href="../../features/traits/client-activity-synced-audience-traits.md"> aktiv målgrupp) och Data Source</a>. </p> </td>
  </tr>
 </tbody>
</table>

## Unika Trait-realiteter och total Trait-population {#unique-trait-realizations}

![](assets/utr-ttp1.png)

Antalet **[!UICONTROL Unique Trait Realizations]** besökare som har lagt till egenskapen i sin profil, inom olika tidsintervall.

Värdet anger **[!UICONTROL Total Trait Population]** antalet besökare som har den här egenskapen i sin profil.

Tänk på siffrorna på det här sättet. I bilden ovan representerar 181 antalet aktiva enheter från vyn [Trait Details](../../features/traits/trait-details-page.md) (Trait Details) som besökte dina egenskaper i går. Värdet [!UICONTROL Total Trait Population] på 1 595 representerar det antal användare som för närvarande är kvalificerade för den här egenskapen. Bilden är avsedd att visa det totala antalet användare som kan användas för segmentering/målinriktning. [!UICONTROL Total Trait Population] Vanligtvis ingår användarna i ett spår i 120 dagar.

Eftersom vi utför två olika beräkningsjobb för att beräkna de två populationerna släpar de [!UICONTROL Total Trait Population] alltid efter [!UICONTROL Unique Trait Realizations] med 24 timmar. I diagrammet ovan ser du 175 [!UICONTROL Unique Trait Realizations] och 6 [!UICONTROL Total Trait Population] för 11 februari. 175-profilerna läggs till [!UICONTROL Total Trait Population] följande dag.

För att ytterligare driva hem poängen skulle de dyka upp i morgondagens [!UICONTROL Unique Trait Realizations]om du fick 10 000 besökare, men skulle bara dyka upp 24 timmar senare på [!UICONTROL Total Trait Population].

## Trait Qualification Limit {#trait-qualification-limit}

Vi tillämpar en gräns på 150 000 trait-kvalifikationer för varje användarprofil, oavsett om det är en autentiserad profil ( [DPUUID](../../reference/ids-in-aam.md)) eller ett enhets-ID ( [UID](../../reference/ids-in-aam.md)). Observera att även om DPUUID:n är unika för en specifik instans av [!DNL Audience Manager], delas UUID:n över [!DNL Audience Manager] plattformen. För [!UICONTROL UUID]övrigt inför vi en rättvisepolicy när vi lagrar kvalifikationer. En algoritm säkerställer att en lika stor del av [!UICONTROL UUID] profilen är tillgänglig för alla instanser av [!DNL Audience Manager].
