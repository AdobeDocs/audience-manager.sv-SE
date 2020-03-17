---
description: Audience Manager tar emot enorma mängder data varje dag. Detta påverkar hur lång tid det tar att bearbeta dina data och generera rapportresultat. Innehållet i det här avsnittet beskriver hur dessa tidsintervall påverkar ditt Audience Manager-konto. Dessutom är de tidsramar och scheman som beskrivs här endast allmänna riktlinjer. Dessa scheman utgör inte serviceavtal (SLA) eller åtaganden som rör dataleverans. Adobe förbehåller sig rätten att när som helst ändra tidsramar och tidsplaner utan föregående meddelande.
seo-description: Audience Manager tar emot enorma mängder data varje dag. Detta påverkar hur lång tid det tar att bearbeta dina data och generera rapportresultat. Innehållet i det här avsnittet beskriver hur dessa tidsintervall påverkar ditt Audience Manager-konto. Dessutom är de tidsramar och scheman som beskrivs här endast allmänna riktlinjer. Dessa scheman utgör inte serviceavtal (SLA) eller åtaganden som rör dataleverans. Adobe förbehåller sig rätten att när som helst ändra tidsramar och tidsplaner utan föregående meddelande.
seo-title: Hur dataleverans och bearbetningstider påverkar rapporter
solution: Audience Manager
title: Hur dataleverans och bearbetningstider påverkar rapporter
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Hur dataleverans och bearbetningstider påverkar rapporter{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager tar emot enorma mängder data varje dag. Detta påverkar hur lång tid det tar att bearbeta dina data och generera rapportresultat. Innehållet i det här avsnittet beskriver hur dessa tidsintervall påverkar ditt Audience Manager-konto. Dessutom är de tidsramar och scheman som beskrivs här endast allmänna riktlinjer. Dessa scheman utgör inte serviceavtal (SLA) eller åtaganden som rör dataleverans. Adobe förbehåller sig rätten att när som helst ändra tidsramar och tidsplaner utan föregående meddelande.

## Rapporteringsnummer {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

I följande tabell visas och beskrivs tidsintervallen i våra allmänna rapporter och realtidsrapporter.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datatyp </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Realtidsdata</b> </p> </td> 
   <td colname="col2"> <p> Dagens realtidsnummer är för timmarna 00:00 till 23:59:59 UTC från igår. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Allmänna rapportdata</b> </p> </td> 
   <td colname="col2"> <p>Informationen i de <a href="../reporting/general-reports.md#general-reports-overview"> allmänna rapporterna</a> är beroende av att andra jobbprocesser slutförs och mängden data som tas emot för en viss dag. Vanligtvis ska data i den allmänna rapporten <span class="wintitle"></span> uppdateras med 18:00 UTC varje dag. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inkommande och utgående filöverföringar {#inbound-outbound-file-transfers}

[!DNL Audience Manager] bearbetar och skickar inkommande och utgående [!UICONTROL Server-to-Server (S2S)] filöverföringar enligt de scheman som beskrivs i detta avsnitt. Med tanke på dessa tidsplaner och bryttider kan det finnas skillnader mellan segmentens realtids- och sluttider.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtyp </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Inkommande filinmatning (offlinedata)</b> </p> </td> 
   <td colname="col2"> <p>Filbearbetning utförs två gånger per dag. Dessa procedurer importerar data och förbereder dem för leverans. </p> <p>Filleveranstiderna varierar eftersom de påverkas av den totala mängden kunddata som behöver bearbetas. Du kan förvänta dig en maximal fördröjning på 48 timmar mellan den tidpunkt då filen överförs i <span class="keyword"> Audience Manager</span> och tills data är tillgängliga för rapportering och aktivering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Utgående (export) filer</b> </p> </td> 
   <td colname="col2"> <p>Filbearbetning och leverans sker en gång om dagen, kl. 14:00 UTC. Tänk på att bearbetningen och leveransen påverkas av det totala antalet filer och deras storlek. I vissa fall kan det dröja så länge som 24 timmar. När detta inträffar skickar <span class="keyword"> Audience Manager</span> två filer för en viss dag i stället för 1. Vi kommer att meddela våra kunder i de sällsynta fall där <span class="keyword"> Audience Manager</span> måste sluta bearbeta en fil helt och hållet. Med tanke på dessa förhållanden är det svårt att uppskatta leveranstider för utgående data. </p> <p>Om du vill ta reda på om du har fått en komplett uppsättning filer kontrollerar du tidsstämpeln och letar efter eventuella saknade dagar. Det här är en 13-siffrig UNIX UTC-tidsstämpel som registrerar tidpunkten när filen skapades. Se <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Utgående dataöverföringar</a>i realtid. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Vanliga frågor och svar om inkommande kunddata](../faq/faq-inbound-data-ingestion.md)

