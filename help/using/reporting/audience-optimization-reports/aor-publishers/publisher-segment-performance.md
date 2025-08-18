---
description: I rapporten Segment Performance jämförs mappade och omappade segment med visningar och Real-Time Segment Uniques. Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning. Genom att jämföra dessa olika segmenttyper inom och mellan rapporter kan ni optimera befintliga kampanjer och hitta förbisedda segment som ni kanske vill skicka till en målgrupp för målinriktning.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Resultatrapport för segment för utgivare
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Resultatrapport för segment{#segment-performance-report}

I rapporten Segment Performance jämförs mappade och omappade segment med visningar och Real-Time Segment Uniques.

Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning.

Genom att jämföra dessa olika segmenttyper inom och mellan rapporter kan ni optimera befintliga kampanjer och hitta förbisedda segment som ni kanske vill skicka till en målgrupp för målinriktning.

## Användningsexempel {#use-cases}

Med rapporten [!UICONTROL Segment Performance] kan du:

* Identifiera mappade målgruppssegment som driver skala eller prestanda framåt.
* Identifiera omappade segment som ska introduceras i framtida kampanjer, baserat på en målgrupps bidrag till tidigare resultat.

## Använda rapporten om segmentprestanda {#using-segment-performance-report}

Växla mellan **[!UICONTROL Mapped]** och **[!UICONTROL Unmapped]** om du vill markera segment som är mappade till ett mål eller inte. Välj **[!UICONTROL All]** om du vill inkludera alla dina segment i rapporten.

Använd kontrollerna **Dagintervall** och **Datum till** om du vill justera intervallet. Observera att 7-dagars och 30-dagars summeringsperioder endast är tillgängliga för söndagsdatum.

Använd listrutan **[!UICONTROL Line Item]** för att välja de webbegenskaper som du vill returnera information för.

I listrutan **[!UICONTROL Segment Data Source]** markerar du datakällorna som innehåller de segment som du vill se i rapporten.

Använd listrutan **[!UICONTROL Segment]** för att välja vilka segment som ska visas i rapporten.

>[!IMPORTANT]
>
>När du aktiverar [!UICONTROL Audience Optimization for Publishers] måste du inkludera beskrivande metadata för [!UICONTROL Line Item IDs], enligt beskrivningen i steg 3 i [Importera datafiler från Google Ad Manager (tidigare DFP) till Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Genom att göra detta försäkrar du dig om att rapporten innehåller information om webbegenskapen som [!UICONTROL Line Item] i stället för [!UICONTROL Line Item ID].

## Tolka resultaten {#interpreting-results}

Din [!UICONTROL Segment Performance]-rapport kan se ut ungefär som den nedan. Klicka på en bubbla i rapporten för att visa underliggande data. Se beskrivningarna för ytterligare information i tabellen nedan.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Objekt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Segment </p> </td> 
   <td colname="col2"> <p>Det alfanumeriska namn som du tilldelade segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segment-ID </p> </td> 
   <td colname="col2"> <p>Unikt ID för det här segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Radartikel </p> </td> 
   <td colname="col2"> <p>Den webbegenskap som du ser den här rapporten för. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Klickningar </p> </td> 
   <td colname="col2"> <p>Antalet gånger som medlemmar i den här egenskapen har klickat på objekt i din webbegenskap. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressions </p> </td> 
   <td colname="col2"> <p>Antalet gånger som medlemmar i den här egenskapen har exponerats för ditt lager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Klickfrekvens. </p> <p>Det här måttet visar hur många procent av intrycken som har följts av klickningar. Dela upp klickningarna efter Impressions för att få detta mätresultat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realtime-segmentpopulering </p> </td> 
   <td colname="col2"> <p>Det faktiska antalet unika besökare som visas i realtid för det angivna tidsintervallet och som var kvalificerade för segmentet när de visades av <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Så här läser du mappade segmentresultat {#read-mapped-segment}

Positionen för de mappade segmenten i en rapport kan tala om för dig mycket om vilka segment som fungerar bra och var du kan behöva göra vissa justeringar.

Om du vill läsa rapporten kan du dela upp resultaten i fyra avsnitt med imaginära rader (i rött) och de kategorier som visas i exempelrapporten nedan. Etiketterna i exemplet kan hjälpa dig att förstå segmentets prestanda och hur du ska svara på dessa resultat.

![](assets/publisher_segment_performance_mapped.png)

## Läs omappade segmentresultat {#read-unmapped-segment}

Att titta på omappade segment i en [!UICONTROL Segment Performance]-rapport är ett bra sätt att hitta nya segment som du inte har övervägt som mål. Vissa av dessa segment kanske överträffar dina mappade segment.

Om du vill läsa den här rapporten kan du dela upp resultaten i fyra avsnitt med imaginära rader (i rött) och kategorier som visas i exempelrapporten nedan.

![](assets/publisher_segment_performance_unmapped.png)
