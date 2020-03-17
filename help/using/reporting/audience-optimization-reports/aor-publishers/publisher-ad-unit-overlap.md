---
description: Rapporten om annonsenhetsöverlappning visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter.
seo-description: Rapporten om annonsenhetsöverlappning visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter.
seo-title: Annonsväxling
solution: Audience Manager
title: Annonsväxling
uuid: e4467e81-acbf-474e-b501-89d57395651f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Annonsväxling{#ad-unit-overlap}

Rapporten visas som ett **[!UICONTROL Ad Unit Overlap]** värmediagram som markerar höga och låga överlappningar mellan annonsenheter.

## Användningsfall {#use-cases}

Med **[!UICONTROL Ad Unit Overlap]** rapporten får ni insikt i var era målgrupper överlappar era webbegenskaper. I rapporten behandlas dina 100 mest relaterade egenskaper och hur de överlappar varandra.

## Använda överlappningsrapport för annonsenhet {#using-the-report}

Använd kontrollerna **[!UICONTROL Top N Base Ad Units]** och **[!UICONTROL Top N Overlapping Ad Units]** för att välja önskat antal annonsenheter för överlappningen. Du kan välja maximalt 100 objekt för varje.

Använd kontrollerna **Dagintervall** och **Datum till och med** för att justera det önskade intervallet. Observera att 7-dagars och 30-dagars summeringsperioder endast är tillgängliga för söndagsdatum.

Använd kontrollerna **[!UICONTROL Base Ad Unit]** och **[!UICONTROL Overlap Ad Unit]** kontrollerna för att välja vilka av dina annonsenheter som du vill visa i överlappningsrapporten.

>[!IMPORTANT]
>
>När du aktiverar [!UICONTROL Audience Optimization for Publishers]måste du inkludera beskrivande metadata för [!UICONTROL Ad Unit IDs], enligt beskrivningen i steg 3 i [Importera DFP-datafiler till Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Genom att göra detta försäkrar du dig om att rapporten anger webbegenskapen som [!UICONTROL Ad Unit] i stället för [!UICONTROL Ad Unit ID].

## Tolka resultaten {#interpreting-results}

Din [!UICONTROL Ad Unit Overlap] rapport kan se ut ungefär som den nedan. Håll muspekaren över en cell för att få mer information om just den överlappningen. Se beskrivningarna för ytterligare information i tabellen nedan.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Objekt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Överlappa annonsenhet</span> </p> </td> 
   <td colname="col2"> <p>Namnet på lagerartikeln. Detta kan till exempel vara en av dina webbplatser eller en artikel på din webbplats. I bilden ovan är basannonsenheterna artiklarna 9-18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basannonsenhet</span> </p> </td> 
   <td colname="col2"> <p>Namnet på lagerartikeln. Detta kan till exempel vara en av dina webbplatser eller en artikel på din webbplats. I bilden ovan är basannonsenheterna artiklarna 1-8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Antal överlappande annonsenheter</span> </p> </td> 
   <td colname="col2"> <p>Antalet användare som har besökt annonsenheten 9-18. Den här informationen extraheras från DFP-loggarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Antal basannonsenheter</span> </p> </td> 
   <td colname="col2"> <p>Antalet användare som har besökt annonsenhetsposterna 1-8. Den här informationen extraheras från DFP-loggarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Överlappa antal unika</span> </p> </td> 
   <td colname="col2"> <p>Överlappningen mellan användare som besökt en <span class="wintitle"> basannonsenhet</span> och <span class="wintitle"> överlappande annonsenhet</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Överlappningsprocent</span> </p> </td> 
   <td colname="col2"> <p>Överlappningen mellan användare som besökt en <span class="wintitle"> basannonsenhet</span> och <span class="wintitle"> överlappande annonsenhet</span>. Detta är det <span class="wintitle"> överlappande Uniques Count</span>, uttryckt i procent av <span class="wintitle"> Base Ad Unit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
