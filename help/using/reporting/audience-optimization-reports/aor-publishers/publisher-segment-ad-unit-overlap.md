---
description: Rapporten Överlappning mellan segment och annonsenhet visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter och Audience Manager-segment.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Överlappning mellan segment och annonsenhet
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# Överlappning mellan segment och annonsenhet{#segment-to-ad-unit-overlap}

Rapporten Överlappning mellan segment och annonsenhet visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter och Audience Manager-segment.

## Användningsexempel {#use-cases}

Med rapporten [!UICONTROL Segment to Ad Unit Overlap] kan du förstå vilka målgrupper som besöker dina webbegenskaper. Rapporten visar överlappningen mellan medlemmar i dina [!DNL Audience Manager]-segment och antalet besökare i dina webbegenskaper. En högre överlappning innebär att många medlemmar i ett segment besöker din webbegenskap.

## Använda överlappningsrapport för segment till annonsenhet {#using-the-report}

Använd kontrollerna **[!UICONTROL Top N Ad Units]** och **[!UICONTROL Top N Segments]** för att välja önskat antal annonsenheter och segment för överlappningen. Du kan välja maximalt 100 objekt för varje.

Använd kontrollerna **Dagintervall** och **Datum till** om du vill justera intervallet. Observera att 7-dagars och 30-dagars summeringsperioder endast är tillgängliga för söndagsdatum.

Använd rutorna **[!UICONTROL Segment Name]** och **[!UICONTROL Ad Unit]** för att filtrera segment och annonsenheter.

>[!IMPORTANT]
>
>När du aktiverar [!UICONTROL Audience Optimization for Publishers] måste du inkludera beskrivande metadata för [!UICONTROL Ad Unit IDs], enligt beskrivningen i steg 3 i [Importera datafiler från Google Ad Manager (tidigare DFP) till Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Genom att göra detta försäkrar du dig om att rapporten innehåller information om webbegenskapen som [!UICONTROL Ad Unit] i stället för [!UICONTROL Ad Unit ID].

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
   <td colname="col1"> <p><span class="wintitle"> annonsenhet </span> </p> </td> 
   <td colname="col2"> <p>Namnet på lagerartikeln. Detta kan till exempel vara en av dina webbplatser eller en artikel på din webbplats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Antal segment i realtid för Uniques </span> </p> </td> 
   <td colname="col2"> <p>Antalet unika besökare som har setts i realtid för det angivna tidsintervallet och som var kvalificerade för segmentet när de visades av <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ad Unit Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>Antalet besökare för den här specifika annonsenheten. Den här informationen extraheras från Google Ad Manager-loggarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Överlappa Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>De medlemmar i ditt segment som exponerades för annonsenhetsobjektet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> överlappningsprocent</span> </p> </td> 
   <td colname="col2"> <p>Överlappningen mellan annonsenhet och segmentpopulationer. Det här är <span class="wintitle">-överlappningen för Uniques Count</span>, uttryckt i procent av <span class="wintitle"> Segment Real Time Uniques </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
