---
description: Returnerar data om antalet unika användare som delas mellan en viss egenskap och ett helt segment.
seo-description: Returnerar data om antalet unika användare som delas mellan en viss egenskap och ett helt segment.
seo-title: Överlappningsrapport för segment till trait
solution: Audience Manager
title: Överlappningsrapport för segment till trait
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Overlap Reports
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# Överlappningsrapport för segment till trait{#segment-to-trait-overlap-report}

Returnerar data om antalet unika användare som delas mellan en viss egenskap och ett helt segment.

>[!NOTE]
>
>Överlappningsrapporterna i Audience Manager följer RBAC-principerna. Du kan bara se segment och egenskaper från datakällor som du har åtkomst till baserat på [RBAC-användargruppen](/help/using/features/administration/administration-overview.md) som du tillhör.

<!-- 

c_segment_trait_overlap.xml

 -->

## Översikt

[!UICONTROL Segment to Trait Overlap]-rapporterna är ett optimeringsverktyg som hjälper dig att skapa fokuserade segment eller utöka segmentens räckvidd. Du kan till exempel skapa fokuserade segment och egenskaper med hög överlappning för att nå en viss målgrupp. Många överlappningar kan dock innebära färre unika användare (mindre räckvidd). Genom att köra den här rapporten kan du utöka räckvidden genom att ta bort egenskaper med många segmentöverlappningar och ersätta dem med egenskaper som inte överlappar varandra.

### Exempelrapport

Följande bild ger en översikt på hög nivå över [!UICONTROL Segment-to-Trait Overlap]-rapporten.

![](assets/segment-to-trait-overlap.png)

### Detaljgranska enskilda datapunkter

Markera en enskild punkt om du vill visa datainformation i ett popup-fönster. Dina klickåtgärder uppdaterar automatiskt data som visas i rapporten.

## Jämför segment med egenskaper {#comparing-segments-to-traits}

Beskriver hur du kan jämföra segment och egenskaper för att hämta meningsfull information från resultaten.

<!-- 

c_compare_s2t.xml

 -->

### Jämförelse mellan Trait and Segment Uniques: Ett exempel

Vid första anblicken kan det verka ologiskt att jämföra segment med egenskaper och försöka dra slutsatser av resultaten. När allt kommer omkring är segment och egenskaper olika, så hur kan data som härleds från olika artiklar få betydelse? I det här fallet jämför vi dock inte egenskaper och segment, utan antalet unika besökare som delas mellan dem. Antalet delade unika besökare ger det gemensamma värdet som gör det möjligt att jämföra segment för att anpassa.

I följande diagram visas relationen mellan en egenskap och det segment den tillhör. I det här fallet har vi en egenskap med 10 besökare och ett segment med 1 000 besökare. De delar tre unika besökare gemensamt.

![](assets/s2t.png)

Det unika besökarantalet är det vanliga, konstanta värdet som delas mellan de olika objektklasserna. Därför kan du fastställa den unika besökarrelationen mellan dem enligt följande:

* Trait delar 30 % av sina unika besökare med segmentet (3/10 = 0,30).
* Segmentet delar 0,3 % av sina unika besökare med egenskapen (3/1 000 = 0,003)

### Sök efter värde i segmentering efter Trait-jämförelse

Om du tittar på överlappningen mellan egenskaper och segment kan det hjälpa dig att uppskatta den totala tillgängliga besökspoolen (prognoser) eller hitta ineffektiva segment med för mycket överlappning.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Användningsexempel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Prognos</b> </td> 
   <td colname="col2"> <p>För att fastställa den tillgängliga besökarpoolen ska du summera skillnaden mellan den totala trait-summan (minus överlappning) och segmentsumman (minus överlappning). </p> <p>Den här segmentanpassade kombinationen kan omfatta upp till 1 004 nya användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Hitta ineffektiva segment</b> </td> 
   <td colname="col2"> <p>Om en egenskap är en del av en <span class="wintitle"> AND</span>-grupp i en segmentdefinition finns de unika besökarna som har den egenskapen redan i segmentet och är inte tillgängliga för att lägga till i segmentet. Du kan använda den här rapporten för att hitta relevanta egenskaper med låg överlappning och lägga till dem i segmentdefinitionen, vilket ökar segmentets räckvidd. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Förstå datafiltren i överlappningsrapporten Segment-till-Trait {#data-filters-s2t-report}

Beskriver hur de unika segmentreglagen överlappar %.

<!-- 

r_s2t_sliders.xml

 -->

Med [!UICONTROL Segment-to-Trait overlap]-rapporten kan du använda två reglage för att filtrera data efter överlappningen % efter trait eller segment.

* **[!UICONTROL Filter Trait Uniques %:]** Filtrerar data efter % av unika besökare som delas mellan egenskapen och segmentet.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Filtrerar data efter % av unika besökare delar mellan segmentet och egenskapen.

### Exempel

I följande diagram visas skillnaden mellan brickorna uniques % och segmentet uniques %. I det här fallet delar trait och segment tre unika besökare. Som proportioner:

* Trait delar 30 % av sina unika besökare med segmentet (3/10 = 0,30).
* Segmentet delar 0,3 % av sina unika besökare med egenskapen (3/1 000 = 0,003)

![](assets/s2t.png)

## Segment-till-trait-dataportfält definierade {#fields-defined}

Beskriver de mått som visas i popup-fönstret när du klickar på en enskild datapunkt.

<!-- 

r_s2t_data_pop.xml

 -->

Popup-fönstret för [!UICONTROL Segment-to-Trait Overlap]-rapporten innehåller måtten nedan. Observera att tabellens unika mått representerar dina *realtidsanvändare*.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segment-ID</span></b> </td> 
   <td colname="col2"> Unikt numeriskt ID för segmentet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Anpassa datakälla  </span></b> </td> 
   <td colname="col2"> Namn på trait-ägaren. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Typ av datakälla</span></b> </td> 
   <td colname="col2">Definierar den typ av provider som ett drag tillhör. Kan antingen vara: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Första part (din egen egenskap). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Tredje part (från en extern datapartner/leverantör). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait-ID</span></b> </td> 
   <td colname="col2"> Unikt numeriskt ID för trait. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Name</span></b> </td> 
   <td colname="col2"> Namn på trait. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Uniques-överlappning %</span></b> </td> 
   <td colname="col2"> % av de unika besökarna som ett varumärke delar med segmentet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segmentvetenskaper överlappar %</span></b> </td> 
   <td colname="col2"> % av unika besökare som delar ett segment med en egenskap. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Överlappa unika</span></b> </td> 
   <td colname="col2"> Antal unika besökare som delas mellan segmentet och trait. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segment Uniques</span></b> </td> 
   <td colname="col2"> Antal unika besökare i segmentet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Uniques</span></b> </td> 
   <td colname="col2"> Antal unika besökare i trait. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Filtrera rapportresultat med datareglage](../../reporting/dynamic-reports/data-sliders.md)
>* [Former, färger och storlekar som används i interaktiva rapporter](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Ikoner och verktyg för rapporter förklaras](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Överlappningsrapporter: Uppdatera schema och minsta segmentstorlek](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datainsamling och felfrekvens i valda rapporter för Audience Manager...](../../reporting/report-sampling.md)
>* [CSV-filer för överlappningsrapporter](../../reporting/dynamic-reports/overlap-csv-files.md)

