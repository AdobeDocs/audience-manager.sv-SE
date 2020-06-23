---
description: Lägg till och ta bort egenskaper i Segment Builder för att visa faktiska trait-populationer tillsammans med faktiska och uppskattade segmentpopulationsdata. Den beräknade populationsstorleken hjälper er att bygga upp rätt segment för kampanjen.
seo-description: Lägg till och ta bort egenskaper i Segment Builder för att visa faktiska trait-populationer tillsammans med faktiska och uppskattade segmentpopulationsdata. Den beräknade populationsstorleken hjälper er att bygga upp rätt segment för kampanjen.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: Trait and Segment Population Data in Segment Builder
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
translation-type: tm+mt
source-git-commit: 4d4915b9a99ddcdf321d9f4970321f5f54e057ea
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 0%

---


# [!UICONTROL Trait] och [!UICONTROL Segment] populationsdata i [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Lägg till och ta bort [!UICONTROL traits] i [!UICONTROL Segment Builder] för att se faktiska [!UICONTROL trait] populationer samt faktiska och uppskattade segmentpopulationsdata. Den beräknade populationsstorleken hjälper er att bygga upp rätt segment för kampanjen.

## [!UICONTROL Trait] Populationsdata {#trait-population-data}

[!UICONTROL Segment Builder] visar dig [!UICONTROL Total Trait Population] för den sista dagen när du lägger till ett [!UICONTROL trait] segment. Dessa data visas i det blå fältet runt det markerade området [!UICONTROL trait] i [!UICONTROL Basic View] avsnittet.

![](assets/trait-size.png)

I följande tabell definieras mått för trait-populationen:


| Mått | Beskrivning |
---------|----------|
| [!UICONTROL Total Trait Population] | Antalet unika ID:n som har den valda egenskapen i sin profil. |


## Beräkna faktiska och beräknade segmentpopulationer {#calculating-real-estimated-populations}

När du skapar ett nytt segment, eller ändrar ett befintligt segment, tar det upp till 24 timmar för Audience Manager att visa resultat för faktiska realtids- och segmentpopulationer.

Audience Manager kan dock omedelbart uppskatta segmentets totala populationsstorlek och realtidsstorlek. Dessa uppskattningar baseras på historiska data som samlats in och på returresultat vid 95% konfidensintervall.

![](assets/confidence-interval.png)

I [!UICONTROL Segment Builder]visas ett blått fält i de uppskattade populationsdiagrammen med de möjliga övre och nedre intervallen för segmentstorleken. Även om tidigare prestanda inte garanterar framtida resultat kan de uppskattade data hjälpa dig att förstå den potentiella storleken för ett nytt eller redigerat segment.

## Översikt över segmentpopulationsdata {#segment-populations}

[!UICONTROL Segment Builder] visar att du segmenterar populationsdata när du skapar och redigerar segment.

* För uppskattade segmentpopulationsdata (realtid och totalt) uppdateras [!UICONTROL Segment Builder] inte diagrammen automatiskt när du lägger till eller tar bort egenskaper i ett segment. Klicka **[!UICONTROL Calculate Estimates]** för att visa (eller uppdatera) de beräknade populationssiffrorna.

* För faktiska (reella) segmentpopulationsdata (realtid och totalt) uppdateras segmentdiagrammet automatiskt när du läser in ett befintligt segment [!UICONTROL Segment Builder] . För nya segment, eller när du lägger till nya egenskaper i ett befintligt segment, uppdateras inte faktiska populationsdata förrän 24 timmar efter att segmentet har skapats.

![](assets/segment-data.png)

Se definitionerna nedan för mer information om beräknade och faktiska segmentpopulationsdata.

## Beräknade segmentpopulationsdata definierade {#estimated-segment-population}

I följande tabell definieras de uppskattade populationsmåtten.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Uppskattad realtidspopulation (potentiell) </span> </p> </td> 
   <td colname="col2"> <p>Det uppskattade antalet unika besökare som har setts i realtid för det angivna tidsintervallet och som var kvalificerade för segmentet när de sågs av Audience Manager. </p> <p>I <span class="wintitle"> Segment Builder</span>kan de sista 30-dagarspopulationerna för traits (<span class="wintitle"> Total Trait Populations</span>) skilja sig åt för egenskaper och segment som utvärderas i realtid. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">För egenskaper är det senaste 30-dagars måttet antalet unika användare som kvalificerat sig för den egenskapen under de senaste 30 dagarna. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">För segment som utvärderas i realtid är det senaste 30-dagarsmåttet det antal användare som har kvalificerat sig för en egenskap (i det segmentet) någon gång tidigare och som har setts igen av Audience Manager under de senaste 30 dagarna. Anta att du har en användare som kvalificerat sig för ett tåg för 60 dagar sedan och som sågs igen för 10 dagar sedan. I dessa data kommer användaren inte att läggas till i antalet trait eftersom han/hon först kvalificerade sig för trait för mer än 30 dagar sedan. De kommer dock att ingå i det sista 30-dagarsantalet för de segment som utvärderas i realtid. Det beror på att de har kvalificerat sig för segmentet inom 30-dagarsintervallet. </li>
     </ul> </p> <p> <p>Obs! Det <span class="wintitle"> beräknade realtidspopulationsmåttet</span> inkluderar inte enheter som har kvalificerats för ett segment baserat på anslutningar som tillhandahålls av en <span class="wintitle"> profilkopplingsregel</span> som använder ett <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> enhetsdiagramalternativ</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Beräknad total population (potentiell)</span> </p> </td> 
   <td colname="col2"> <p>Det uppskattade antalet unika besökare som kan finnas i ditt nya eller ändrade segment. Precis som med nästan alla uppskattningar garanterar inte tidigare prestanda framtida resultat, men du kan använda den beräknade summan för att: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Se hur många personer ett nytt eller ändrat segment kan nå när du skapar ett segment. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Justera segmentet efter dina mål. Stora segment är till exempel användbara för kampanjer som är inriktade på varumärken, och mindre segment är användbara för riktade kampanjer eller kampanjer som riktar sig om. </li> 
     </ul> </p> <p> <p>Obs! Det <span class="wintitle"> beräknade totala populationsmåttet</span> inkluderar inte enheter som har kvalificerats för ett segment baserat på anslutningar som tillhandahålls av en <span class="wintitle"> profilkopplingsregel</span> som använder ett <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> enhetsdiagramalternativ</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Befintliga (faktiska) segmentpopulationsdata har definierats {#existing-segment-population}

[!UICONTROL Profile Merge Rules] påverkar det faktiska antalet populationer i realtid och totalt antal. Dessa summor varierar beroende på om ett segment tillhör använder ett enhetsdiagramalternativ eller inte. [!UICONTROL Profile Merge Rule] Se även Alternativ för [profilsammanfogningsregel definierade](../../features/profile-merge-rules/merge-rule-definitions.md).

### Segmentpopulationsdata för [!UICONTROL Merge Rules] Utan [!UICONTROL Device Graph Option]

I följande tabell definieras faktiska värden för populationen i realtid och totalt när dina segment används av ett segment som [!UICONTROL Profile Merge Rule] skapats utan ett [!UICONTROL device graph] alternativ. Detta är inställningarna **[!UICONTROL No Device Options]** och **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Realtidspopulation (befintlig)</span> </p> </td> 
   <td colname="col2"> <p>Det faktiska antalet unika besökare som har setts i realtid för det angivna tidsintervallet och som var kvalificerade för segmentet när de sågs av Audience Manager. </p> <p>I <span class="wintitle"> Segment Builder</span>kan de sista 30-dagarspopulationerna för egenskaper (<span class="wintitle"> Total Trait Populations</span>) vara olika för egenskaper och segment som utvärderas i realtid. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">För egenskaper är det senaste 30-dagars måttet antalet unika användare som kvalificerat sig för den egenskapen under de senaste 30 dagarna. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">För segment som utvärderas i realtid är det senaste 30-dagarsmåttet det antal användare som har kvalificerat sig för en egenskap (i det segmentet) någon gång tidigare och som har setts igen av Audience Manager under de senaste 30 dagarna. Anta att du har en användare som kvalificerat sig för ett tåg för 60 dagar sedan och som sågs igen för 10 dagar sedan. I dessa data kommer användaren inte att läggas till i antalet trait eftersom han/hon först kvalificerade sig för trait för mer än 30 dagar sedan. De kommer dock att ingå i det sista 30-dagarsantalet för de segment som utvärderas i realtid. Det beror på att de har kvalificerat sig för segmentet inom 30-dagarsintervallet. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Total population (befintlig)</span> </p> </td> 
   <td colname="col2"> <p>Det faktiska antalet unika besökare som var kvalificerade för segmentet från och med i går. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Segmentera populationsdata för [!UICONTROL Merge Rules] med ett [!UICONTROL Device Graph] alternativ

I följande tabell definieras faktiska värden för populationen i realtid och totalt när dina segment används av ett [!UICONTROL Profile Merge Rule] alternativ som skapats med ett [!DNL device graph] alternativ. Det här är de enhetsalternativ som är tillgängliga för [!UICONTROL Profile Link Device Graph], [!DNL Adobe] och andra [!DNL device graph][!DNL device graph] alternativ från tredje part.


| Kolumn A | Kolumn B |
---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | Det faktiska antalet enheter som visas i realtid med aktuella profiler som, när de sammanfogas med upp till 100 andra enhetsprofiler som är kopplade till enhetsdiagrammet, innehåller egenskaperna som ska kvalificera sig för segmentet så fort det sågs av Audience Manager. |
| [!UICONTROL Total Population (Existing)] | Det totala antalet enheter med profiler som, när de sammanfogades med upp till 100 andra enhetsprofiler som är kopplade till enhetsdiagrammet, alla var kvalificerade för segmentet. |

### Begränsningar på grund av återanvändnings- och frekvensuttryck vid beräkning av segmentpopulationer

[!UICONTROL Segment Builder] har stöd för uppskattningar av segmentstorlek för segmentregler som innehåller upp till fyra recency- och frekvensuttryck. Om du väljer mer än fyra recency- och frekvensuttryck när du skapar en segmentregel visas ett fel i segmentberäkningsverktyget när populationen beräknas.

### Begränsningar på grund av [!UICONTROL Merge Rules] vid beräkning av segmentpopulationer

För närvarande finns det en känd begränsning eftersom vår uppskattning av segmentstorlek inte tar hänsyn till [!UICONTROL profile merge rules]. Titta till exempel på segment med **[!UICONTROL No Authenticated Profile + Current Device Profile]** sammanfogningsregeln[](../../features/profile-merge-rules/merge-rule-definitions.md). På grund av det sätt på vilket vi för närvarande beräknar antalet segment kommer de uppskattade populationerna att inkludera autentiserade profiler. Befintliga segmentpopulationer kommer dock att ignorera autentiserade profiler korrekt.

>[!MORELIKETHIS]
>
>* [Vanliga frågor om regler för profilsammanslagning och enhetsdiagram](../../faq/faq-profile-merge.md)
>* [Profillänk](../profile-merge-rules/merge-rules-overview.md)

