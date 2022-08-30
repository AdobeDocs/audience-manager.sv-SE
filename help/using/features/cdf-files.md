---
description: Grundläggande information om CDF-filer (Customer Data Feed) och anvisningar om hur man kommer igång. Börja här om du är intresserad av att få CDF-filer eller bara vill ha mer information.
keywords: data från andra part;data från andra part;data från andra part;data från andra part
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Kunddataflöden
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 1%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Grundläggande information om [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) och anvisningar om hur du kommer igång. Börja här om du är intresserad av att få [!UICONTROL CDF] eller bara vill ha mer information.

## Filinnehåll och syfte {#file-contents-purpose}

En [!UICONTROL CDF]-fil innehåller samma data som ett [!DNL Audience Manager]-händelseanrop (`/event`) skickar till våra servrar. Detta inkluderar data som användar-ID:n, [!UICONTROL trait IDs], [!UICONTROL segment IDs]och alla andra parametrar som har hämtats av ett händelseanrop. Intern [!DNL Audience Manager] systemen bearbetar händelsedata till [!UICONTROL CDF] fil med innehåll ordnat i fält som visas i en angiven ordning. [!DNL Audience Manager] försöker generera [!UICONTROL CDF] filer per timme och lagrar dem i en säker, kundspecifik bucket på en [!DNL Amazon S3] server. Vi tillhandahåller dessa filer så att du kan arbeta med dem [!DNL Audience Manager] data utanför de gränser som våra användargränssnitt har.

>[!IMPORTANT]
>
>Observera följande begränsningar när du arbetar med CDF-filer:
>
>* Innan du konfigurerar leveransen av CDF-filer bör du kontrollera att du har rätt behörighet från tredjepartsleverantörer för export av egenskaper från tredje part. Audience Manager stöder för närvarande inte funktioner i användargränssnittet för att begära exporttillstånd för CDF-filer från tredjepartsleverantörer av data, så kontakta dem oberoende av varandra.
>* Du ska inte använda [!UICONTROL CDF] filer som en proxy för att övervaka sidtrafik, stämma av rapportavvikelser eller för fakturering osv.


## Komma igång {#getting-started}

Det finns ingen självbetjäningsprocess att starta [!UICONTROL CDF] filleverans. Kontakta [!DNL Audience Manager] konsult eller kundtjänst för att komma igång. Under implementeringen kan du [!DNL Audience Manager] kommer att

* Konfigurera [!DNL Amazon S3] lagringsbucket.
* Ange som skrivskyddad [!DNL S3] autentiseringsuppgifter för din fillagringshastighet. Du kommer inte att kunna se eller komma åt kataloger och filer som tillhör andra kunder.

Filmeddelanden och [!UICONTROL CDF] filerna visas i [!DNL S3] när de är klara för nedladdning. Du ansvarar för att övervaka och hämta filer från dina tilldelade [!DNL S3] katalog. Se [Bearbetningsmeddelanden för CDF-filer](#cdf-file-processing-notifications).

## Nästa steg {#next-steps}

avsnitten nedan och [Vanliga frågor om kunddataflöden](../faq/faq-cdf.md) kan hjälpa dig att bli mer bekant med den här tjänsten.

## [!UICONTROL Customer Data Feed] Innehåll som definierats {#cdf-defined}

Listar och definierar dataelement och arrayer i en [!UICONTROL CDF] fil, efter utseendeordning. Definitionerna innehåller datatyper, men den här informationen ingår inte i en [!UICONTROL CDF] -fil.

>[!IMPORTANT]
>
>Händelsepixlar exkluderas som standard i CDF-konfigurationer. Se till att du anger i din begäran till kundtjänst om du vill att händelsepixlar ska inkluderas i dina CDF-filer. Varje händelsepixel fylls i som en unik rad i dina CDF-filer.

## Definitioner {#definitions}

A [!UICONTROL CDF] filen innehåller några eller alla fält som definieras nedan. Mer information om intern filordning finns i [Filstruktur för kunddatafeed](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Datatyper </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>Tidsstämpel </p> </td> 
   <td colname="col3"> <p>Den tid en CDF-fil bearbetades av <span class="wintitle"> Datainsamlingsservrar</span> (DCS). Tidsstämpeln använder <i>yyyy-mm-dd hh:mm:ss</i> format och anges i UTC-tidszonen. </p> <p> <p>Obs! Händelsetiden <i>är inte</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">Tidpunkten för sidhändelsen eller själva händelsesammanropet, men den kan vara nära den tidpunkten. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Relaterat till DCS-timmen i filnamnet. Se även <a href="#different-processing-times"> Filnamnstider för kunddatafeed och filinnehållstider..</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>Det här är <span class="wintitle"> Unikt användar-ID</span> (UUID), som är ett 38-siffrigt enhets-ID för besökaren på platsen. Se även <a href="../reference/ids-in-aam.md"> Index för ID:n i Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numeriskt </p> </td> 
   <td colname="col3"> <p>ID:t för behållaren som aktiverar ID-synkronisering. Det här fältet fylls bara i om du anger behållar-ID i <i>d_nsid</i> -fält i webbplatsimplementeringen. I annat fall inkluderas inte standardvärdet 0 i CDF-filer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Numerisk array </p> </td> 
   <td colname="col3"> <p>En matris med trait ID:n som innehåller alla egenskaper som en besökare har realiserat (kvalificerat för) i händelseanropet. </p> <p>Observera att arrayen kan innehålla egenskaper som besökaren har kvalificerat sig för tidigare och för vilka de kvalificerar sig igen genom det här händelseanropet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Numerisk array </p> </td> 
   <td colname="col3"> <p>En array med segment-ID:n som innehåller alla segment som en besökare realiserat (kvalificerat för) i händelseanropet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>En sträng som hämtar alla parametrar (variabler, ID:n, nyckelvärdepar, enhets-ID:n med mera) har skickats in i händelseanropet. </p> <p>Kortare exempel: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>Den okodade URL:en för den refererande sidan (om sådan finns). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>IP-adressen för den besökare som fångats in i händelseanropet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) som tilldelats besökaren. Se även <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies och Adobe Experience Platform Identity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Numerisk array </p> </td> 
   <td colname="col3"> <p>En array med segment-ID:n som innehåller segment som redan realiserats och nya segment som besökaren är kvalificerad för. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Numerisk array </p> </td> 
   <td colname="col3"> <p>En matris med första och tredje parts trait-ID:n som innehåller tidigare realiserade egenskaper och nya egenskaper som besökaren har kvalificerat sig för sedan den senaste datamatningen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Filstruktur {#cdf-file-structure}

Visar och definierar datastrukturen för en [!UICONTROL CDF] -fil. Detta inkluderar datasekvens, fältavgränsare och avgränsare, datamappning och exempelfil.

## Identifierare och sekvens för datafält {#identifiers-and-sequence}

[!UICONTROL CDF] filer innehåller inte taggade kolumner eller fältrubriker. I stället [!UICONTROL CDF] filen definierar fält och arrayer med icke-utskrivbara [!DNL ASCII] tecken. Dessutom [!UICONTROL CDF] -filen listar varje fält och array i en viss ordning. Genom att förstå fältidentifierarna och ordningen kan du tolka filen korrekt.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF-filelement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fältavgränsare och avgränsare </p> </td> 
   <td colname="col2"> <p>Dessa tecken som inte skrivs ut definierar elementen och strukturen i CDF-filen: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> eller <code> ^A</code>) separerar data i enskilda fält med en utrymmesindikator som inte skrivs ut. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> eller <code> ^B</code>) avgränsar data i en array och begär parametrar. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> eller <code> ^C</code>) definierar nyckelvärdepar. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fältsekvens </p> </td> 
   <td colname="col2"> <p> <p>Viktigt: <span class="keyword"> Audience Manager</span> förbehåller sig rätten att lägga till nya fält i slutet av CDF-filen i framtida versioner. Detta innebär att den tekniska utformningen av filtolkningssystemet inte ska anta ett fast antal kolumner (även om det kan anta en fast ordning för befintliga kolumner).</p> </p> <p>Data i CDF-filen visas i den ordning som visas nedan. /N kan visas i stället för något av dessa fält, vilket anger ett null-värde.</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Händelsetid </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Enhet </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">Behållar-ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Realiserade egenskaper </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Realiserade segment </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Begärandeparametrar </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referent </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP-adress </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud enhets-ID (eller MID). Se även <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies och Adobe Experience Platform Identity Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Alla segment </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Alla egenskaper </li> 
     </ol> </p> <p>Fältbeskrivningar finns i <a href="#cdf-defined"> Innehåll för kunddatafeed definierad</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Filöversikt {#cdf-file-map}

[!UICONTROL CDF] fildata visas i den ordning som visas nedan.

![](assets/sequence-map.png)

## Identifiera arrayer

Arrayer i en [!UICONTROL CDF] filen börjar och slutar med `Ctrl + a` fältavgränsare. Detta gör att det första elementet i en array visas som ett fristående datafält. Den [!UICONTROL traits] array börjar med `^A1234`. Arrayavgränsaren och ID:t `^B5678` följer den här posten. Därför kan du vara frestad att tro att det första elementet i [!UICONTROL traits] matrisen är ID 5678 (eftersom den börjar med `^B`). Detta är inte fallet, och därför måste du känna till en datafils sekvens och struktur. Även om det första elementet i [!UICONTROL trait] arrayen (eller någon annan array i en [!UICONTROL CDF] fil) börjar med `^A`definierar utseendeordningen eller placeringen i filen början av en array. Och det första elementet i en array separeras alltid från föregående post med `^A`.

## Exempel [!UICONTROL CDF] Fil {#sample-file}

Ett exempel [!UICONTROL CDF] filen kan se ut ungefär så här. Vi har infogat radbrytningar i det här exemplet för att det ska passa in på sidan.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Namngivningskonventioner {#cdf-naming-conventions}

Avsnitten nedan listar och definierar elementen i [!UICONTROL CDF] filnamn.

## [!UICONTROL CDF] Filnamn: Syntax och exempel {#cdf-file-name}

En typisk [!UICONTROL CDF] filnamnet innehåller de element som anges nedan. Obs! *kursiv* anger en variabelplatshållare:

### Syntax

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### Exempel

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

I [!DNL S3] lagringsintervall sorteras filerna i stigande ordning efter partner-ID ([!UICONTROL PID]), dag och timme.

## [!UICONTROL CDF] Filnamnselement definierade {#cdf-file-name-elements}

I följande tabell listas och definieras elementen i en [!UICONTROL CDF] filnamn.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filnamnselement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Det här är standardrotlagringskassetten för din CDF-fil på en Amazon S3-server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>Namnet på den skrivskyddade S3-bucket som innehåller dina CDF-filer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Det datum då filen bearbetades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Ett tidsvärde uttryckt i 24-timmarsnotation och angivet i UTC-tidszonen. Se även <a href="#different-processing-times"> Filnamnstider för kunddatafeed och filinnehållstider..</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Ditt partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Värden som identifierar filsekvensen. Sekvensen ökar enligt följande: 0_0_0, 0_1_0, 0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Ett GZIP-filtillägg. CDF-filer är gzip-komprimerade. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Filbearbetningsmeddelanden {#cdf-file-processing-notifications}

[!DNL Audience Manager] skriver en `.info` till [!DNL S3] för att ta reda på när [!UICONTROL Customer Data File] ([!UICONTROL CDF]) kan hämtas. The `.info` filen innehåller också [!DNL JSON] formaterade metadata om innehållet i [!UICONTROL CDF] filer. I det här avsnittet finns information om syntaxen och fälten som används i den här meddelandefilen.

## Exempelinformationsfil {#sample-info-file}

Varje `.info` filen innehåller `Files` och `Totals` -avsnitt. The `Files` -avsnittet innehåller en array som innehåller specifika mått för varje timfil. The `Totals` -avsnittet innehåller mätvärden som är sammanställda över hela [!UICONTROL CDF] filer för en viss dag. Innehållet i `.info` filen kan se ut ungefär som i följande exempel.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Fält för informationsfil definierade {#info-file-fields-defined}

I följande tabeller listas och definieras elementen i en [!UICONTROL CDF] `.info` -fil.

### Filobjekt

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>Startar arrayen som innehåller metadata om dina CDF-filer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Filstorlek i byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. Siffran efter bindestrecket visar antalet delar som används för att skapa filen under överföringen av flera delar. The <code> ETag</code> är inte identisk med filens MD5-kontrollsumma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Filnamnet. Se <a href="#cdf-naming-conventions"> Namnkonventioner för kunddataflödesfiler</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Ett indexvärde för varje fil. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Summobjekt

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>Startar objektet som innehåller aggregerade data om alla dina CDF-filer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Den dag som informationen är tillgänglig. Användningsområden <i>yyyy-mm-dd</i> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>Timmen som data är tillgängliga för. Använder 24-timmarsformat som angetts i UTC-tidszon. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Den totala storleken för alla dina CDF-filer för det datumet i byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Totalt antal filer som överförts till din S3-katalog. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Filnamnstiderna och filinnehållstiderna skiljer sig åt {#different-processing-times}

Dina [!UICONTROL CDF] filen innehåller tidsstämplar i filnamnet och filinnehållet. Dessa tidsstämplar registrerar olika händelseprocesser för samma [!UICONTROL CDF] -fil. Det är inte ovanligt att olika tidsstämplar visas i namnet och innehållet i samma fil. Genom att förstå varje tidsstämpel kan du undvika vanliga misstag när du arbetar med dessa data eller försöker sortera dem efter tid.

## Hitta [!UICONTROL CDF] Tidsstämplar {#locating-timestamps}

[!UICONTROL CDF] filer spelar in olika tid på två olika platser.

![](assets/cdf-timestamp.png)

## Förstå skillnaden mellan tidsstämplar {#understanding-timestamps}

I följande tabell finns mer information om [!UICONTROL CDF] tidsstämplar och information om hur de används.

| Tidsstämpelplats | Beskrivning |
|--- |--- |
| Filnamn | Tidsstämpeln i [!DNL CDF] filnamnet anger när [!DNL Audience Manager] började förbereda filen för leverans. Den här tidsstämpeln anges i [!DNL UTC] tidszon. Den använder `hour=` parameter, med tiden formaterad som en tvåsiffrig timme med 24 timmars notation. Den här tiden kan skilja sig från den händelsetid som spelas in i filinnehållet. När du arbetar med [!DNL CDF] filer, ibland märker du att [!DNL S3] Bucket är tomt under en viss timme. En tom bucket betyder något av följande:<ul><li>Det finns inga data för just den timmen. </li><li> Våra servrar är mycket belastade och kan inte bearbeta filer på en viss timme. När servern fångar upp placerar den de filer som borde ha gått in i en tidigare tidsmarkeringsfil i en hink med ett senare tidsvärde. Du kommer till exempel att se det här när en fil som borde ha varit inom timmen 17, visas inom timmen 18, (med `hour=18` i filnamnet). I det här fallet började servern förmodligen bearbeta filen på timme 17, men kunde inte slutföra den inom det tidsintervallet. I stället skickas filen till nästa timtidsintervall.</li></ul><br>**Viktigt**: Använd inte filnamnets tidsstämpel för att gruppera händelser efter tid. Om du behöver gruppera efter tid använder du `EventTime` tidsstämpel i filinnehållet. |
| Filinnehåll | Tidsstämpeln i [!DNL CDF] filinnehållet markerar när [!DNL Data Collection Servers] började bearbeta filen. Den här tidsstämpeln anges i [!DNL UTC] tidszon. Den använder `EventTime` fält, med tid formaterad som *`yyyy-mm-dd hh:mm:ss`*. Den här tiden ligger nära den faktiska tiden för händelsen på sidan, men kan vara en annan än timindikatorn i filnamnet. <br> **Tips**: Till skillnad från `hour=` tidsstämpel i filnamnet kan du använda `EventTime` för att gruppera data efter tid. |

>[!MORELIKETHIS]
>
>* [Vanliga frågor om anpassade dataflöden](../faq/faq-cdf.md)

