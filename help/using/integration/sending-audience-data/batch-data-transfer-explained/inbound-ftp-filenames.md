---
description: Beskriver obligatoriska fält, syntax, namnkonventioner och filstorlekar som du måste följa när du skickar data till Audience Manager. Ange namn och storlek för filerna enligt dessa specifikationer när du skickar data till en Audience Manager FTP-katalog.
seo-description: Beskriver obligatoriska fält, syntax, namnkonventioner och filstorlekar som du måste följa när du skickar data till Audience Manager. Ange namn och storlek för filerna enligt dessa specifikationer när du skickar data till en Audience Manager FTP-katalog.
seo-title: Krav på FTP-namn och filstorlekar för inkommande datafiler
solution: Audience Manager
title: Krav på FTP-namn och filstorlekar för inkommande datafiler
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: f037a12af641da44ed67e62a249c41487da7ac07
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 6%

---


# [!DNL FTP] Krav för namn och filstorlek för inkommande datafiler {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Beskriver obligatoriska fält, syntax, namnkonventioner och filstorlekar som du måste följa när du skickar data till [!DNL Audience Manager]. Ange namn och storlek för filerna enligt dessa specifikationer när du skickar data till en Audience Manager- [!DNL FTP] katalog.

>[!WARNING]
>
>We are gradually phasing out support for [!DNL FTP] configurations. While inbound data file ingestion is still supported in existing [!DNL FTP] integrations, we strongly recommend using [!DNL Amazon S3] to onboard offline data for new integrations. Mer information finns i [Krav på Amazon S3-namn och filstorlekar för inkommande datafiler](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

>[!NOTE]
>
>Textformaten (`monospaced text`, *kursiv*, parenteser `[ ]` `( )` etc.) i det här dokumentet anger kodelement och alternativ. Mer information finns i [Formatkonventioner för kod- och textelement](../../../reference/code-style-elements.md).

## Filnamnssyntax {#file-name-syntax}

[!DNL FTP] filnamn innehåller följande obligatoriska och valfria element:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Information om andra godkända filnamnsformat finns i [Anpassade partnerintegreringar](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] endast bearbetar [!DNL ASCII] och [!DNL UTF-8] kodade filer.

### Namnge element

Tabellen definierar elementen i ett [!DNL FTP] filnamn.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filnamnselement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Sökvägen till och namnet på FTP-katalogen i <span class="keyword"> Audience Manager</span> . Kontakta kontohanteraren för att få information om FTP-katalogen och autentiseringsuppgifter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Ett ID som talar om för <span class="keyword"> Audience Manager</span> om en datafil innehåller egna användar-ID:n, Android-ID:n, iOS-ID:n eller andra ID:n som tillhör <a href="/help/using/features/global-data-sources.md"> globala datakällor</a>. Följande alternativ godkänns:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>ID för datakälla (även kallat Data Provider ID):</b> Detta är ett unikt ID som Audience Manager tilldelar en datakälla (se Audience Manager <a href="/help/using/reference/ids-in-aam.md"> index för ID:n </a>). Använd det här tilldelade ID:t i ett filnamn när du skickar in data som innehåller dina egna användar-ID:n. Till exempel instruerar <code>...ftp_dpm_21_123456789.sync</code> <span class="keyword"> Audience Manager</span> att lägga in data i ID:n som tillhör datakällan 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID):</b> Använd ID 20914 i ett datafilnamn om det innehåller Android-ID:n. Du måste använda fältet <code><i>_DPID_TARGET_DATA_OWNER</i></code> när du använder Android-id:n. Till exempel anger <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> <span class="keyword"> Audience Manager</span> att datafilen bara innehåller Android-id:n och att ID:n ska kvalificera sig för de egenskaper som tillhör <code><i>_DPID_TARGET_DATA_OWNER</i></code> datakällan.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS-ID (IDFA):</b> Använd ID 20915 i ett datafilnamn om det innehåller iOS-ID:n. Du måste använda fältet <code><i>_DPID_TARGET_DATA_OWNER</i></code> när du använder iOS-ID:n. Till exempel anger <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> <span class="keyword"> Audience Manager</span> att datafilen endast innehåller iOS-ID:n och att ID:n ska kvalificera sig för de egenskaper som tillhör <code><i>_DPID_TARGET_DATA_OWNER</i></code> datakällan.</li>
     <li> <b>ID som tillhör andra globala datakällor</b>: Du kan lägga in Roku ID:n för Advertising (RIDA), Microsoft Advertising ID:n (MAID) och andra ID:n. Använd det ID som motsvarar varje datakälla, enligt beskrivningen i artikeln <a href="/help/using/features/global-data-sources.md"> om</a>globala datakällor.</li> 
    </ul> <p> <p>Obs!  Blanda inte ID-typer i datafilerna. Om ditt filnamn till exempel innehåller Android-identifieraren ska du inte ange iOS-ID eller dina egna ID:n i datafilen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Det här fältet anger för Audience Manager vilken datakälla data ska sparas i. Det här fältet är obligatoriskt om du ställer in DPID på ett Android-id, iOS-ID eller ett annat ID som tillhör globala datakällor. På så sätt kan <span class="keyword"> Audience Manager</span> länka fildata tillbaka till din organisation. </p> <p>Exempel: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> anger för Audience Manager att du kvalificerar kund-ID:n som tillhör datakällan 33 för egenskaper eller signaler som tillhör datakällan 21. </li> 
     <li> <b>Android ID (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> anger för <span class="keyword"> Audience Manager</span> att datafilen endast innehåller Android ID:n och att ID:n ska kvalificera sig för de egenskaper som tillhör datakällan 21.</li> 
     <li> <b>iOS-ID (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> anger för <span class="keyword"> Audience Manager</span> att datafilen endast innehåller iOS-ID:n och att ID:n ska kvalificera sig för de egenskaper som tillhör datakällan 21.</li>
     <li> <b>ID som tillhör andra globala datakällor</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> anger för <span class="keyword"> Audience Manager</span> att datafilen endast innehåller Roku ID:n och att ID:n ska kvalificera sig för de egenskaper som tillhör datakällan 21. Använd det ID som motsvarar varje datakälla, enligt beskrivningen i artikeln <a href="/help/using/features/global-data-sources.md"> om</a>globala datakällor.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synkroniseringsalternativ som inkluderar: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normalt scenario när externa dataleverantörer skickar egenskaper per användare för att läggas till eller tas bort i Audience Manager-systemet. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Gör att kunder och dataleverantörer kan skicka en lista över egenskaper per användare som ska skriva över den här användarens befintliga egenskaper för en viss datakälla i Audience Manager. Du behöver inte inkludera alla användare i en överskrivningsfil. Inkludera endast de användare som du vill ändra. Traits som inte har tilldelats måldatakällan raderas inte. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Ett heltal. Används när du delar upp stora filer i flera delar för att förbättra bearbetningstiden. Talet anger vilken del av originalfilen du skickar in. </p> <p>För effektiv filbearbetning kan du dela datafilerna på det sätt som anges: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Okomprimerad: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimerad: 200-300 MB </li> 
    </ul> <p>Se de två första <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> filnamnsexemplen</a> nedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>En 10-siffrig UTC UNIX-tidsstämpel i sekunder. Tidsstämpeln gör varje filnamn unikt. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip är det tillåtna komprimeringsformatet för ett FTP-filnamn. Om du använder filkomprimering bör du kontrollera att filnamnet har rätt filtillägg. </p> <p>Komprimerade filer måste vara 3 GB eller mindre. Om filerna är större bör du kontakta kundtjänst. Även om Audience Manager kan hantera stora filer kan vi hjälpa dig att minska filstorleken och effektivisera dataöverföringen. Se <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Filkomprimering för inkommande dataöverföringsfiler</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel på filnamn {#file-name-examples}

I följande exempel visas korrekt formaterade filnamn. Filnamnen kan se likadana ut.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Hämta](assets/ftp_dpm_1234_1445374061.overwrite) exempelfilen om du behöver fler exempel. Den här filen sparas med `.overwrite` filtillägget. Öppna med en enkel textredigerare.

## Godkända filstorlekar {#accepted-file-sizes}

Titta på bilderna nedan om du snabbt/tidigast vill bearbeta dina filer och om du vill ha filstorleksbegränsningar när du skickar data till en [!DNL Audience Manager] / [!DNL FTP] katalog.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtyp </th> 
   <th colname="col2" class="entry"> Optimal storlek </th> 
   <th colname="col3" class="entry"> Maxstorlek </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Komprimerad</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Okomprimerad</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Krav på Amazon S3-namn och filstorlekar för inkommande datafiler](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

