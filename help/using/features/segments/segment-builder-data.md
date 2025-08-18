---
description: Lägg till och ta bort egenskaper i Segment Builder för att visa faktiska trait-populationer tillsammans med faktiska och uppskattade segmentpopulationsdata. Den beräknade populationsstorleken hjälper er att bygga upp rätt segment för kampanjen.
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: Trait and Segment Population Data in Segment Builder
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 0%

---

# [!UICONTROL Trait] och [!UICONTROL Segment] Populationsdata i [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Lägg till och ta bort [!UICONTROL traits] i [!UICONTROL Segment Builder] om du vill visa faktiska [!UICONTROL trait] populationer tillsammans med faktiska och beräknade data för segmentpopulationen. Den beräknade populationsstorleken hjälper er att bygga upp rätt segment för kampanjen.

## [!UICONTROL Trait] populationsdata {#trait-population-data}

[!UICONTROL Segment Builder] visar [!UICONTROL Total Trait Population] för den sista dagen när du lägger till en [!UICONTROL trait] i ett segment. Dessa data visas i det blå fältet runt din valda [!UICONTROL trait] i avsnittet [!UICONTROL Basic View].

![](assets/trait-size.png)

I följande tabell definieras mått för trait-populationen:


| Mått | Beskrivning |
|---------|----------|
| [!UICONTROL Total Trait Population] | Antalet unika ID:n som har den valda egenskapen i sin profil. |


## Beräkna faktiska och beräknade segmentpopulationer {#calculating-real-estimated-populations}

När du skapar ett nytt segment, eller ändrar ett befintligt segment, tar det upp till 24 timmar för Audience Manager att visa resultat för den faktiska realtids- och segmentpopulationen.

Audience Manager kan dock omedelbart beräkna segmentets totala populationsstorlek och realtidsstorlek. Dessa uppskattningar baseras på historiska data som samlats in och på returresultat vid 95% konfidensintervall.

![](assets/confidence-interval.png)

I [!UICONTROL Segment Builder] visar ett blått fält i de beräknade populationsdiagrammen de möjliga övre och nedre intervallen för segmentstorleken. Även om tidigare prestanda inte garanterar framtida resultat kan de uppskattade data hjälpa dig att förstå den potentiella storleken för ett nytt eller redigerat segment.

## Översikt över segmentpopulationsdata {#segment-populations}

[!UICONTROL Segment Builder] visar att du segmenterar populationsdata när du skapar och redigerar segment.

* För beräknade segmentpopulationsdata (realtid och totalt) uppdaterar [!UICONTROL Segment Builder] inte diagrammen automatiskt när du lägger till eller tar bort egenskaper i ett segment. Klicka på **[!UICONTROL Calculate Estimates]** om du vill visa (eller uppdatera) de beräknade populationssiffrorna.

* För faktiska (reella) segmentpopulationsdata (realtid och totalt) uppdaterar [!UICONTROL Segment Builder] segmentdiagrammet automatiskt när du läser in ett befintligt segment. För nya segment, eller när du lägger till nya egenskaper i ett befintligt segment, uppdateras inte faktiska populationsdata förrän 24 timmar efter att segmentet har skapats.

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
   <td colname="col1"> <p> <span class="wintitle"> beräknad realtidspopulation (möjlig) </span> </p> </td> 
   <td colname="col2"> <p>Uppskattat antal unika besökare som har setts i realtid för det angivna tidsintervallet och som var kvalificerade för segmentet när de sågs av Audience Manager. </p> <p>I <span class="wintitle"> Segment Builder </span> kan de sista 30-dagarspopulationerna för egenskaper (<span class="wintitle"> Total Trait Populations </span>) vara olika för egenskaper och segment som utvärderats i realtid. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">För egenskaper är det senaste 30-dagars måttet antalet unika användare som kvalificerat sig för den egenskapen under de senaste 30 dagarna. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">För segment som utvärderas i realtid är det senaste 30-dagarsmåttet det antal användare som har kvalificerat sig för en egenskap (i det segmentet) någon gång tidigare och som har setts igen av Audience Manager under de senaste 30 dagarna. Anta att du har en användare som kvalificerat sig för ett tåg för 60 dagar sedan och som sågs igen för 10 dagar sedan. I dessa data kommer användaren inte att läggas till i antalet trait eftersom han/hon först kvalificerade sig för trait för mer än 30 dagar sedan. De kommer dock att ingå i det sista 30-dagarsantalet för de segment som utvärderas i realtid. Det beror på att de har kvalificerat sig för segmentet inom 30-dagarsintervallet. </li>
     </ul> </p> <p> <p>Obs! Måttet <span class="wintitle"> för beräknad realtidspopulation </span> inkluderar inte enheter som har kvalificerats för ett segment baserat på anslutningar som tillhandahålls av en <span class="wintitle"> profilkopplingsregel </span> som använder ett <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> enhetsdiagramalternativ </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> beräknad total population (potentiell)</span> </p> </td> 
   <td colname="col2"> <p>Det uppskattade antalet unika besökare som kan finnas i ditt nya eller ändrade segment. Precis som med nästan alla uppskattningar garanterar inte tidigare prestanda framtida resultat, men du kan använda den beräknade summan för att: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Se hur många personer ett nytt eller omarbetat segment kan nå när du skapar ett segment. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Justera segmentet beroende på dina mål. Stora segment är till exempel användbara för kampanjer som är inriktade på varumärken, och mindre segment är användbara för riktade kampanjer eller kampanjer som riktar sig om. </li> 
     </ul> </p> <p> <p>Obs! Måttet <span class="wintitle"> för uppskattad total population </span> inkluderar inte enheter som har kvalificerats för ett segment baserat på anslutningar från en <span class="wintitle"> profilkopplingsregel </span> som använder ett <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> enhetsdiagramalternativ </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Befintliga (faktiska) segmentpopulationsdata har definierats {#existing-segment-population}

[!UICONTROL Profile Merge Rules] påverkar det faktiska antalet populationer i realtid och totalt antal. Dessa summor varierar beroende på om det [!UICONTROL Profile Merge Rule] som ett segment tillhör använder ett enhetsdiagramalternativ eller inte. Se även [Alternativ för profilkopplingsregel definierade](../../features/profile-merge-rules/merge-rule-definitions.md).

### Segmentpopulationsdata för [!UICONTROL Merge Rules] utan [!UICONTROL Device Graph Option]

I följande tabell definieras faktiska populationsvärden i realtid och totalt när dina segment används av en [!UICONTROL Profile Merge Rule] som skapats utan ett [!UICONTROL device graph]-alternativ. Det här är inställningarna för enhetsalternativ **[!UICONTROL No Device Options]** och **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">-realtidspopulation (befintlig)</span> </p> </td> 
   <td colname="col2"> <p>Det faktiska antalet unika besökare som har setts i realtid för det angivna tidsintervallet och som var kvalificerade för segmentet när de sågs av Audience Manager. </p> <p>I <span class="wintitle"> Segment Builder </span> kan de sista 30-dagarspopulationerna för egenskaper (<span class="wintitle"> Total Trait Populations </span>) vara olika för egenskaper och segment som utvärderats i realtid. </p> <p> 
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

### Segmentpopulationsdata för [!UICONTROL Merge Rules] med ett [!UICONTROL Device Graph]-alternativ

I följande tabell definieras faktiska populationsvärden i realtid och totalt när dina segment används av en [!UICONTROL Profile Merge Rule] som skapats med ett [!DNL device graph]-alternativ. Det här är enhetsalternativsinställningarna för [!UICONTROL Profile Link Device Graph], [!DNL Adobe] [!DNL device graph] och andra alternativ från tredje part [!DNL device graph] som är tillgängliga för dig.


| Kolumn A | Kolumn B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing)] | Det faktiska antalet enheter som visas i realtid med aktuella profiler som, när de sammanfogas med upp till 100 andra enhetsprofiler som är kopplade till enhetsdiagrammet, innehåller egenskaperna som ska kvalificera sig för segmentet så fort det ses av Audience Manager. |
| [!UICONTROL Total Population (Existing)] | Det totala antalet enheter med profiler som, när de sammanfogades med upp till 100 andra enhetsprofiler som är kopplade till enhetsdiagrammet, alla var kvalificerade för segmentet. |

### Begränsningar på grund av återanvändnings- och frekvensuttryck vid beräkning av segmentpopulationer

[!UICONTROL Segment Builder] har stöd för uppskattningar av segmentstorlek för segmentregler som innehåller upp till 4 uttryck för senaste och frekvens. Om du väljer mer än fyra recency- och frekvensuttryck när du skapar en segmentregel visas ett fel i segmentberäkningsverktyget när populationen beräknas.

### Begränsningar på grund av [!UICONTROL Merge Rules] vid beräkning av segmentpopulationer

För närvarande finns det en känd begränsning eftersom vår uppskattare av segmentstorlek inte tar hänsyn till [!UICONTROL profile merge rules]. Titta till exempel på segment med **[!UICONTROL No Authenticated Profile + Current Device Profile]** [sammanfogningsregeln](../../features/profile-merge-rules/merge-rule-definitions.md). På grund av det sätt på vilket vi för närvarande beräknar antalet segment kommer de uppskattade populationerna att inkludera autentiserade profiler. Befintliga segmentpopulationer kommer dock att ignorera autentiserade profiler korrekt.

>[!MORELIKETHIS]
>
>* [Vanliga frågor om regler för profilsammanslagning och enhetsdiagram](../../faq/faq-profile-merge.md)
>* [Profillänk](../profile-merge-rules/merge-rules-overview.md)
