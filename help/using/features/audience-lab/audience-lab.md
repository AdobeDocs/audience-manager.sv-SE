---
description: Skapa ömsesidigt uteslutande testsegment i segmenttestgrupper för att jämföra och mäta effektiviteten för olika destinationer. Du kan avsätta en kontrollgrupp och dela upp segmentet i procent av en helhet för att testa effekten.
seo-description: Skapa ömsesidigt uteslutande testsegment i segmenttestgrupper för att jämföra och mäta effektiviteten för olika destinationer. Du kan avsätta en kontrollgrupp och dela upp segmentet i procent av en helhet för att testa effekten.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---


# [!UICONTROL Audience Lab] {#audience-lab}

Skapa ömsesidigt uteslutande testsegment i [!UICONTROL Segment Test Groups] för att jämföra och mäta effektiviteten för olika destinationer. Du kan avsätta en kontrollgrupp och dela upp segmentet i procent av en helhet för att testa effekten.

## Översikt {#audience-lab-overview}

[!UICONTROL Audience Lab] använder [Profile Link](../../features/profile-merge-rules/merge-rules-overview.md) för att driva tester mellan olika enheter. Detta bidrar till att säkerställa att användaren kvalificerar sig för samma testsegment och får samma behandling på alla enheter. Testsegmenten i testgrupperna ärver [profilkopplingsregeln](../../features/profile-merge-rules/merge-rules-dashboard.md) som bassegmentet har tilldelat.

I [!UICONTROL Audience Lab] standardvyn visas ett kort för varje testgrupp. Klicka på ett kort för att komma åt **[!UICONTROL Test Group]** vyn. Vyn innehåller följande information:

* **[Information om testgrupp](../../features/audience-lab/audience-lab-information-view.md)**
* **[Testgruppsrapportering](../../features/audience-lab/audience-lab-reporting-view.md)**

Du kan skapa **upp till 10 testgrupper**, där var och en har **upp till 15 testsegment**.

![](assets/test-groups-view.PNG)

## Sök efter och filtrera testgrupper {#search-and-filter}

När du har börjat skapa flera testgrupper med flera testsegment kan det vara enklare att använda sökrutan för att hitta en specifik testgrupp. Du kan söka efter en testgrupp genom att:

* Testgruppens namn.
* Namnet på något av testsegmenten i testgruppen.
* Beskrivningen av testgruppen.

![](assets/search_and_filter_audience_lab.png)

Du kan också filtrera testgrupperna efter status. Alla tillgängliga statusvärden beskrivs i [statusavsnittet](../../features/audience-lab/audience-lab.md#status) nedan.

## [!UICONTROL Status] {#status}

Status för en testgrupp kan vara aktiv, schemalagd, pausad, utkast eller slutförd. Mer information om var och en av dem finns i tabellen nedan:

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Status </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktiv </span></b> </p> </td> 
   <td colname="col2"> <p>En <i>aktiv</i> testgrupp innebär att data för närvarande skickas till destinationer. Tryck på <b><span class="uicontrol"> Pausa test </span></b> på <b><span class="uicontrol"> </span></b> testgruppskortet om du vill pausa sändning av data till mål. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Schemalagd </span></b> </p> </td> 
   <td colname="col2"> <p>En <i>schemalagd</i> testgrupp är inte aktiv ännu men kan inte redigeras längre. Den aktiveras vid det startdatum som du valde i guiden <b>Skapa testgrupper</b> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausad </span></b> </p> </td> 
   <td colname="col2"> <p>En <i>pausad</i> testgrupp skickar för närvarande inga data till destinationerna. Tryck på <b><span class="uicontrol"> Aktivera </span></b> i <b><span class="uicontrol"> </span></b> testgruppskortet om du vill fortsätta skicka egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Utkast </span></b> </p> </td> 
   <td colname="col2"> <p>En <i>utkasttestgrupp</i> är ännu inte aktiv och kan fortfarande redigeras. Data skickas ännu inte till mappade mål. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Slutförd </span></b> </p> </td> 
   <td colname="col2"> <p>En <i>slutförd</i> testgrupp har nått slutdatumet som du valde i <b><span class="uicontrol"> guiden </span></b> Skapa testgrupper och har slutat skicka rapportdata. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Åtgärder </th> 
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Redigera </span></b> </p> </td>
   <td colname="col2"> <p>Tillgänglig <b>endast</b> för utkasttestgrupper. Gör att du kan återuppta <b><span class="uicontrol"> </span></b> guiden Skapa ny testgrupp. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pausa </span></b> </p> </td>
   <td colname="col2"> <p>Tillgängligt för aktiva testgrupper. Gör att du kan pausa sändning av testsegment till mål. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktivera </span></b> </p> </td>
   <td colname="col2"> <p>Tillgängligt för pausade testgrupper. Gör att du kan fortsätta skicka testsegmenten till mål. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Visa </span></b> </p> </td>
   <td colname="col2"> <p>Tillgängligt för slutförda testgrupper. Gör att du kan visa den rapportinformation som testet har genererat. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Duplicera </span></b> </p> </td>
   <td colname="col2"> <p>Gör att du kan skapa en ny testgrupp med samma konfiguration som den du duplicerar. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ta bort </span></b> </p> </td>
   <td colname="col2"> <p>Gör att du kan ta bort en testgrupp. Testsegmenten mappas inte om från destinationerna, baslinjesegmentet och konverteringsegenskaperna som är kopplade till testgruppen är fullt redigerbara. Du uppmanas att hämta CSV-filen när du tar bort en testgrupp för att spara rapporten om du vill. </p> </td>
  </tr>
 </tbody>
</table>