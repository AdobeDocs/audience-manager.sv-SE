---
description: Det här dokumentet innehåller teknisk information som rör efterlevnad av datasekretesslagar i Audience Manager.
seo-description: Det här dokumentet innehåller teknisk information som rör efterlevnad av datasekretesslagar i Audience Manager.
seo-title: Förfrågningar om datasekretess
solution: Audience Manager
keywords: GDPR-gränssnitt, GDPR API, CCPA, sekretess
title: Förfrågningar om datasekretess
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Datastyrning och sekretess
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 58%

---

# Förfrågningar om datasekretess {#data-privacy-requests}

## Översikt {#overview}

I det här dokumentet finns en översikt över hur du hanterar enskilda dataintegritets- och avanmälningsbegäranden som du kan skicka till [!DNL Audience Manager] via användargränssnittet för [Privacy Service](https://privacyui.cloud.adobe.io/) och **[!DNL Privacy Service API]**.

Med dessa verktyg kan du skicka förfrågningar om sekretess för konsumentdata som gjorts under [!DNL GDPR] och [!DNL CCPA].

Innan du läser den här artikeln rekommenderar vi att du går igenom ordlistorna för [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) och [CCPA](aam-ccpa-glossary.md) för att få en bättre förståelse för den terminologi som används här.

Du kan skicka enskilda förfrågningar om åtkomst till och borttagning av konsumentdata från [!DNL Audience Manager] på två sätt:

* Genom gränssnittet för [Privacy Service](https://privacyui.cloud.adobe.io/). Se dokumentationen [här](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Genom **[!DNL Privacy Service API]**. Läs dokumentationen [här](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) och [!DNL API] referensen [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

När du skickar individuella förfrågningar om dataintegritet kan du skicka alla [!DNL Audience Manager]-identifierare (ID), enligt beskrivningen i **[Audience Manager Identifiers](data-privacy-ids.md)**-avsnittet, tillsammans med deras respektive namnområdes-ID:n (ID för datakälla).

[Privacy Service](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html) har stöd för två typer av förfrågningar: förfrågningar om dataåtkomst och dataradering.

## Förfrågningar om dataåtkomst {#access-data}

Du kan skicka enskilda dataåtkomstbegäranden via [Privacy Servicens användargränssnitt](https://privacyui.cloud.adobe.io) (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) eller genom att anropa Privacy Servicens API (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) och [!DNL API] referens [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Med användargränssnittet i [Privacy Service](https://privacyui.cloud.adobe.io/) kan du skapa nya jobbförfrågningar genom att använda [!UICONTROL Request Builder] eller överföra en [!DNL JSON]-fil.

Om du vill se hur en giltig [!DNL JSON]-fil ser ut kan du [ ladda ned en JSON-fil som exempel](../data-security-and-privacy/assets/access_request.json).

Vi vet att ni strävar efter att uppfylla förfrågningar om datasekretess inom den tidsperiod som fastställs i lagstiftningen.

## Förfrågningar om dataradering {#delete-data}

Du kan skicka begäranden om borttagning av data via [Privacy Servicens användargränssnitt](https://privacyui.cloud.adobe.io) (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) eller genom att anropa Privacy Servicens API (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) och [!DNL API] referens [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Med användargränssnittet i [Privacy Service](https://privacyui.cloud.adobe.io/) kan du skapa nya jobbförfrågningar genom att använda [!UICONTROL Request Builder] eller överföra en [!DNL JSON]-fil.

Om du vill se hur en giltig [!DNL JSON]-fil ser ut kan du [ ladda ned en JSON-fil som exempel](../data-security-and-privacy/assets/access_request.json).

Adobe vet att ni strävar efter att uppfylla förfrågningar om datasekretess inom 30 dagar. Av den anledningen har [!DNL Adobe] åtagit sig att behandla din begäran om att ta bort data så snart som möjligt.

Som svar på dina förfrågningar om borttagning av konsumentdata tar [!DNL Audience Manager] bort egenskaper och segment som är associerade med identifieraren [!DNL Audience Manager] som ingår i förfrågan. Dessutom kommer respektive [!DNL Audience Manager]-identifierare för den person som avanmälde sig från ytterligare datainsamling av [!DNL Audience Manager] och respektive ID-mappningar att tas bort.

När du skickar deklarerade ID:n, t.ex. [!DNL CRM] ID:n för olika enheter eller [!DNL cookie] ID:n, i datasekretessbegäranden, utför [!DNL Audience Manager] den nödvändiga borttagningen på alla länkade enheter (upp till 100 enheter per deklarerat ID).

[!DNL Audience Manager] försöker meddela aktiveringspartners om borttagningsbegäran genom att skicka osegmenterad information om registrerade som begär att vissa data ska tas bort. Vissa aktiveringspartners:

1. Det går inte att använda begäran om att dela upp (eller ta bort segment) från [!DNL Audience Manager] och/eller
2. Kan inte ta emot uppdateringar från [!DNL Audience Manager] med en frekvens på mindre än 30 dagar. I dessa fall kan [!DNL Audience Manager]-kunder inte skicka borttagningsbegäranden till aktiveringspartners på ett automatiserat sätt via [!DNL Audience Manager].

I sådana fall kan ni inte skicka automatiska borttagningsförfrågningar till aktiveringspartners via [!DNL Audience Manager].

Ladda ned vårt [Partner Excel-blad](assets/AAM-Partners-October2019.xlsx) för att se vilka [!DNL Audience Manager] aktiveringspartners som stöder unsegment.

## Begäran om avanmälan {#opt-out-requests}

[!DNL Audience Manager] stöder branschövergripande standarder när det gäller hantering av avanmälan. Läs vidare för att få fullständig information om vilka typer av undantag som stöds av [!DNL Audience Manager].

Begäran om åtkomst och borttagning av data hanteras via [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), men förfrågningar om avanmälan stöds för närvarande via [!DNL DCS API]. Läs vidare för att lära dig hur avanmälningen [!DNL API]-samtal ska se ut.

### Globala förfrågningar om avanmälan

Den globala avanmälningen representerar en avanmälan för [!DNL Audience Manager] och andra [!DNL Adobe Experience Cloud]-lösningar för alla varumärken. Tabellen nedan visar de metoder som används för global avanmälan:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avanmälan för </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>Sidan <a href="https://www.adobe.com/se/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices </a> innehåller enklicksfunktioner som gör att slutanvändarna kan styra och välja bort datainsamling med annonslösningarna i Adobe Experience Cloud (inklusive Audience Manager). Mer information finns i avsnittet för <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> företagskunder </a> på sidan Privacy Choices. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkta API-anrop till Audience Manager </p> </td> 
   <td colname="col2"> <p>Användarna kan avanmäla sig från datainsamling för alla Audience Manager-varumärken genom att anropa DCS API:t nedan och inkludera användar-ID för <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Då anges <code>demdex=NOTARGET</code>- och <code>dextp=NOTARGET</code>-cookies för det Audience Manager användar-ID som skickats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobila enheter </p> </td> 
   <td colname="col2"> <p>Se inställningarna för avanmälning och sekretess för: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/sv-SE/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-enheter </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/sv-SE/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-enheter </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Dina slutanvändare kan också avanmäla sig från global datainsamling genom att besöka webbplatserna för våra branschstandardspartners.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Följ instruktionerna för avanmälan som beskrivs ovan:

* [!DNL Audience Manager]All datainsamling, segmentering och aktivering upphör i så länge användaren inte rensar sina webbläsarcookies.
* Historiska data tas bort från användarprofilen efter 120 dagar.

### Avanmälan på partnernivå med deklarerade ID-anrop

Genom att avanmäla dig på partnernivå kan du avanmäla dina användare från datainsamling av specifika [!DNL Audience Manager]-partners. Du kan skicka avanmälningsbegäranden på partnernivå för enhets-ID:n, inklusive [!DNL CRM] ID:n och hashade e-postadresser.

Efter en avanmälan på partnernivå med ett deklarerat ID-anrop:

* [CRM ID](../../reference/ids-in-aam.md) tas bort från datainsamling
* Det sista enhets-ID ([unikt användar-ID för Audience Manager](../../reference/ids-in-aam.md)) som är länkat till [CRM-ID](../../reference/ids-in-aam.md) tas bort från datainsamling.
* [!DNL Audience Manager] kommer att upphöra med all datainsamling, segmentering eller aktivering som fortsätter för  [!DNL CRM] ID:t och det sista enhets-ID:t som är länkat till  [!DNL CRM] ID:t,
* [!DNL Audience Manager] delar upp det avvalda  [!DNL CRM] ID:t och det sista enhets-ID:t från alla segment,
* [!UICONTROL Destination] partners får en begäran om att dela upp segment för  [!DNL CRM] ID:t och det sista enhets-ID:t. Avsegmentering fungerar för destinationer i [realtid](data-privacy-requests.md#aam-partners-with-unsegmentation) och satsvisa destinationer.
* Inga historiska data tas bort.

När [!DNL Audience Manager] tar emot en avanmälningsbegäran på partnernivå innehåller [!DNL JSON] som returneras av [!DNL DCS] felkoden [171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), med meddelandet [!UICONTROL "Encountered opt out tag"], i stället för användar-ID:t för [!DNL Audience Manager].

Du kan göra en deklarerad ID-avanmälan med nyckelvärdesparen `d_cid` och `d_cid_ic`. Gamla parametrar som `d_dpid` och `d_dpuuid` fungerar fortfarande, men betraktas som föråldrade. Se [CID ersätter DPID och DPUUID](../../reference/cid.md). I exemplen visar *kursiv stil* platshållaren för en variabel.

#### Avanmäl dig med [!DNL CID] och [!DNL CID_IC]

En beskrivning och syntax finns i [URL-variabler och syntax för deklarerade ID:n](../../features/declared-ids.md#variables-and-syntax).

| Avanmälan med | Exempel på kod |
|--- |--- |
| Ett dataleverantörs-ID och användar-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| En integreringskod och användar-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Flera `d_cid` och `d_cid_ic` nyckelvärdepar. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Avanmälan på partnernivå med enhets-ID-anrop

Genom att avanmäla dig på partnernivå kan du avanmäla dina användare från datainsamling av specifika [!DNL Audience Manager]-partners. Du kan avanmäla datainsamling för ett visst enhets-ID för ett varumärke genom att göra följande anrop till [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Avanmälan med | Exempel på kod |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Ett [!DNL Experience Cloud]-ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Läs mer om `uuid`, `mid` och `imsOrgId` i [index över ID:n i Audience Manager](/help/using/reference/ids-in-aam.md).

Efter en avanmälan på partnernivå med ett enhets-ID-anrop:

* Enhetens ID tas bort från datainsamling.
* [!DNL Audience Manager]All datainsamling, segmentering och aktivering upphör i för partnern för det enhets-ID:t.
* [!DNL Audience Manager] delar upp enhets-ID från alla segment,
* Destinationspartners tar emot begäran om att avsegmentera enhetens ID. Avsegmentering fungerar för destinationer i [realtid](data-privacy-requests.md#aam-partners-with-unsegmentation) och satsvisa destinationer.
* Inga historiska data tas bort.

## [!DNL Audience Manager] Partners med osegmenteringsfunktioner  {#aam-partners-with-unsegmentation}

[!DNL Audience Manager] kommer att försöka meddela aktiveringspartners om begäranden om borttagning från registrerade genom att skicka dem information som delar upp (eller tar bort segment) för att hjälpa dig att automatisera dina förfrågningar om sekretess för konsumentdata.

Några av våra aktiveringspartners:

1. Det går inte att använda uppsegmenteringsbegäranden från [!DNL Audience Manager] och/eller
2. Kan inte ta emot uppdateringar från [!DNL Audience Manager] oftare än en gång på 30 dagar.

I sådana fall kan ni inte skicka automatiska borttagningsförfrågningar till aktiveringspartners via [!DNL Audience Manager].

Se [listan över enhetsbaserade mål](/help/using/features/destinations/device-based-destinations-list.md) för att se vilka [!DNL Audience Manager] aktiveringspartners som stöder segmentdelning.

## Förfrågningar om datakorrigering {#correction}

Eftersom [!DNL Audience Manager] inte är källan till data finns det en begränsad roll för datakorrigering i [!DNL Audience Manager]. Korrigeringen kan innebära att konsumenten har begärt att antingen diskvalificeras från ett felaktigt [!UICONTROL trait]/[!UICONTROL segment] eller kvalificeras till önskat [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] kunderna kan välja att hämta relevanta signaler/egenskaper/segment mot användarprofiler och skicka informationen via  [offlinedatainmatning ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) till  [!DNL Audience Manager]. Observera att användaren fortsätter att kvalificera sig för det ursprungliga [!UICONTROL trait] och [!UICONTROL segments] om de upprepar sitt beteende.
