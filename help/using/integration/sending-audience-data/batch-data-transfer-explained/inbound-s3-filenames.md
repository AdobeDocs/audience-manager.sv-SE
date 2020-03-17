---
description: Beskriver obligatoriska fält, syntax, namnkonventioner och filstorlekar som du måste följa när du skickar data till Audience Manager. Ange namn och storlek för filerna enligt dessa specifikationer när du skickar data till en Audience Manager-/Amazon S3-katalog.
seo-description: Beskriver obligatoriska fält, syntax, namnkonventioner och filstorlekar som du måste följa när du skickar data till Audience Manager. Ange namn och storlek för filerna enligt dessa specifikationer när du skickar data till en Audience Manager-/Amazon S3-katalog.
seo-title: Krav för Amazon S3-namn och filstorlek för inkommande datafiler
solution: Audience Manager
title: Krav för Amazon S3-namn och filstorlek för inkommande datafiler
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Krav för Amazon S3-namn och filstorlek för inkommande datafiler{#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Beskriver obligatoriska fält, syntax, namnkonventioner och filstorlekar som du måste följa när du skickar data till Audience Manager. Ange namn och storlek för filerna enligt dessa specifikationer när du skickar data till en Audience Manager/ [!DNL Amazon S3] -katalog.

>[!NOTE]
>
>Textformaten (`monospaced text`, *kursiv*, parenteser `[ ]` `( )` etc.) i det här dokumentet anger kodelement och alternativ. Mer information finns i [Formatkonventioner för kod- och textelement](../../../reference/code-style-elements.md).

## Filnamnssyntax {#file-name-syntax}

[!DNL S3] filnamn innehåller följande obligatoriska och valfria element:

* **[!DNL S3]prefix:**`s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **Filnamnselement:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Information om andra godkända filnamnsformat finns i [Anpassade partnerintegreringar](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {prioritet=&quot;high&quot;}
>
>[!DNL Audience Manager] endast bearbetar [!DNL ASCII] och [!DNL UTF-8] kodade filer.

### Namnge element

Tabellen definierar elementen i ett [!DNL S3] filnamn.

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
   <td colname="col2"> <p>Dataleverantörs-ID <span class="term"> (DPID) är en identifierare som talar om för</span> Audience Manager <span class="keyword"></span> om en datafil innehåller egna användar-ID:n, Android- eller iOS-ID:n. Följande alternativ godkänns: </p> <p> <b>Data Partner-ID</b> </p> <p>Detta är ett unikt ID Audience Manager som tilldelas ditt företag eller din organisation. Använd det här tilldelade ID:t i ett filnamn när du skickar in data som innehåller dina egna användar-ID:n. Till exempel anger <code>...ftp_dpm_21_123456789.sync</code> <span class="keyword"> Audience Manager</span> att en partner med ID 21 har skickat filen och den innehåller användar-ID som tilldelats av den partnern. </p> <p> <b>Android-ID (GAID)</b> </p> <p> Använd ID 20914 som DPID i ett datafilnamn om filen innehåller Android-ID:n. När du använder ID 20914 som DPID måste du ändå identifiera ditt företag för <span class="keyword"> Audience Manager</span>. Det innebär att filnamnet måste använda parametern <code><i>_DPID_TARGET_DATA_OWNER</i></code> för ditt företags-ID. Exempel: du skickar filer med Android-id:n och ditt Data Provider-ID är 21. I det här fallet ser filnamnet ut så här <code>...ftp_dpm_20914_21_123456789.sync</code>. Detta anger för <span class="keyword"> Audience Manager</span> att filen innehåller Android-id:n och kommer från en partner som identifieras med ID 21. </p> <p> <b>iOS-ID (IDFA)</b> </p> <p> Använd ID 20915 som DPID i ett datafilnamn om filen innehåller iOS-ID:n. När du använder ID 20915 som DPID måste du ändå identifiera ditt företag för <span class="keyword"> Audience Manager</span>. Det innebär att filnamnet måste använda parametern <code><i>_DPID_TARGET_DATA_OWNER</i></code> för ditt företags-ID. Exempel: du skickar filer med Android-id:n och ditt Data Provider-ID är 21. I det här fallet ser filnamnet ut så här <code>...ftp_dpm_20915_21_123456789.sync</code>. Detta anger för <span class="keyword"> Audience Manager</span> att filen innehåller iOS-ID:n och kommer från en partner som identifieras med ID 21. </p> 
    <draft-comment> 
     <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
      <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Data Partner-ID:</b> Detta är ett unikt ID Audience Manager som tilldelas ditt företag eller din organisation. Använd det här tilldelade ID:t i ett filnamn när du skickar in data som innehåller dina egna användar-ID:n. Till exempel anger <code>...ftp_dpm_21_123456789.sync</code> <span class="keyword"> Audience Manager</span> att en partner med ID 21 har skickat filen och den innehåller användar-ID som tilldelats av den partnern. </li> 
      <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (GAID):</b> Använd ID 20914 i ett datafilnamn om det innehåller Android-ID. Till exempel anger <code>...ftp_dpm_20914_21_123456789.sync</code> <span class="keyword"> Audience Manager</span> att datafilen endast innehåller Android-ID:n. Obs! ID 21 </li> 
      <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS-ID (IDFA):</b> Använd ID 20915 i ett datafilnamn om det innehåller iOS-ID:n. Till exempel anger <code>...ftp_dpm_20915_123456789.sync</code> <span class="keyword"> Audience Manager</span> att datafilen endast innehåller iOS-ID:n. </li> 
     </ul> 
    </draft-comment> <p> <p>Obs!  Blanda inte ID-typer i datafilerna. Om ditt filnamn till exempel innehåller Android-identifieraren ska du inte ange iOS-ID eller dina egna ID:n i datafilen. </p> </p><p>Mer information finns i <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/global-data-sources.html">Globala datakällor</a> .</p> <p>Se även <code><i>_DPID_TARGET_DATA_OWNER</i></code> posten nedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>En platshållare för ett ID. Du kan till exempel ställa in det på ditt <span class="keyword"> Audience Manager</span> ID om du ställer in DPID på ett datakälla-ID eller ett Android- eller iOS-ID. Detta gör att <span class="keyword"> Audience Manager</span> kan länka fildata tillbaka till din organisation. </p> <p>Exempel: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> visar att en partner med ID 21 har skickat in data från en datakälla som använder ID 33. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> visar att en partner med ID 21 har skickat in data som innehåller Android-ID:n. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> visar att en partner med ID 21 har skickat in data som innehåller iOS-ID:n. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Det företags- eller organisationsnamn du använder i <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>En 10-siffrig UTC UNIX-tidsstämpel i sekunder. Tidsstämpeln gör varje filnamn unikt. </p> 
    <draft-comment> 
     <p> <p>Obs!  Audience Manager använder inte tidsstämpeln vid bearbetning av inkommande filer. Tidsstämpeln i filnamnet har tagits bort i Audience Manager men krävs ändå för bakåtkompatibilitet. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synkroniseringsalternativ som inkluderar: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normalt scenario när externa dataleverantörer skickar egenskaper per användare för att läggas till eller tas bort i Audience Manager-systemet. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Gör att dataleverantörer kan skicka en lista över egenskaper per användare som ska skriva över den här användarens befintliga egenskaper från tredje part för den här dataleverantören i Audience Manager. Du behöver inte inkludera alla användare i en överskrivningsfil. Inkludera endast de användare som du vill ändra. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Ett heltal. Används när du delar upp stora filer i flera delar för att förbättra bearbetningstiden. Talet anger vilken del av originalfilen du skickar in. </p> <p>För effektiv filbearbetning kan du dela datafilerna på det sätt som anges: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Okomprimerad: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Komprimerad: 200-300 MB </li> 
    </ul> <p>Se de två första <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> filnamnsexemplen</a> nedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>När du skickar filer till Amazon S3 ska du bara använda gzip-komprimering. När filerna är komprimerade får de <code> .gz</code> filnamnstillägget. Använd inte ZIP-komprimering. </p> <p>Komprimerade filer måste vara 3 GB eller mindre. Om filerna är större kan du kontakta kundtjänst. Även om Audience Manager kan hantera stora filer kan vi hjälpa er att minska filstorleken och effektivisera dataöverföringen. Se <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Filkomprimering för inkommande dataöverföringsfiler</a>. </p> </td> 
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

Du kan [hämta](assets/ftp_dpm_1234_1445374061.overwrite) exempelfilen om du vill ha fler exempel. Den här filen har sparats med `.overwrite` filtillägget. Öppna med en enkel textredigerare.

## Godkända filstorlekar {#accepted-file-sizes}

Titta på bilderna nedan om du snabbt/tidigast vill bearbeta dina filer och om du vill ha filstorleksbegränsningar när du skickar data till en [!DNL Audience Manager] / [!DNL Amazon S3] katalog.

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

>[!NOTE]
>
>Den inkommande dataverifieringsprocessen kommer att markera tomma filer som ogiltiga och kommer inte att bearbeta dem.

>[!MORELIKETHIS]
>
>* [Krav för FTP-namn för inkommande datafiler](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)

