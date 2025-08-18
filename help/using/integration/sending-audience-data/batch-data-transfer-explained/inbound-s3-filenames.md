---
description: Beskriver obligatoriska fält, syntax, namnkonventioner och filstorlekar som du måste följa när du skickar data till Audience Manager. Ange namn och storlek för filerna enligt dessa specifikationer när du skickar data till en Audience Manager-/Amazon S3-katalog.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Amazon S3-namn och filstorlek för inkommande datafiler
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 1%

---

# Krav för namn och filstorlek för [!DNL Amazon S3] för inkommande datafiler {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Beskriver obligatoriska fält, syntax, namnkonventioner och filstorlekar som du måste följa när du skickar data till [!DNL Audience Manager]. Ange namn och storlek för filerna enligt dessa specifikationer när du skickar data till en [!DNL Audience Manager] / [!DNL Amazon S3] -katalog.

>[!NOTE]
>
>Textformaten (`monospaced text`, *kursiv*, hakparenteser `[ ]` `( )` osv.) i det här dokumentet anger kodelement och alternativ. Mer information finns i [Formatkonventioner för kod- och textelement](../../../reference/code-style-elements.md).

## Filnamnssyntax {#file-name-syntax}

[!DNL S3]-filnamn innehåller följande obligatoriska och valfria element:

* **[!DNL S3]-prefix:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Filnamnselement:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Information om andra godkända filnamnsformat finns i [Anpassade partnerintegreringar](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] bearbetar bara [!DNL ASCII]- och [!DNL UTF-8]-kodade filer.

### Namnelement

Tabellen definierar elementen i ett [!DNL S3]-filnamn.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namnelement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Sökvägen till och namnet på din Amazon S3-bucket. Kontakta din Account Manager för att få information om katalognamn, sökväg och autentiseringsuppgifter för S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>En tidsstämpel (baserad på UTC-tid) som anger när du skickar filerna till S3-bucket. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Ett ID som meddelar <span class="keyword"> Audience Manager</span> om en datafil innehåller dina egna användar-ID, Android-ID:n, iOS-ID:n eller andra ID:n som tillhör <a href="/help/using/features/global-data-sources.md"> globala datakällor </a>. Följande alternativ godkänns:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Data-Source-ID (kallas även dataproviderns-ID):</b> Detta är ett unikt ID som Audience Manager tilldelar en datakälla (se Audience Manager <a href="/help/using/reference/ids-in-aam.md">-indexet för ID:n </a>). Använd det här tilldelade ID:t i ett filnamn när du skickar in data som innehåller dina egna användar-ID:n. <code>...ftp_dpm_21_123456789.sync</code> instruerar till exempel <span class="keyword"> Audience Manager</span> att inhämta data till ID:n som tillhör datakällan 21. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID):</b> Använd ID 2014 i ett datafilnamn om det innehåller Android ID. Du måste använda fältet <code><i>_DPID_TARGET_DATA_OWNER</i></code> när du använder Android ID:n. <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> meddelar till exempel <span class="keyword"> Audience Manager</span> att datafilen bara innehåller Android ID:n och att ID:n ska kvalificera sig för de egenskaper som tillhör datakällan <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID:n (IDFA):</b> Använd ID 20915 i ett datafilnamn om det innehåller iOS ID:n. Du måste använda fältet <code><i>_DPID_TARGET_DATA_OWNER</i></code> när du använder iOS ID:n. <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> meddelar till exempel <span class="keyword"> Audience Manager</span> att datafilen bara innehåller iOS ID:n och att ID:n ska kvalificera sig för de egenskaper som tillhör datakällan <code><i>_DPID_TARGET_DATA_OWNER</i></code>.</li>
     <li> <b>ID:n som tillhör andra globala datakällor</b>: Du kan lägga till Roku ID:n för Advertising (RIDA), Microsoft Advertising ID:n (MAID) och andra ID:n. Använd det ID som motsvarar varje datakälla, så som beskrivs i artikeln <a href="/help/using/features/global-data-sources.md"> för globala datakällor i </a>.</li> 
    </ul> <p> <p>Obs! Blanda inte ID-typer i dina datafiler. Om ditt filnamn till exempel innehåller Android-identifieraren ska du inte ange iOS-ID:n eller dina egna ID:n i datafilen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Det här fältet anger för Audience Manager vilken datakälla data ska sparas i. Det här fältet är obligatoriskt om du ställer in DPID på ett Android-id, ett iOS-id eller ett annat ID som tillhör globala datakällor. På så sätt kan Audience Manager länka fildata tillbaka till din organisation. <br> Den här måldatakällan måste ägas av ditt företag. För datadelning med andra företag måste du ha en åtkomstmappning mellan ditt företag och måldatakällan för att kunna importera data till en måldatakälla som tillhör ett annat företag. Kontakta din Adobe-konsult eller kundsupport om du vill konfigurera mappningen.</p> <p><b>Viktigt!</b> Du <i>behöver inte</i> begära en mappning för befintliga datautdelningsrelationer (för måldatakällor som tillhör andra företag som du överförde data till före den 14 mars 2022). Mappningen behövs inte heller när du registrerar data i måldatakällor som tillhör ditt PID. </p> <p>Exempel: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> meddelar Audience Manager att du kvalificerar kund-ID:n som tillhör datakällan 33 för egenskaper eller signaler som tillhör datakällan 21. </li> 
     <li> <b>Android ID (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> säger till <span class="keyword"> Audience Manager</span> att datafilen endast innehåller Android ID:n och att ID:n ska vara kvalificerade för de egenskaper som tillhör datakällan 21.</li> 
     <li> <b>iOS ID:n (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> säger till <span class="keyword"> Audience Manager</span> att datafilen endast innehåller iOS ID:n och att ID:n ska vara kvalificerade för de egenskaper som tillhör datakällan 21.</li>
     <li> <b>ID:n som tillhör andra globala datakällor</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> anger för <span class="keyword"> Audience Manager</span> att datafilen endast innehåller Roku ID:n och att ID:n ska vara kvalificerade för de egenskaper som tillhör datakällan 21. Använd det ID som motsvarar varje datakälla, så som beskrivs i artikeln <a href="/help/using/features/global-data-sources.md"> för globala datakällor i </a>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Det företags- eller organisationsnamn du använder i <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>En 10-siffrig UTC UNIX-tidsstämpel i sekunder. Tidsstämpeln gör varje filnamn unikt. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synkroniseringsalternativ som inkluderar: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normalt scenario när tredjepartsdataleverantörer skickar egenskaper per användare för att läggas till eller tas bort i Audience Manager-systemet. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Gör att dataleverantörer kan skicka en lista över egenskaper per användare som ska skriva över den här användarens befintliga egenskaper från tredje part för den här dataleverantören i Audience Manager. Du behöver inte inkludera alla användare i en överskrivningsfil. Inkludera endast de användare som du vill ändra. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Ett heltal. Används när du delar upp stora filer i flera delar för att förbättra bearbetningstiden. Talet anger vilken del av originalfilen du skickar in. </p> <p>För effektiv filbearbetning kan du dela datafilerna på det sätt som anges: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Okomprimerad: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimerad: 200-300 MB </li> 
    </ul> <p>Se de första 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> exemplen på filnamn </a> nedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>När du skickar filer till Amazon S3 bör du bara använda gzip-komprimering. När filerna är komprimerade får de tillägget <code> .gz</code>. Använd inte ZIP-komprimering. </p> <p>Komprimerade filer måste vara 3 GB eller mindre. Om filerna är större kan du kontakta kundtjänst. Även om Audience Manager kan hantera stora filer kan vi hjälpa dig att minska filstorleken och effektivisera dataöverföringen. Se <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Filkomprimering för inkommande dataöverföringsfiler </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel på filnamn {#file-name-examples}

I följande exempel visas korrekt formaterade filnamn. Filnamnen kan se likadana ut.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

Du kan [hämta](assets/ftp_dpm_1234_1445374061.overwrite) exempelfilen om du vill ha fler exempel. Filen har sparats med filtillägget `.overwrite`. Öppna med en enkel textredigerare.

## Godkända filstorlekar {#accepted-file-sizes}

Titta på bilderna nedan om du vill ha snabb/tidigaste bearbetning av dina filer och om du vill ha filstorleksbegränsningar när du skickar data till en [!DNL Audience Manager] / [!DNL Amazon S3] -katalog.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filtyp </th> 
   <th colname="col2" class="entry"> Optimal storlek </th> 
   <th colname="col3" class="entry"> Maximal storlek </th> 
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


>[!NOTE]
>
>Den inkommande dataverifieringsprocessen kommer att markera tomma filer som ogiltiga och kommer inte att bearbeta dem.

## Längdbegränsningar {#line-limits}

Inkommande datafiler har en linjelängd på högst 102400 byte. Linjer som överskrider denna gräns tas inte med i överföringen.

>[!MORELIKETHIS]
>
>* [FTP-namnkrav för inkommande datafiler](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
