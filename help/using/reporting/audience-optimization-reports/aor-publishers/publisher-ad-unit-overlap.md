---
description: Rapporten om annonsenhetsöverlappning visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Annonsväxling
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Annonsväxling{#ad-unit-overlap}

Rapporten **[!UICONTROL Ad Unit Overlap]** visas som ett värmediagram som markerar höga och låga överlappningar mellan annonsenheter.

## Användningsexempel {#use-cases}

Med rapporten **[!UICONTROL Ad Unit Overlap]** får du insikt i var din publik överlappar dina webbegenskaper. I rapporten behandlas dina 100 mest relaterade egenskaper och hur de överlappar varandra.

## Använda överlappningsrapport för annonsenhet {#using-the-report}

Använd kontrollerna **[!UICONTROL Top N Base Ad Units]** och **[!UICONTROL Top N Overlapping Ad Units]** för att välja önskat antal annonsenheter för överlappningen. Du kan välja maximalt 100 objekt för varje.

Använd kontrollerna **Dagintervall** och **Datum till** om du vill justera intervallet. Observera att 7-dagars och 30-dagars summeringsperioder endast är tillgängliga för söndagsdatum.

Använd kontrollerna **[!UICONTROL Base Ad Unit]** och **[!UICONTROL Overlap Ad Unit]** för att välja vilka av dina annonsenheter du vill visa i överlappningsrapporten.

>[!IMPORTANT]
>
>När du aktiverar [!UICONTROL Audience Optimization for Publishers] måste du inkludera beskrivande metadata för [!UICONTROL Ad Unit IDs], enligt beskrivningen i steg 3 i [Importera datafiler från Google Ad Manager (tidigare DFP) till Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Genom att göra detta försäkrar du dig om att rapporten innehåller information om webbegenskapen som [!UICONTROL Ad Unit] i stället för [!UICONTROL Ad Unit ID].

## Tolka resultaten {#interpreting-results}

Din [!UICONTROL Ad Unit Overlap]-rapport kan se ut ungefär som den nedan. Håll muspekaren över en cell för att få mer information om just den överlappningen. Se beskrivningarna för ytterligare information i tabellen nedan.

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
   <td colname="col1"> <p><span class="wintitle"> överlappande annonsenhet</span> </p> </td> 
   <td colname="col2"> <p>Namnet på lagerartikeln. Detta kan till exempel vara en av dina webbplatser eller en artikel på din webbplats. I bilden ovan är basannonsenheterna artiklarna 9-18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> basannonsenhet</span> </p> </td> 
   <td colname="col2"> <p>Namnet på lagerartikeln. Detta kan till exempel vara en av dina webbplatser eller en artikel på din webbplats. I bilden ovan är basannonsenheterna artiklarna 1-8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Antal överlappande annonsenheter </span> </p> </td> 
   <td colname="col2"> <p>Antalet användare som har besökt annonsenheten 9-18. Den här informationen extraheras från Google Ad Manager-loggarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> antal basannonsenheter </span> </p> </td> 
   <td colname="col2"> <p>Antalet användare som har besökt annonsenhetsposterna 1-8. Den här informationen extraheras från Google Ad Manager-loggarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Överlappa Uniques Count</span> </p> </td> 
   <td colname="col2"> <p>Överlappningen mellan användare som har besökt en <span class="wintitle"> basannonsenhet </span> och <span class="wintitle"> överlappar annonsenhet </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> överlappningsprocent</span> </p> </td> 
   <td colname="col2"> <p>Överlappningen mellan användare som har besökt en <span class="wintitle"> basannonsenhet </span> och <span class="wintitle"> överlappar annonsenhet </span>. Det här är <span class="wintitle">-överlappningen för Uniques Count</span>, uttryckt i procent av <span class="wintitle"> Base Ad Unit </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
