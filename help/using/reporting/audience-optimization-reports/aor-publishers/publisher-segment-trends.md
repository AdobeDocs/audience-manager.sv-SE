---
description: Rapporten Segmenttrender returnerar data om visningar och klickfrekvenser för mappade och omappade segment över tiden. Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning. Jämför trender och volym för valda mätvärden för att få en bättre bild av hur era målgrupper beter sig över tid.
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: Trendrapport för segment
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 2%

---

# Trendrapport för segment{#segment-trend-report}

Rapporten Segmenttrender returnerar data om visningar och klickfrekvenser för mappade och omappade segment över tiden.

Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning.

Jämför trender och volym för valda mätvärden för att få en bättre bild av hur era målgrupper beter sig över tid.

## Användningsexempel {#use-cases}

Använd [!UICONTROL Segment Trend] för att validera ett segments prestanda över tid och för att identifiera trender baserat på starka prestanda eller skalbarhet.

Med den här rapporten kan du förstå vilka av dina webbegenskaper som visar en ökning av antalet fel och felsökning efter behov. Den här rapporten är nästa steg efter att du har identifierat din publik i [!UICONTROL Segment Performance] för att försäkra dig om att de goda eller dåliga resultat du såg i [!UICONTROL Segment Performance] -fliken är konsekvent över tid.

## Använda segmenttrendrapporten {#using-the-report}

Växla mellan **[!UICONTROL Mapped]** och **[!UICONTROL Unmapped]** om du vill markera segment som är mappade till ett mål eller inte. Välj **[!UICONTROL All]** för att inkludera alla era segment i rapporten.

Justera fönstret för att titta bakåt med **[!UICONTROL Date Through]** skjutreglage.

Klicka på något av segmenten under **[!UICONTROL Date Through]** för att ta fram alternativet att bara behålla det segmentet i rapporten eller exkludera det.

Använd **[!UICONTROL Line Item]** för att välja de egenskaper i din portfölj för vilka du vill returnera information.

I **[!UICONTROL Segment Data Source]** markerar du datakällorna som innehåller de segment som du vill se i rapporten.

Använd **[!UICONTROL Segment]** för att välja vilka segment som ska visas i rapporten.

>[!IMPORTANT]
>
>Vid aktivering [!UICONTROL Audience Optimization for Publishers]måste du ta med beskrivande metadata för [!UICONTROL Line Item] ID, enligt beskrivning i steg 3 av [Importera Google Ad Manager-datafiler (tidigare DFP) till Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Genom att göra detta försäkrar du dig om att rapporten innehåller information om webbegenskapen som [!UICONTROL Line Item] i stället för [!UICONTROL Line Item] ID.

## Tolka resultaten {#interpreting-results}

The [!UICONTROL Segment Trend] rapporten returnerar data i ett linjediagram endast för 14-dagarsintervall. I det här exemplet visar rapporten intrycks- och klickningstrender för en uppsättning mappade och omappade segment.

Håll pekaren över en linje för att få mer information om den aktuella segmenttrenden. Se beskrivningarna för ytterligare information i tabellen nedan.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Objekt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment</span> </p> </td> 
   <td colname="col2"> <p>Det alfanumeriska namn som du tilldelade det här segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment-ID</span> </p> </td> 
   <td colname="col2"> <p>Det unika ID:t för det här segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Radartikel</span> </p> </td> 
   <td colname="col2"> <p>Den webbegenskap som du ser den här rapporten för. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Klickningar</span> </p> </td> 
   <td colname="col2"> <p>Antalet gånger som medlemmar i den här egenskapen har klickat på objekt i din webbegenskap. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Antalet gånger som medlemmar i den här egenskapen har exponerats för ditt lager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Klickfrekvens. Det här måttet visar hur många procent av intrycken som ska följas av klickningar. Dela upp klickningarna med avtryck för att få fram mätvärdet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment Uniques</span> </p> </td> 
   <td colname="col2"> <p>Antalet segmentmedlemmar under de senaste 30 dagarna. </p> </td> 
  </tr> 
 </tbody> 
</table>
