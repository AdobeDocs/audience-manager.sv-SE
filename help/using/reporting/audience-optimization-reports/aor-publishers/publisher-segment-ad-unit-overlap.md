---
description: Rapporten Överlappning mellan segment och annonsenhet visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter och Audience Manager.
seo-description: Rapporten Överlappning mellan segment och annonsenhet visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter och Audience Manager.
seo-title: Överlappning mellan segment och annonsenhet
solution: Audience Manager
title: Överlappning mellan segment och annonsenhet
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 4%

---


# Överlappning mellan segment och annonsenhet{#segment-to-ad-unit-overlap}

Rapporten Överlappning mellan segment och annonsenhet visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter och Audience Manager.

## Användningsexempel {#use-cases}

Med [!UICONTROL Segment to Ad Unit Overlap]-rapporten kan du förstå vilka målgrupper som besöker dina webbegenskaper. Rapporten visar överlappningen mellan medlemmarna i dina [!DNL Audience Manager]-segment och antalet besökare i dina webbegenskaper. En högre överlappning innebär att många medlemmar i ett segment besöker din webbegenskap.

## Använda överlappningsrapporten Segment till annonsenhet {#using-the-report}

Använd kontrollerna **[!UICONTROL Top N Ad Units]** och **[!UICONTROL Top N Segments]** för att välja önskat antal annonsenheter och segment för överlappningen. Du kan välja maximalt 100 objekt för varje.

Använd kontrollerna **Dagintervall** och **Datum till och med** för att justera backupintervallet. Observera att 7-dagars och 30-dagars summeringsperioder endast är tillgängliga för söndagsdatum.

Använd rutorna **[!UICONTROL Segment Name]** och **[!UICONTROL Ad Unit]** för att filtrera segment och annonsenheter.

>[!IMPORTANT]
>
>När du aktiverar [!UICONTROL Audience Optimization for Publishers] måste du inkludera beskrivande metadata för [!UICONTROL Ad Unit IDs], enligt beskrivningen i steg 3 av [Importera Google Ad Manager-datafiler (tidigare DFP) till Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Genom att göra detta försäkrar du dig om att rapporten anger webbegenskapen som [!UICONTROL Ad Unit] i stället för [!UICONTROL Ad Unit ID].

## Tolka resultaten {#interpreting-results}

Din [!UICONTROL Segment to Ad Unit Overlap]-rapport kan se ut ungefär som den nedan. Håll muspekaren över en cell för att få mer information om just den överlappningen. Se beskrivningarna för ytterligare information i tabellen nedan.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Objekt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Annonsenhet  </span> </p> </td> 
   <td colname="col2"> <p>Namnet på lagerartikeln. Detta kan till exempel vara en av dina webbplatser eller en artikel på din webbplats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Antal segmentenheter i realtid</span> </p> </td> 
   <td colname="col2"> <p>Antalet unika besökare som har setts i realtid för det angivna tidsintervallet och som var kvalificerade för segmentet när de sågs av <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Antal annonsenheter</span> </p> </td> 
   <td colname="col2"> <p>Antalet besökare för den här specifika annonsenheten. Den här informationen extraheras från Google Ad Manager-loggarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Överlappa antal unika</span> </p> </td> 
   <td colname="col2"> <p>De medlemmar i ditt segment som exponerades för annonsenhetsobjektet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Överlappningsprocent</span> </p> </td> 
   <td colname="col2"> <p>Överlappningen mellan annonsenhet och segmentpopulationer. Detta är <span class="wintitle"> Överlappa Uniques Count</span>, uttryckt i procent av <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

