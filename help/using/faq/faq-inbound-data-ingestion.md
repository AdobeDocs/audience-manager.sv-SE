---
description: Vanliga frågor om att lägga in offlinedata i Audience Manager.
keywords: ftp eller s3;s3 eller ftp
seo-description: Frequently asked questions about bringing offline data into Audience Manager.
seo-title: Inbound Customer Data Ingestion FAQ
solution: Audience Manager
title: Vanliga frågor om inmatning av inkommande kunddata
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
exl-id: 48eef5f1-0655-4dac-9ab4-74b11c705c13
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1343'
ht-degree: 86%

---

# Vanliga frågor om inmatning av inkommande kunddata{#inbound-customer-data-ingestion-faq}

Vanliga frågor om att lägga in offlinedata i Audience Manager.

 

**Kan ni sammanfatta registreringsprocessen?**

Registreringsprocessen består av två steg som beskrivs i [Översikt över att skicka satsvisa data till Audience Manager](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* Steg 1: synkronisera användar-ID:n
* Steg 2: skapa och överföra den inkommande datafilen enligt kraven för filformat.

 

**Kan ni sammanfatta distributionsprocessen?**

Vi rekommenderar följande:

* Samarbeta med er dataleverantör för att formatera den dagliga inkommande datafilen enligt Adobes specifikationer. Kraven på filnamn och syntax finns i följande dokumentation:
   * [Namn- och innehållskrav för ID-synkroniseringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Innehåll i inkommande datafil: syntax, ogiltiga tecken, variabler och exempel](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Amazon S3-namn och filstorlek för inkommande datafiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Samarbeta med er [!DNL Adobe]-konsult för att överföra en testdatafil till [!DNL Adobe] för formatverifiering.
* Samarbeta med er [!DNL Adobe]-konsult för att ta fram en taxonomi som passar för att tolka innehållet i datafilen.
* I mellanlagrings-/utvecklingsmiljön bekräftar du att ID-synkroniseringen är konfigurerad för att hämta dataleverantörens besökar-ID och överföra det till [!DNL Audience Manager]-servrarna i realtid.
* Distribuera DIL/ID-synkronisering till produktion. ID-synkroniseringen har redan konfigurerats som en modul i DIL-koden av er Adobe-konsult.
* Överför produktionsdatafiler till [!DNL Audience Manager]. Med tanke på beroendena för ID-synkroniseringsmappningar kan det vara bra att börja överföra data upp till en vecka efter distributionen av produktionskoden, men ni kan börja överföra datafilerna så fort koden går till produktion.

 

**Vilket FTP-läge ska jag använda för att överföra komprimerade eller krypterade filer?**

Se [Filkomprimering för inkommande dataöverföringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>Vi fasar ut stödet för FTP-konfigurationer. Inläsning av inkommande datafiler stöds fortfarande i befintliga FTP-integreringar, men vi rekommenderar starkt att ni använder Amazon S3 för att lägga in offlinedata för nya integreringar. Mer information finns i [Krav på Amazon S3-namn och filstorlekar för inkommande datafiler](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

 

**Kan jag överföra en inkommande datafil (filen [!DNL .sync] eller [!DNL .overwrite]) innan jag driftsätter [!DNL Audience Manager] -koden i produktionen?**

Ja. Så länge du använder en [!UICONTROL cross-device data source] för att lagra de CRM-data som du överför lagrar Audience Manager alltid dessa data. Efter de [!UICONTROL Profile Merge Rules] förbättringar som Audience Manager lanserade i oktober 2019 och som gör att endast offlineanvändning kan användas, kan du överföra och vidta åtgärder för data utan att distribuera Audience Manager-kod till produktionen alls. Se:

* [Översikt över förbättrade regler för profilsammanslagning](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [Personalization baserad på data som bara är offline](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

[!DNL Audience Manager] söker efter och bearbetar filer flera gånger under dagen. Överför data när du är redo.

 

**Hur lång tid tar det innan data från en överförd fil är tillgängliga för målinriktning?**

Data är tillgängliga för målinriktning efter 48 timmar. Tolka inte e-postmeddelandet om att överföringen har slutförts som om data är tillgängliga. Det betyder bara att [!DNL Audience Manager] har hämtat filen och slutfört det första steget i bearbetningen.

 

**Hur ofta ska jag skicka filer och ska de vara fullständiga eller inkrementella?**

Det bästa är att skicka en inkrementell fil en gång om dagen för nya besökare och besökare vars data har ändrats. Många [!DNL Audience Manager]-kunder skickar en fullständig fil en gång i månaden. Men dessa intervall och steg är dock flexibla. Ni bör skicka data gradvis och vid tidpunkter som passar er.

 

**Hur länge lagrar Audience Manager mina filer på servern?**

FTP-filer tas bort efter att de har bearbetats. [!DNL S3]-filer tas bort efter 30 dagar. Filer som inte kan bearbetas på grund av format, syntax eller andra fel tas bort. Se även [Vanliga frågor om sekretess och datalagring](../faq/faq-privacy.md).

 

**Vad är skillnaden mellan fullständiga och inkrementella filer?**

* **Fullständig:** En fullständig fil skriver över alla era befintliga besökarprofiler och ersätter dem med data i filen. Fullständiga filer identifieras av taggen `.overwrite` som läggs till efter filnamnet. Du kan använda en `.overwrite`-fil för att återställa besökarnas traits eller ta bort inaktuella, föråldrade traits.

  >[!NOTE]
  >
  >[!DNL .overwrite]-filerna skriver bara över [!DNL Audience Manager]-profildata som är associerade med dataleverantören. Med andra ord förblir alla [!DNL Audience Manager]-data som är kopplade till besökaren intakta efter att en [!DNL .overwrite]-fil har bearbetats.

* **Inkrementell:** En inkrementell fil lägger till nya data i befintliga besökarprofiler. Inkrementella filer identifieras av taggen `.sync` som läggs till efter filnamnet. Befintliga profiler raderas eller skrivs inte över när ni skickar en inkrementell fil.

Följande exempel visar hur dessa filtyper påverkar lagrade besökarprofiler.

| Användningsexempel | Beskrivning |
|---|---|
| Inkrementell och fullständig | <ul><li>Dag 1 `.sync` filinnehåll: `visitor123 = a,b,c`</li><li>Dag 2 `.overwrite` filinnehåll: `visitor123 = c,d,e`</li><li>Dag 3 besökarprofil ID 123 innehåll: `c,d,e`</li></ul> |
| Endast inkrementell | <ul><li>Dag 1 `.sync` filinnehåll: `visitor123 = a,b,c`</li><li>Dag 2 `.sync` filinnehåll: `visitor123 = c,d,e`</li><li>Dag 3 besökarprofil ID 123 innehåll: `a,b,c,d,e`</li></ul> |

Mer information om fullständiga och inkrementella filtyper finns i:

* [Amazon S3-namn och filstorlek för inkommande data..](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Vad händer om jag skickar en fil med ID:n för besökare som aldrig har varit med om en ID-synkronisering på sidan?**

Under bearbetningen hoppar [!DNL Audience Manager] över den posten och går vidare till nästa. Om ett [DPID (dataleverantörs-ID)](../reference/ids-in-aam.md) konfigurerats som ett enhetsövergripande DPID, sparas data som hämtas innan en ID-synkronisering sparas och de kan användas en kort tid efter ID-synkroniseringen.

 

**Vad är en tidsstämpel, vad är den till för och kan ni ge ett exempel?**

Tidsstämplar används för loggning och registrering. De krävs av den syntax som används för ett korrekt formaterat inkommande filnamn. Se:

* [Amazon S3-namnkrav för inkommande datafiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Vad är en [!DNL Data Provider ID (DPID)] och hur skaffar jag den?**

Er Adobe-konsult kommer att tilldela er datakälla ett tresiffrigt eller fyrsiffrigt [DPID (dataleverantörs-ID)](../reference/ids-in-aam.md). Detta ID är unikt och ändras inte.

 

**Hur stora kan de dagliga datafilerna vara?**

Se [Filkomprimering för inkommande dataöverföringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**Har Audience Manager stöd för filkomprimering?**

Ja, se:

* [Filkomprimering för inkommande dataöverföringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Amazon S3-namnkrav för inkommande datafiler](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Den primära nyckeln i databasen för vår datakälla är e-postadresser. Betraktas de som personligt identifierbar information?**

Ja. [!DNL Audience Manager] sparar inte e-postadresser i databasen. Besökarna bör tilldelas ett slumpmässigt genererat ID eller en ensidig version av e-postadressen innan ID-synkroniseringar initieras.

 

**Är innehållet i datafilen skiftlägeskänsligt? Vad gäller för ID-synkroniseringen?**

Det finns två grundläggande komponenter i en datafil: En [!UICONTROL User ID] (se [!UICONTROL User ID] i [Definierade filvariabler](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) och profildata, vanligtvis i form av nyckelvärdespar eller koder. [!UICONTROL User ID] är skiftlägeskänsligt. I allmänhet är profil- eller nyckelvärdesdata inte skiftlägeskänsliga.

 

**Ska jag använda FTP eller [!DNL Amazon S3] för att överföra filer?**

Vi rekommenderar [!DNL Amazon S3] eftersom processen är enklare. [!DNL Audience Manager] överför FTP-filer till [!DNL S3] i vilket fall som helst, så processen blir smidigare om du själv släpper filerna på [!DNL Amazon S3]. Dessutom delar kunder som överför samtidigt till FTP på bandbredden, så de bör förvänta sig lägre överföringshastigheter. [!DNL Amazon S3] replikeras och distribueras också, så det är vanligtvis säkrare och mer tillförlitligt än en FTP-server. Mer information finns i [Om Amazon S3](../reference/amazon-s3.md).

>[!WARNING]
>
>Vi fasar ut stödet för FTP-konfigurationer. Inläsning av inkommande datafiler stöds fortfarande i befintliga FTP-integreringar, men vi rekommenderar starkt att du använder [!DNL Amazon S3] för att lägga in offlinedata för nya integreringar. Mer information finns i [Krav på Amazon S3-namn och filstorlekar för inkommande datafiler](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

 

**Hur bearbetar Audience Manager inkommande filer?**

[!DNL Audience Manager] använder [!DNL Amazon Simple Queue Service (SQS)] för inkommande databearbetning. Så här fungerar det:

1. [!DNL Audience Manager]-kunder överför inkommande data till en [!DNL Amazon S3]-bucket.
1. Data placeras i [!DNL Amazon SQS]-kön och väntar på att bearbetas av [!DNL Audience Manager].
1. [!DNL Audience Manager] läser max 119 000 poster från [!DNL Amazon SQS]-kön och delar upp dem i högst 3 satser. Filerna i varje sats bearbetas samtidigt.

 

**Jag måste överföra flera filer samtidigt. Bearbetas filerna samtidigt?**

Det beror på. [!DNL Audience Manager] läser max 119 000 poster från [!DNL Amazon SQS]-kön och delar upp dem i högst 3 satser. Era filer bearbetas bara samtidigt om de hamnar i samma sats. På grund av den stora mängd data som dagligen matas in i [!DNL Audience Manager] kan vi inte garantera en viss filbearbetningsordning.

>[!MORELIKETHIS]
>
>* [Beskrivning av satsvis överföring av data](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)
