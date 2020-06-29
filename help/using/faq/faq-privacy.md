---
description: Svar på vanliga sekretessfrågor och datarelaterade frågor eller frågor.
seo-description: Svar på vanliga sekretessfrågor och datarelaterade frågor eller frågor.
seo-title: Vanliga frågor om sekretess och datalagring
solution: Audience Manager
title: Vanliga frågor om sekretess och datalagring
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Vanliga frågor om sekretess och datalagring{#privacy-and-data-retention-faq}

Svar på vanliga sekretessfrågor och datarelaterade frågor eller frågor.

<!-- faq_privacy.xml -->

## Frågor och svar om sekretess {#privacy-faq}

>[!TIP]
>
>Mer information finns på [Adobes sekretesscenter](https://www.adobe.com/privacy.html) .

**Hur använder Audience Manager cookies och vilka cookies används?**

Se [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html).

**Kan Audience Manager kunder i USA rikta in sig på EU:s fastigheter?**

Ja. Audience Manager samarbetar med kunder som har internationella tillgångar och inventarier. EU har strikta integritetslagar, men Audience Manager har kunder som använder förstahandsdata för målgruppsanpassning i Europa. Audience Manager kan stödja målgruppsanpassning till EU-målgrupper, men det är ditt ansvar att följa lokala sekretessbestämmelser.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Vanliga frågor om datalagring {#data-retention-faq}

I följande tabell visas kvarhållningstiderna för olika datatyper och lagringssystem.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datatyp, källa eller lagring </th> 
   <th colname="col2" class="entry"> Datalagringsperiod </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Serverlösningar </p> </td> 
   <td colname="col2"> <p>120 dagar. </p> <p> Audience Manager tar bort användardata från våra backend-servrar 120 dagar efter att en användare senast visats på Audience Manager-plattformen. Om <span class="keyword"> Audience Manager</span> registrerar användaraktivitet inom denna 120-dagarscykel sparar vi dessa data i ytterligare 120 dagar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-servrar </p> </td> 
   <td colname="col2"> <p> 14 dagar. </p> <p>Audience Manager tar bort användardata från våra edge-servrar 14 dagar efter att en användare senast sågs på Audience Manager-plattformen. Om <span class="keyword"> Audience Manager</span> registrerar användaraktivitet inom denna 14-dagarscykel sparar vi dessa data i ytterligare 14 dagar. Om användaren aktiveras igen efter 14-dagarsperioden kommer det att uppstå en fördröjning mellan den första nya sidvyn och när användaren blir åtgärdbar. Det tar 6-18 timmar att få ut hela profilen tillbaka till kantcentret efter mer än 14 dagars inaktivitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Råloggar </p> </td> 
   <td colname="col2"> <p>180 dagar (tas bort efter 180 dagar utan aktivitet). </p> <p>Raw-loggar är data som tas emot av en edge-server via HTTP-anrop eller från onboardfiler som skickas till <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server-loggar </p> </td> 
   <td colname="col2"> <p><b>Rapporter</b> </p> <p>Loggfiler sparas för rapportering i upp till 30 dagar. Vi lagrar inte omatchade loggar (dvs. loggar för vilka det inte finns någon ID-synkronisering mellan en besökares annons-server-ID och <span class="keyword"> Audience Manager</span> -ID) i vår backend-lagring, och matchade loggar som lagras i <span class="keyword"> Amazon S3</span> sparas i upp till 30 dagar. </p> <p><b>Åtgärdsbara loggfiler</b> </p> <p>Både matchade och omatchade loggar sparas i upp till 30 dagar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-nivåprofiler (autentiserade profiler) </p> </td> 
   <td colname="col2"> <p>Standardintervallet för TTL (time-to-live) för inaktiva CRM-nivåprofiler är 24 månader. Du kan emellertid använda användargränssnittet i Audience Manager för att minska eller förlänga TTL-intervallet för inaktiva CRM-nivåprofiler mellan en månad och 5 år. Du kan uppnå detta när du skapar eller redigerar en datakälla för olika enheter.</p> <p>Mer information finns i Inställningar för datakälla i <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Skapa en datakälla för olika enheter </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID för mobila enheter </p> </td> 
   <td colname="col2"> <p>Kvarhållningsvillkoren för mobila enhets-ID:n (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) följer den gräns som beskrivs i de första två raderna, serverdelen och edge-servrarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CDF (Customer Data Feeds) </p> </td> 
   <td colname="col2"> <p>En CDF-fil innehåller samma data som ett <span class="keyword"> Audience Manager</span> -händelseanrop (/event) skickar till våra servrar. Kvarhållningsperioden är 8 dagar. Mer information om CDF finns i Vanliga frågor om <a href="../features/cdf-files.md"> CDF Intro</a> och <a href="../faq/faq-cdf.md"> CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappningar mellan synkroniserade ID:n </p> </td> 
   <td colname="col2"> <p>Livslängden för <a href="../features/administration/usage-limits.md#id-mapping-limits"> ID-mappningar</a> mellan cookie-ID:n för Audience Manager (unika användar-ID:n för<a href="../reference/ids-in-aam.md">Audience Manager eller UUID:n</a>för AAM) och cookie-ID:n från tredje part är begränsad till 120 dagar. Livslängden för ID-mappningen återställs varje gång cookie-filen för Audience Manager visas i nätverket Audience Manager. Den senaste synkroniseringen av ID-mappning bevaras under hela den tid som det associerade <a href="../reference/ids-in-aam.md">Audience Manager-unika användar-ID:t (AAM UUID)</a>är giltigt.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inkommande data </p> </td> 
   <td colname="col2"> <p>Detta är inkommande data som du skickar till <span class="keyword"> Audience Manager</span> via FTP eller direkt till en <span class="keyword"> Amazon S3</span> -katalog. Se Vanliga frågor och svar om <a href="../faq/faq-inbound-data-ingestion.md"> inkommande kunddatainmatning</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utgående data </p> </td> 
   <td colname="col2"> <p>Detta är batchdata som <span class="keyword"> Audience Manager</span> skickar till aktiveringspartners. Kvarhållningsperioden är 8 dagar. Mer information om utgående data finns i <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Utgående batchöverföringar</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bevaring av anpassningsdata {#trait-qual}

Tabellen nedan listar bibehållningsalternativen för kvalifikationer.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Trait Operation </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ta bort en egenskap </p> </td> 
   <td colname="col2"> <p>Om du tar bort ett drag tas alla data om kvalificering av egenskaper bort från alla användarprofiler som tidigare har kvalificerat sig för egenskapen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fackgränsen har nåtts </p> </td> 
   <td colname="col2"> <p>Vi inför en gräns på 100 000 kvalifikationer för varje användarprofil. Gränsen gäller autentiserade profiler och enhetsprofiler. Om en användarprofil når denna gräns raderas först-in-och-ut-kursen för de äldsta egenskaperna. </p> <p>Mer information finns i vår <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

