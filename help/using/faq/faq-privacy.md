---
description: Svar på vanliga frågor och problem som rör sekretess och data.
seo-description: Svar på vanliga frågor och problem som rör sekretess och data.
seo-title: Vanliga frågor om sekretess och datalagring
solution: Audience Manager
title: Vanliga frågor om sekretess och datalagring
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 96%

---


# Vanliga frågor om sekretess och datalagring {#privacy-and-data-retention-faq}

Svar på vanliga frågor och problem som rör sekretess och data.

<!-- faq_privacy.xml -->

## Vanliga frågor och svar om sekretess {#privacy-faq}

>[!TIP]
>
>Mer information finns på [Adobes sekretesscenter](https://www.adobe.com/se/privacy.html).

**Hur använder Audience Manager cookies och vilka cookies används?**

Se [Cookies för Audience Manager](https://docs.adobe.com/content/help/sv-SE/core-services/interface/ec-cookies/cookies-am.html).

**Kan Audience Manager-kunder i USA inrikta sig på EU-användare?**

Ja. Audience Manager fungerar med klienter som har internationella tillgångar och lager. EU har strikta dataskyddslagar, men Audience Manager har kunder som använder förstapartsdata för målgruppsanpassning i Europa. Audience Manager har stöd för anpassning till målgrupper i EU, men det är ditt ansvar att följa lokala dataskyddslagar.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Vanliga frågor om datalagring {#data-retention-faq}

I följande tabell anges lagringstiderna för olika datatyper och lagringssystem.

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
   <td colname="col2"> <p>120 dagar. </p> <p> Audience Manager tar bort användardata från våra backend-servrar 120 dagar efter att en användare senast besökte Audience Manager-plattformen. Om <span class="keyword"> Audience Manager</span> registrerar användaraktivitet inom denna 120-dagarscykel sparas data i ytterligare 120 dagar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-servrar </p> </td> 
   <td colname="col2"> <p> 14 dagar. </p> <p>Audience Manager tar bort användardata från våra edge-servrar 14 dagar efter att en användare senast besökte Audience Manager-plattformen. Om <span class="keyword"> Audience Manager</span> registrerar användaraktivitet inom denna 14-dagarscykel sparas data i ytterligare 14 dagar. Om användaren är aktiv igen efter 14-dagarsperioden finns en fördröjning mellan den första nya sidvisningen och när användaren kan åtgärdas. Det tar 6-18 timmar att få tillbaka hela profilen till Edge-centret efter mer än 14 dagars inaktivitet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Råloggar </p> </td> 
   <td colname="col2"> <p>180 dagar (tas bort efter 180 dagar utan aktivitet). </p> <p>Råloggar är data som tas emot av en edge-server via HTTP-anrop eller från onboardfiler som skickas till <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server-loggar </p> </td> 
   <td colname="col2"> <p><b>Rapporter</b> </p> <p>Loggfiler sparas för rapportering upp till 30 dagar. Vi lagrar inte omatchade loggar (dvs. loggar för vilka det inte finns någon ID-synkronisering mellan en besökares annonsserver-ID och <span class="keyword"> Audience Manager</span>-ID) i vår backend-server och matchade loggar som lagras i <span class="keyword"> Amazon S3</span> sparas i upp till 30 dagar. </p> <p><b>Verkställbara loggfiler</b> </p> <p>Både matchade och omatchade loggar sparas i upp till 30 dagar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profiler på CRM-nivå (autentiserade profiler) </p> </td> 
   <td colname="col2"> <p>Standardintervallet för TTL (time-to-live) för inaktiva profiler på CRM-nivå (kund-ID:n) är 24 månader. Du kan emellertid använda användargränssnittet i Audience Manager för att minska eller förlänga TTL-intervallet för inaktiva CRM-nivåprofiler mellan en månad och 5 år. Du kan göra det när du skapar eller redigerar en enhetsövergripande datakälla.</p> <p>Mer information finns i Inställningar för datakälla i <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Skapa en enhetsövergripande datakälla</a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID för mobila enheter </p> </td> 
   <td colname="col2"> <p>Lagringsvillkoren för mobila enhets-ID:n (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) följer de som beskrivs för backend-servrar och edge-servrar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kunddataflöden (CDF) </p> </td> 
   <td colname="col2"> <p>En CDF-fil innehåller samma data som ett <span class="keyword"> Audience Manager</span>-händelseanrop (/event) skickar till våra servrar. Lagringsperioden är 8 dagar. Mer information om CDF finns i introduktion till <a href="../features/cdf-files.md"> CDF</a> och vanliga frågor om <a href="../faq/faq-cdf.md"> CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappningar mellan synkroniserade ID:n </p> </td> 
   <td colname="col2"> <p>Livslängden för <a href="../features/administration/usage-limits.md#id-mapping-limits"> ID-mappningar</a> mellan cookie-ID:n för Audience Manager (<a href="../reference/ids-in-aam.md">unika användar-ID:n för Audience Manager eller UUID:n för AAM</a>) och cookie-ID:n från tredje part begränsas till 120 dagar. Livslängden för ID-mappningen återställs varje gång Audience Manager-cookien identifieras i Audience Manager-nätverket. Den senaste synkroniseringen av ID-mappning bevaras så länge tillhörande <a href="../reference/ids-in-aam.md">Audience Manager unika användar-ID (AAM UUID)</a> är giltigt.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inkommande data </p> </td> 
   <td colname="col2"> <p>Detta är inkommande data som ni skickar till <span class="keyword">Audience Manager</span> via FTP eller direkt till en <span class="keyword">Amazon S3</span>-katalog. Se <a href="../faq/faq-inbound-data-ingestion.md">Vanliga frågor och svar om inmatning av inkommande kunddata</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utgående data </p> </td> 
   <td colname="col2"> <p>Detta är satsvisa data som <span class="keyword"> Audience Manager</span> skickar till aktiveringspartners från tredje part. Lagringsperioden är 8 dagar. Mer information om utgående data finns i <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">Utgående satsvisa överföringar</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lagring av data för trait-kvalificering {#trait-qual}

Tabellen nedan listar lagringsalternativen för trait-kvalificering.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Trait-användning </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ta bort ett trait </p> </td> 
   <td colname="col2"> <p>Om du tar bort ett trait tas alla data om trait-kvalificering bort från alla användarprofiler som tidigare har kvalificerat för detta trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gränsen för traits är uppnådd </p> </td> 
   <td colname="col2"> <p>Vi har en gräns på 100 000 trait-kvalificeringar för varje användarprofil. Gränsen gäller autentiserade profiler och enhetsprofiler. Om en användarprofil når denna gräns raderas de äldsta trait-kvalifikationerna enligt först in, först ut. </p> <p>Mer information finns i <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"> Gräns för trait-kvalificering</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

