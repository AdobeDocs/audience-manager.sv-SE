---
description: Beskriver kraven på segmentstorlek och skapandetid som krävs för uppdateringsprocessen för överlappningsrapporten.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Uppdateringsschema för överlappningsrapporter och minsta segmentstorlek
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Överlappningsrapporter: Uppdatera schema och minsta segmentstorlek{#overlap-reports-update-schedule-and-minimum-segment-size}

Beskriver kraven på egenskaper, segmentstorlek och skapandetid som krävs för uppdateringsprocessen för överlappningsrapporten.

## Uppdatera schema och krav {#update-schedule}

[!UICONTROL Overlap] som uppdateras varje vecka på söndag. Förbearbetningen av rapporten börjar på lördag. Detta påverkar hur nya eller befintliga segment visas i en överlappningsrapport på måndag. Ska inkluderas i en överlappningsrapport:

* Ett segment måste innehålla minst 70 000 användare i realtid under de senaste 14 dagarna.
* Ett trait måste innehålla 28 000 [unik implementering av egenskaper](/help/using/features/traits/trait-and-segment-qualification-reference.md) under de senaste 14 dagarna.
* Ett segment måste ha skapats före torsdag kl. 12.00 UTC (2 hela dagar innan uppdateringsprocessen för överlappningsrapporten varje vecka börjar).
* Ditt företag måste vara en fullständig [!DNL Audience Manager] kund. Kontakta [!DNL Audience Manager] konsult eller kundtjänst om du vill veta mer.

## Segmentstorlek och/eller skapandetid påverkar rapportering {#segment-size}

Om du inte ser något segment i något av [!UICONTROL Overlap] kan det bero på att segmentet inte uppfyller dessa minimikrav.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Användningsexempel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentstorleken är för liten</b> </p> </td> 
   <td colname="col2"> <p>Låt oss säga att du skapar ett segment före kl. 12 torsdag UTC, men det innehåller färre än 70 000 användare i realtid. Det här segmentet visas inte i en <span class="wintitle"> Överlappningsrapport</span> tills det uppfyller kraven för användartröskelvärde. Observera också att segmentet måste uppfylla det antal användare som krävs för, eller före, torsdagens brytningsperiod. Om den inte klarar veckoslutet visas segmentet i <span class="wintitle"> Överlappa rapporter</span> veckan efter det att kommande söndagsdata har körts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentet har skapats för sent</b> </p> </td> 
   <td colname="col2"> <p>Säg att du skapar ett segment på fredag och det innehåller över 70 000 användare i realtid. Det här segmentet visas inte i <span class="wintitle"> Överlappa rapporter</span> för nästa vecka eftersom den skapades mindre än två dagar före rapportuppdateringsperioden. Segmentet visas dock i en <span class="wintitle"> Överlappningsrapport</span> efter nästa veckouppdatering. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Överlappningsrapport för trait till trait](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Överlappningsrapport för segment till trait](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Överlappningsrapport för segment till segment](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

