---
description: Beskriver obligatoriska fält, syntax och konventioner som används för att namnge en utgående datafil.
seo-description: Beskriver obligatoriska fält, syntax och konventioner som används för att namnge en utgående datafil.
seo-title: Syntax och exempel för utgående datafilnamn
solution: Audience Manager
title: Syntax och exempel för utgående datafilnamn
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
translation-type: tm+mt
source-git-commit: b32283a6cb3d001f0a1fc85f3e63fba651f32760

---


# Namn på utgående datafil: Syntax och exempel{#outbound-data-file-name-syntax-and-examples}

Beskriver obligatoriska fält, syntax och konventioner som används för att namnge en utgående datafil.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>Formatelement (`monospaced text`, *kursiv*, hakparenteser `[ ]` `( )`osv.) i det här dokumentet anger kodelement och alternativ. Mer information finns i [Formatkonventioner för kod- och textelement](../../../reference/code-style-elements.md).

## Syntax- och filnamnselement {#syntax-file-name}

Utgående filnamn innehåller följande element. Alla element nedan är valfria.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parametrar

Tabellen definierar elementen i ett namn på en utgående datafil.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filnamnselement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Hänvisar till dataöverföringsmetoderna. Överföringsmetoderna omfattar: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Överföring med SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> - överföring till <span class="keyword"> Amazon AWS </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>Mål-ID. </p> <p>I <span class="keyword"> Audience Manager </span>är ett mål den instans av integreringen där du kan mappa dina målsegment. Kunderna kan ha flera destinationer beroende på verksamhetens behov. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Data-provider eller ID för datakälla. Detta ID identifierar typen av användar-ID som finns i filinnehållet. De vanligaste användar-ID-nycklarna är: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">2014 - <span class="keyword"> Google Advertiser ID </span> (raw, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">2015 - Apple ID för <span class="keyword"> annonsörer </span> (raw, unhashed) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">Leverantörs-ID - Användar-ID:n från tredje part (webb/cookie) </li> 
     </ul> </p> <p>Mer information finns i <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">Globala datakällor</a> .</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> Kundidentifieraren från tredjepartsplattformen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>Synkroniseringsläget är en makroplatshållare som lägger till en etikett till filnamnet baserat på synkroniseringstyp. Synkroniseringstyperna omfattar fullständig och inkrementell. De visas i filnamnet som <code> iter </code> eller <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Anger en iterativ eller stegvis synkronisering. En inkrementell fil innehåller endast nya data som samlats in sedan den senaste synkroniseringen. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Anger en fullständig synkronisering. En helt synkroniserad fil innehåller gamla data och alla nya data som samlats in sedan den senaste synkroniseringen. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>En 13-siffrig UNIX-tidsstämpel i millisekunder i UTC-tidszonen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Ett heltal. Identifierar en del av en fil som har delats upp i flera delar för att förbättra bearbetningstiden. Talet anger vilken del av den ursprungliga filen som data hör till.</p>  <p>Heltalet måste vara minst 3 siffror långt, föregånget av nollor, om delningsstorleken är mindre än 100 delar.</p>  <p>Originalfilen kommer inte att ha något delat nummer. Den första delade filen avslutas med 001. Se exempel nedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP-komprimering. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel på filnamn {#file-name-examples}

### Scenario 1

Filer som skickas till en [!DNL Amazon S3] plats med *`PID_ALIAS="XYZCustomer"`* och [!DNL Google Advertiser IDs] i filinnehållet.

Exempel: inkrementella filer:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Exempel: fullständiga filer:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Scenario 2

Filer som skickas till [!DNL FTP] platsen, utan *`PID_ALIAS`* och med [!DNL Apple Advertiser IDs] i filinnehållet:

Exempel: inkrementella filer:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Exempel: fullständiga filer:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Scenario 3**: Filer som skickas till [!DNL FTP] platsen, med användar-ID *`PID_ALIAS="XYZCustomer"`* och med användar-ID från tredje part i filinnehållet ( *`Vendor ID=45454`*):

Exempel: inkrementella filer:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Exempel: fullständiga filer:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Innehåll i utgående datafil: Syntax och parametrar {#outbound-contents-syntax}

Beskriver obligatoriska fält, syntax och konventioner som används för att organisera information i en utgående datafil. Formatera data enligt dessa specifikationer.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>Formatelement (`monospaced text`, *kursiv*, hakparenteser `[ ]` `( )`osv.) i det här dokumentet anger kodelement och alternativ. Mer information finns i [Formatkonventioner för kod- och textelement](../../../reference/code-style-elements.md).

### Syntax

Fält i datafilen visas i följande ordning:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parametrar

Tabellen innehåller variabler som definierar innehållet i en datafil.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>Ett unikt användar-ID som tilldelats av <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Avgränsa UUID- och segmentdata med ett blanksteg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>Det segment-ID som en besökare tillhör. Avgränsa flera segment med kommatecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>Det segment-ID som användaren diskvalificerades från. Avgränsa flera segment med kommatecken. Med en fullständig synkronisering kan du ignorera de borttagna segmenten eftersom datafilen innehåller den fullständiga listan över aktuella segment för användaren. Vanligtvis vill du veta mer om segment som en användare tillhör i stället för de som de har tagits bort från. Se även <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Namn på utgående datafil: Syntax och exempel </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exempel: Grundläggande filformat

En korrekt formaterad datafil kan se ut som i följande exempel. Den här filposten anger att en användare kvalificerar sig för segmenten 24, 26 och 27. Om det behövs avgränsar ett blanksteg ID:n för `UUID` och segment. Ett annat utrymme avgränsar uppsättningarna med segment-ID:n. I det här exemplet tillhör en användare segmenten 24, 26 och 27. De har tagits bort från segmenten 25 och 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
