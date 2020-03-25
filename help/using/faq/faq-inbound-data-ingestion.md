---
description: Frågor och svar om hur man lägger in offlinedata i Audience Manager.
keywords: ftp or s3;s3 or ftp
seo-description: Frågor och svar om hur man lägger in offlinedata i Audience Manager.
seo-title: Vanliga frågor och svar om inkommande kunddata
solution: Audience Manager
title: Vanliga frågor och svar om inkommande kunddata
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 187874fb5d0c4363f771297766f3c4bc9d967c9b

---


# Vanliga frågor och svar om inkommande kunddata{#inbound-customer-data-ingestion-faq}

Frågor och svar om hur man lägger in offlinedata i Audience Manager.

 

**Kan du sammanfatta introduktionsprocessen?**

Startprocessen består av två steg som beskrivs i [Skicka batchdata till Audience Manager-översikt](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* Steg 1: synkronisera användar-ID;
* Steg 2: skapa och överföra den inkommande datafilen enligt kraven för filformat.

 

**Kan du sammanfatta distributionsprocessen?**

Vi rekommenderar följande:

* Samarbeta med din dataleverantör för att formatera den dagliga inkommande datafilen enligt Adobes specifikationer. Följande dokumentation innehåller information om namngivning och syntaxkrav:
   * [Namn- och innehållskrav för ID-synkroniseringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Innehåll i inkommande datafil: Syntax, ogiltiga tecken, variabler och exempel](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Krav för Amazon S3-namn och filstorlek för inkommande datafiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Samarbeta med din [!DNL Adobe] konsult för att överföra en testdatafil till [!DNL Adobe] för formatverifiering.
* Samarbeta med din [!DNL Adobe] konsult och ta fram en taxonomi som passar för att tolka innehållet i datafilen.
* I staging-/utvecklingsmiljön bekräftar du att ID-synkroniseringen är konfigurerad för att hämta dataleverantörens besökar-ID och överföra det till [!DNL Audience Manager] servrarna i realtid.
* Distribuera DIL/ID-synkronisering till produktion. Synkroniseringen av ID:n kommer redan att konfigureras som en modul i DIL-koden av din Adobe-konsult.
* Överför produktionsdatafiler till [!DNL Audience Manager]. Med tanke på beroendena av ID-synkroniseringsmappningar kan det vara bra att börja överföra data upp till en vecka efter distributionen av produktionskoden, men du kan börja överföra datafilerna så fort koden går till produktion.

 

**Vilket FTP-läge ska jag använda för att överföra komprimerade eller krypterade filer?**

Se [Filkomprimering för inkommande dataöverföringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>Vi fasar ut stödet för FTP-konfigurationer. Inläsning av inkommande datafiler stöds fortfarande i befintliga FTP-integreringar, men vi rekommenderar starkt att du använder Amazon S3 för att lägga in offlinedata för nya integreringar. Mer information finns i [Krav för namn och filstorlek för Amazon S3 för inkommande datafiler](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) .

 

**Kan jag överföra en inkommande datafil (filen[!DNL .sync]eller[!DNL .overwrite]) innan jag driftsätter[!DNL Audience Manager]-koden i produktionen?**

Ja. Så länge du använder en datakälla för olika enheter för att lagra de CRM-data som du överför lagrar Audience Manager alltid dessa data. I enlighet med förbättringarna av reglerna för profilsammanslagning som Audience Manager lanserade i oktober 2019, som gör att endast data kan användas offline, kan du överföra och utföra åtgärder på data utan att distribuera Audience Manager-kod till produktion alls. Se:

* [Översikt över regelförbättringar för profilsammanslagning](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* Personbaserade mål - [personalisering baserad på data som bara är offline](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**Vilken tid på dagen ska jag överföra min fil?**

[!DNL Audience Manager] söker efter och bearbetar filer flera gånger under dagen. Överför dina data när du är redo.

 

**Hur lång tid tar det innan data från en överförd fil är tillgängliga för målinriktning?**

Data är tillgängliga för målinriktning efter 48 timmar. Tolka inte heller e-postmeddelandet om att överföringen har slutförts som ett uttalande om att data är tillgängliga. Detta innebär bara att [!DNL Audience Manager] har hämtat filen och slutfört det första steget i bearbetningen.

 

**Hur ofta ska jag skicka filer och ska de vara fullständiga eller inkrementella?**

Det bästa är att skicka en inkrementell fil en gång om dagen för nya besökare och för besökare vars data har ändrats. Många [!DNL Audience Manager] kunder skickar en fullständig fil en gång i månaden. Dessa filintervall och steg är dock flexibla. Du bör skicka data i steg och vid tidpunkter som passar dig.

 

**Hur länge behåller Audience Manager mina filer på servern?**

FTP-filer tas bort efter att de har bearbetats. [!DNL S3] filer tas bort efter 30 dagar. Filer som inte kan bearbetas på grund av format, syntax eller andra fel tas bort. Se även Frågor och svar om [sekretess och datalagring](../faq/faq-privacy.md).

 

**Vad är skillnaden mellan fullständiga och inkrementella filer?**

* **Fullständig:** En fullständig fil skriver över alla dina befintliga besökarprofiler och ersätter dem med data i filen. Fullständiga filer identifieras av taggen som läggs till efter filnamnet `.overwrite` . Du kan använda en `.overwrite` fil för att återställa besökarens egenskaper eller ta bort inaktuella, föråldrade egenskaper.

   >[!NOTE]
   >
   >Filerna [!DNL .overwrite] skriver bara över [!DNL Audience Manager] profildata som är kopplade till den här DataProvider. Med andra ord förblir alla [!DNL Adobe Analytics] data som är kopplade till besökaren intakta efter att en [!DNL .overwrite] fil har bearbetats.

* **Inkrementell:** En inkrementell fil lägger till nya data i dina befintliga besökarprofiler. Inkrementella filer identifieras av taggen som läggs till efter filnamnet `.sync` . Att skicka en inkrementell fil raderar eller skriver inte över befintliga profiler.

I följande exempel visas hur dessa filtyper påverkar lagrade besökarprofiler.

| Användningsfall | Beskrivning |
|---|---|
| Inkrementell och fullständig | <ul><li>Dag 1 - `.sync` filinnehåll: `visitor123 = a,b,c`</li><li>Dag 2- `.overwrite` filens innehåll: `visitor123 = c,d,e`</li><li>Innehåll i profil-ID 123 för besökare dag 3: `c,d,e`</li></ul> |
| Endast inkrementell | <ul><li>Dag 1 - `.sync` filinnehåll: `visitor123 = a,b,c`</li><li>Dag 2- `.sync` filens innehåll: `visitor123 = c,d,e`</li><li>Innehåll i profil-ID 123 för besökare dag 3: `a,b,c,d,e`</li></ul> |

Mer information om fullständiga och inkrementella filtyper finns i:

* [Krav för Amazon S3-namn och filstorlek för inkommande data..](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Vad händer om jag skickar in en fil med ID:n för besökare som aldrig har utfört synkroniseringen av ID:n på sidan?**

Under bearbetningen [!DNL Audience Manager] hoppar över den posten och går vidare till nästa. Om ett [DPID (Data Provider ID)](../reference/ids-in-aam.md) ställs in som ett DPID för flera enheter, sparas data som hämtas innan en ID-synkronisering sparas och är tillgängliga för användning kort efter att ID-synkroniseringen görs.

 

**Vad är tidsstämpeln, vad är den till och kan du ge ett exempel?**

Tidsstämplar används för loggning och registrering. De krävs av den syntax som används för ett korrekt formaterat inkommande filnamn. Se:

* [Amazon S3-namnkrav för inkommande datafiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Vad är ett Data Provider ID (DPID) och hur får jag det?**

Din Adobe-konsult kommer att tilldela din datakälla ett tresiffrigt eller fyrsiffrigt [DPID (Data Provider ID)](../reference/ids-in-aam.md) . Detta ID är unikt och ändras inte.

 

**Hur stora kan de dagliga datafilerna vara?**

Se [Filkomprimering för inkommande dataöverföringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**Har Audience Manager stöd för filkomprimering?**

Ja, se:

* [Filkomprimering för inkommande dataöverföringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Amazon S3-namnkrav för inkommande datafiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Den primära nyckeln i min datakälldatabas är en e-postadress. Betraktar det personligt identifierbar information?**

Ja. [!DNL Audience Manager] sparar inte e-postadresser i databasen. Besökarna bör tilldelas ett slumpmässigt genererat ID eller en ensidig version av e-postadressen innan ID-synkroniseringen initieras.

 

**Är innehållet i datafilen skiftlägeskänsligt? Vad sägs om ID-synkroniseringen?**

Det finns två grundläggande komponenter i en datafil: A [!UICONTROL User ID] (se [!UICONTROL User ID] i [Definierade](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)filvariabler) och profildata, vanligtvis i form av nyckelvärdepar eller koder. Det [!UICONTROL User ID] är skiftlägeskänsligt. I allmänhet är profil- eller nyckelvärdesdata inte skiftlägeskänsliga.

 

**Ska jag använda FTP eller[!DNL Amazon S3]för att överföra filer?**

Vi rekommenderar [!DNL Amazon S3] eftersom processen är enklare. [!DNL Audience Manager] FTP-filer överförs till [!DNL S3] alla andra, så processen blir smidigare om du släpper filerna på [!DNL Amazon S3] dig själv. Dessutom delar kunder som överför samtidigt till FTP FTP FTP bandbredden, så de förväntar sig lägre överföringshastigheter. [!DNL Amazon S3] replikeras och distribueras också, så den är vanligtvis säkrare och mer tillförlitlig än en FTP-server. Mer information finns i [Om Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Vi fasar ut stödet för FTP-konfigurationer. Inläsning av inkommande datafiler stöds fortfarande i befintliga FTP-integreringar, men vi rekommenderar starkt att du använder Amazon S3 för att lägga in offlinedata för nya integreringar. Mer information finns i [Krav för namn och filstorlek för Amazon S3 för inkommande datafiler](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) .

 

**Hur bearbetar Audience Manager inkommande filer?**

[!DNL Audience Manager] används [!DNL Amazon Simple Queue Service (SQS)] för inkommande databearbetning. Så här fungerar det:

1. [!DNL Audience Manager] kunderna överför sina inkommande data till en [!DNL Amazon S3] bucket.
1. Data kommer in i [!DNL Amazon SQS] kön och väntar på att bearbetas av [!DNL Audience Manager].
1. [!DNL Audience Manager] läser upp till 119000 poster från [!DNL Amazon SQS] kön och delar upp dem i upp till 3 grupper. Filer i varje grupp bearbetas samtidigt.

 

**Jag måste överföra flera filer samtidigt. Bearbetas filerna samtidigt?**

Det beror på. [!DNL Audience Manager] läser upp till 119000 poster från [!DNL Amazon SQS] kön och delar upp dem i upp till 3 grupper. Dina filer bearbetas endast samtidigt om de hamnar i samma grupp. På grund av den stora mängd data som dagligen hämtas in av [!DNL Audience Manager] kan vi inte garantera någon filbearbetningsordning.

>[!MORELIKETHIS]
>
>* [Beskriver batchdataöverföringsprocessen](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

