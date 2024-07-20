---
description: Beskriver obligatoriska fält, syntax och namnkonventioner som används för filbaserad ID-synkronisering. Namnge och ordna filinnehållet enligt dessa specifikationer.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: Namn- och innehållskrav för ID-synkroniseringsfiler
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 3%

---

# Namn- och innehållskrav för ID-synkroniseringsfiler {#name-and-content-requirements-for-id-synchronization-files}

Beskriver obligatoriska fält, syntax och namnkonventioner som används för filbaserad ID-synkronisering. Namnge och ordna filinnehållet enligt dessa specifikationer.

>[!NOTE]
>
>Textformaten (`monospaced text`, *kursiv*, parenteser `[ ]` `( )` etc.) i det här dokumentet anger kodelement och alternativ. Mer information finns i [Formatkonventioner för kod- och textelement](../../../reference/code-style-elements.md).

## Filnamnssyntax och exempel {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID-filnamn innehåller följande obligatoriska och valfria element:

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>Ett statiskt prefix som identifierar filen som en ID-synkroniseringsfil. Använd det här prefixet när du matchar enhets-ID:n till andra enhets-ID:n eller kund-ID:n (DPUID).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Ett statiskt prefix som identifierar filen som en ID-synkroniseringsfil för personbaserade mål. Använd det här prefixet när du matchar kund-ID:n (DPUID) till hash-kodade e-postadresser för personbaserade mål.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>Huvuddataleverantörens ID är det överordnade ID:t för DPID:n i filnamnet. Det första användar-ID:t i datafilen motsvarar också huvud-ID:t. De efterföljande DPID:n är andra identifierare som tillhör mallen. Synkroniseringen mappar DPID:n i filnamnet till UUID:n i filen.</p> <p>Detta DPID får bara innehålla enhets-ID, t.ex. AAM UUID, GAID, IDFA osv. Den får inte innehålla DPUID. Om du gör det kan synkroniseringen bli felaktig.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>DataProvider-ID. Dessa ID:n representerar enheter eller datakällor som är kopplade till huvud-DID:t. Synkroniseringen mappar DPID:n i filnamnet till UUID:n i filen. </p> <p>Antalet DPID i filnamnet måste matcha antalet UUID i datafilen. Exempel: ditt filnamn innehåller ett huvud-DPID och tre DPID. Datafilen måste innehålla fyra motsvarande UUID-kolumner, formaterade enligt beskrivningen i filinnehållsavsnittet nedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>En 10-siffrig UNIX-tidsstämpel i sekunder. Tidsstämpeln gör varje filnamn unikt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Anger en normal, fullständig synkronisering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Ett heltal. Används när du delar upp stora filer i flera mindre filer. Detta hjälper till att förbättra bearbetningstiden. Talet anger vilken del av originalfilen du skickar in. Se exemplen på filnamn nedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Anger att filen komprimeras med gzip-komprimering (tillval). </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exempel på filnamn

I följande exempel visas korrekt formaterade filnamn. Filnamnen kan se likadana ut.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Information om namngivning av filer för ID-synkronisering (c2c-prefix) för personbaserade mål finns i [Arbetsflöde A - Personalization baserad på all onlineaktivitet i kombination med offlinedata](../../../features/destinations/people-based-destinations-workflow-combined.md) eller [Arbetsflöde B - Personalization baserad på data som bara är offline](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Syntax för filinnehåll och exempel {#file-content-syntax}

Innehållet i en ID-fil innehåller följande element:

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

Filen innehåller användar-ID ([!DNL UUID]). Separera ID:n på varje rad med en flik. I följande exempel visas en korrekt formaterad ID-fil. Innehållet kan se likadant ut.

```
abc123 def456 ghi789 xyz987
```

### Fillinnehåll {#considerations}

När du skapar dina inkommande filer måste du se till att den första kolumnen bara är ifylld med enhets-ID:n, som [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA] och så vidare. Se [Index för ID:n i Audience Manager](../../../reference/ids-in-aam.md) för en detaljerad förklaring av ID:n som stöds av Audience Manager.

>[!IMPORTANT]
>
>Använd inte [DPUID](../../../reference/ids-in-aam.md) i den första kolumnen. Om du gör det kan synkroniseringen bli felaktig.

## Synkroniseringen matchar DPUID:n med UUID:n {#sync-matches-dpuuids-uuids}

Syftet med en ID-synkroniseringsfil är att synkronisera [DPUID](../../../reference/ids-in-aam.md) från dina egna datakällor med [!DNL Audience Manager] UID:n. Synkroniseringen mappar [!DNL DPUUID] från mallen [!DNL DPID] och dess relaterade [!DNL DPID] till [!DNL Audience Manager] [!DNL UUID]. Var du placerar ID:n i filnamnet och brödtexten avgör hur dessa ID:n mappas till varandra. Ta till exempel de två exempelfilerna som visas här:

* **Fil 1:** `adobe_id_0_12345_1476312152.sync`

* **Fil 2:** `adobe_id_12345_67890_1476312876.sync`

<br/>

Utifrån exempelnamnet och innehållet mappas ID:n ihop så här:

**Fil 1** ( [Hämta exempelfil](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = Adobe Audience Manager UUID | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR.38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Steg 1: ID-synkroniseringsprocessen synkroniserar [!DNL DPUUID] från [!DNL DPID] 12345 med [!DNL Audience Manager] [!DNL UUID] i den vänstra kolumnen. Observera att [!DNL DPID] &quot;0&quot; i filnamnet representerar [!DNL Audience Manager] [!DNL UUID].
<br/>

**Fil 2** ( [Hämta exempelfil](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR.38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Steg 2: [!DNL DPUUID] från [!DNL DPID] 12345 har synkroniserats i steg 1 med Audience Manager [!DNL UUID]. Det som den här ID-synkroniseringen gör är att synkronisera [!DNL DPUUID] från [!DNL DPID] 67890 med Audience Manager [!DNL UUID] från steg 1.

<br/>

## Andra formatkrav {#other-format-reqs}

Användar-ID:n kan inte:

* Ha flikar i själva ID:t. Flikar används bara för att avgränsa enskilda ID:n i datafilen.
* Innehåller personligt identifierbar information ([!UICONTROL PII]).
* Använd kodningen [!DNL URL]. Skicka bara in okodade ID:n.

Rader som slutar med tabbar eller mellanslag bearbetas eller realiseras inte. Se i regel till att du inte tar bort radslut.
