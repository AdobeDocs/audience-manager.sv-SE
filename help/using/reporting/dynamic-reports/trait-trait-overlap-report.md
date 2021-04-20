---
description: Returnerar data om antalet unika användare som delas av alla dina första och tredje parts egenskaper.
seo-description: Returnerar data om antalet unika användare som delas av alla dina första och tredje parts egenskaper.
seo-title: Överlappningsrapport för trait till trait
solution: Audience Manager
title: Överlappningsrapport för trait till trait
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 8%

---

# Överlappningsrapport för trait till trait{#trait-to-trait-overlap-report}

Returnerar data om antalet unika användare som delas av alla dina första och tredje parts egenskaper.

>[!NOTE]
>
>Överlappningsrapporterna i Audience Manager följer RBAC-principerna. Du kan bara se egenskaper från datakällor som du har åtkomst till baserat på [RBAC-användargruppen](/help/using/features/administration/administration-overview.md) som du tillhör.

<!-- 

c_overlap_reports.xml

 -->

## Översikt

[!UICONTROL Trait-to-Trait Overlap]-rapporten returnerar data för % av unika användare som delas mellan alla dina egna egenskaper och dina egenskaper hos tredje part. Den här rapporten är ett optimeringsverktyg som hjälper dig att:

* Skapa segment med hög eller låg överlappning, beroende på dina behov. Med hög överlappning får ni en målgrupp, men färre unika besökare. Fällor med låg överlappning kan vara användbara för att nå en större, unik besökaruppsättning.
* Validera tredjeparts trait-data: En stark överlappning mellan liknande egenskaper från första och tredje part tyder på att datapartnerns egenskaper är korrekta och tillförlitliga. Omvänt kan låg överlappning indikera att en egenskap från tredje part kanske inte innehåller samma information som din egen, liknande egenskap från första part.
* Hitta oväntad överlappning mellan egenskaper och använd den informationen för att skapa innovativa segment.

## Exempelrapport

Följande bild ger en översikt på hög nivå över element i [!UICONTROL Trait-to-Trait Overlap]-rapporten.

>[!NOTE]
>
>Rapporten [!UICONTROL Trait-to-Trait Overlap] returnerar ett tomt fält när den jämför samma egenskap med sig själv.

![](assets/trait-to-trait-overlap.png)

## Detaljgranska enskilda datapunkter

Markera en enskild punkt om du vill visa datainformation i ett popup-fönster. Dina klickåtgärder uppdaterar automatiskt data som visas i rapporten.

## Trait-to-Trait överlappar dataportfält som definierats {#field-definitions}

Beskriver de mått som visas i popup-fönstret när du klickar på en enskild datapunkt.

<!-- 

r_t2t_data_pop.xml

 -->

Popup-fönstret för [!UICONTROL Trait-to-Trait Overlap]-rapporten innehåller måtten nedan. Observera att tabellens unika mått representerar dina *realtidsanvändare*.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Överlappa %</span></b> </td> 
   <td colname="col2"> Visar procentandelen av unik överlappning mellan jämförda egenskaper (överlappar unika/trait-uniques). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Typ av datakälla</span></b> </td> 
   <td colname="col2">Definierar den typ av datakälla som ett drag tillhör. Kan antingen vara: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Första part (din egen egenskap). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Tredje part (från en extern datapartner/leverantör). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Överlappande traits-ID</span></b> </td> 
   <td colname="col2"> Unikt numeriskt ID för det överlappande tecknet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Namn på överlappande tram</span></b> </td> 
   <td colname="col2"> Namnet på det överlappande tecknet. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait ID 2</span></b> </td> 
   <td colname="col2"> Unikt numeriskt ID för egenskapen i basdatakällan. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Name 2</span></b> </td> 
   <td colname="col2"> Namnet på egenskapen i din basdatakälla. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Överlappa unika</span></b> </td> 
   <td colname="col2"> <p>För att få överlappningen % använder Audience Manager följande formel:</p> <p>Överlappande uniques / (Base trait Uniques + Overlapping trait Uniques - Overlapping Uniques)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Överlappande fackenheter</span></b> </td> 
   <td colname="col2"> Antalet unika besökare från den överlappande egenskapen. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Grundläggande Trait Uniques</span></b> </td> 
   <td colname="col2"> Antalet unika besökare från grundtrakten. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrera rapportresultat med datareglage](../../reporting/dynamic-reports/data-sliders.md)
>* [Former, färger och storlekar som används i dynamiska rapporter](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Ikoner och verktyg för rapporter förklaras](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Överlappningsrapporter: Uppdatera schema och minsta segmentstorlek](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datainsamling och felfrekvens i valda rapporter för Audience Manager...](../../reporting/report-sampling.md)
>* [CSV-filer för överlappningsrapporter](../../reporting/dynamic-reports/overlap-csv-files.md)

