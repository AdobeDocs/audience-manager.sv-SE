---
description: Det här dokumentet beskriver de tekniska detaljerna kring dataintegritet för Audience Manager.
seo-description: Det här dokumentet beskriver de tekniska detaljerna kring dataintegritet för Audience Manager.
seo-title: Begäranden om dataintegritet
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Begäranden om dataintegritet
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 0%

---


# Begäranden om dataintegritet {#data-privacy-requests}

## Översikt {#overview}

I det här dokumentet finns en översikt över hur du hanterar enskilda dataintegritets- och avanmälningsbegäranden som du kan skicka till [!DNL Audience Manager] via [Privacy Servicens användargränssnitt](https://privacyui.cloud.adobe.io/) och **[!DNL Privacy Service API]**.

Med de här verktygen kan du skicka förfrågningar om sekretess för konsumentdata som gjorts under [!DNL GDPR] och [!DNL CCPA].

Innan vi läser den här artikeln rekommenderar vi att du går igenom ordlistan för [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) och [CCPA-ordlistan](aam-ccpa-glossary.md)för att få en bättre förståelse för den terminologi som används här.

Du kan skicka enskilda förfrågningar om åtkomst till och radering av konsumentdata från [!DNL Audience Manager]på två sätt:

* Genom [Privacy Servicens gränssnitt](https://privacyui.cloud.adobe.io/). Se dokumentationen [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Genom **[!DNL Privacy Service API]**. Se dokumentationen [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) och [!DNL API] referensen [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

När du skickar individuella förfrågningar om dataintegritet kan du skicka alla identifierare (ID), enligt beskrivningen i avsnittet [!DNL Audience Manager] Audience Manager-identifierare **[](data-privacy-ids.md)**, tillsammans med deras respektive namnområdes-ID (ID för datakälla).

Det finns två typer av förfrågningar i [Privacy Servicen](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) : förfrågningar om dataåtkomst och dataradering.

## Begäranden om dataåtkomst {#access-data}

Du kan skicka enskilda dataåtkomstbegäranden via [Privacy Servicens gränssnitt](https://privacyui.cloud.adobe.io/) (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) eller genom att ringa [!DNL Privacy Service API] (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) och [!DNL API] referens [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Med [Privacy Servicens användargränssnitt](https://privacyui.cloud.adobe.io/) kan du skapa nya jobbbegäranden antingen genom att använda [!UICONTROL Request Builder] eller genom att överföra en [!DNL JSON] fil.

Om du vill se hur en giltig [!DNL JSON] fil ser ut kan du [hämta ett exempel på JSON](../data-security-and-privacy/assets/access_request.json).

Vi förstår att ni strävar efter att uppfylla era förfrågningar om dataintegritet inom den tidsperiod som fastställs i lagstiftningen.

## Begäranden om borttagning av data {#delete-data}

Du kan skicka begäranden om borttagning av data via [Privacy Servicens gränssnitt](https://privacyui.cloud.adobe.io/) (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) eller genom att ringa till [!DNL Privacy Service API] (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) och [!DNL API] referens [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Med [Privacy Servicens användargränssnitt](https://privacyui.cloud.adobe.io/) kan du skapa nya jobbbegäranden antingen genom att använda [!UICONTROL Request Builder] eller genom att överföra en [!DNL JSON] fil.

Om du vill se hur en giltig [!DNL JSON] fil ser ut kan du [hämta ett exempel på JSON](../data-security-and-privacy/assets/access_request.json).

Adobe förstår att ni strävar efter att uppfylla era kundförfrågningar om datasekretess inom 30 dagar. Av den anledningen [!DNL Adobe] är du fast besluten att behandla din begäran om att ta bort data så snart som möjligt.

Som svar på dina förfrågningar om borttagning av konsumentdata tar bort egenskaper och segment som är kopplade till den identifierare som ingår i begäran [!DNL Audience Manager] [!DNL Audience Manager] . Dessutom kommer respektive [!DNL Audience Manager] identifierare för den person som avanmälde sig från ytterligare datainsamling av [!DNL Audience Manager] och respektive ID-mappningar att tas bort.

När du skickar deklarerade ID:n, t.ex. [!DNL CRM] enhets-ID:n eller [!DNL cookie] ID:n, i datasekretessbegäranden, [!DNL Audience Manager] utförs den nödvändiga borttagningen på alla länkade enheter (upp till 100 enheter per deklarerat ID).

[!DNL Audience Manager] kommer att försöka meddela aktiveringspartners om raderingsbegäranden genom att skicka dem information om att dela upp segment för registrerade som begär att vissa uppgifter ska raderas. Vissa aktiveringspartners:

1. Det går inte att använda begäran om att dela upp segment (eller ta bort segment) från [!DNL Audience Manager] och/eller
2. Kan inte ta emot uppdateringar från [!DNL Audience Manager] inom 30 dagar. I sådana fall kan [!DNL Audience Manager] kunderna inte skicka borttagningsbegäranden till aktiveringspartners på ett automatiserat sätt via [!DNL Audience Manager].

I sådana fall kan du inte skicka borttagningsbegäranden till aktiveringspartners på ett automatiskt sätt via [!DNL Audience Manager].

Ladda ned vårt [Partner Excel-blad](assets/AAM-Partners-October2019.xlsx) för att se vilka [!DNL Audience Manager] aktiveringspartners som stöder segmentering.

## Avanvisningsbegäranden {#opt-out-requests}

[!DNL Audience Manager] stöder branschövergripande standarder när det gäller hantering av avanmälan. Läs vidare för att få fullständig information om vilka typer av undantag som stöds av [!DNL Audience Manager].

Begäran om dataåtkomst och borttagning hanteras via [Privacy Servicen](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), men avanmälningsbegäranden stöds för närvarande via [!DNL DCS API]. Läs vidare för att lära dig hur avanmälningssamtalen [!DNL API] ska se ut.

### Globala avanmälningsbegäranden

Den globala avanmälningen representerar en avanmälan över [!DNL Audience Manager] och andra [!DNL Adobe Experience Cloud] lösningar för alla varumärken. Tabellen nedan visar de metoder som används för global avanmälan:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avanmäl dig för </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>Sidan <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices </a> innehåller enklicksfunktioner som gör att slutanvändarna kan styra och avanmäla datainsamling med annonslösningarna i Adobe Experience Cloud (inklusive Audience Manager). Mer information finns i avsnittet om <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> företagskunder </a> på sidan Sekretessalternativ. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkta API-anrop till Audience Manager </p> </td> 
   <td colname="col2"> <p>Dina användare kan avanmäla sig från datainsamling av alla Audience Manager-varumärken genom att ringa till DCS API nedan och inkludera användar-ID:t för <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Därför kommer vi att ange <code>demdex=NOTARGET</code> och <code>dextp=NOTARGET</code> cookies för det skickade användar-ID:t för Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobila enheter </p> </td> 
   <td colname="col2"> <p>Se avanmälnings- och sekretessinställningarna för: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-enheter </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-enheter </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Dina slutanvändare kan också avanmäla sig från global datainsamling genom att besöka våra branschstandardpartners webbplatser.

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Efter de avanmälningsbegäranden som beskrivs ovan:

* [!DNL Audience Manager] upphör med all datainsamling, segmentering eller aktivering så länge användaren inte rensar sina cookies i webbläsaren.
* Historiska data tas bort från användarprofilen efter 120 dagar.

### Deltagande på partnernivå med deklarerade ID-anrop

Genom att avanmäla dig på partnernivå kan du avanmäla dina användare från datainsamling av specifika [!DNL Audience Manager] partner. Du kan skicka avanmälningsförfrågningar på partnernivå för enhets-ID:n, inklusive [!DNL CRM] ID:n och hashade e-postadresser.

Efter en avanmälan på partnernivå med ett deklarerat ID-anrop:

* ID:t för [kreditriskreducering](../../reference/ids-in-aam.md) tas bort från datainsamlingen.
* Det sista enhets-ID ([Audience Manager-unikt användar-ID](../../reference/ids-in-aam.md)) som är länkat till [CRM-ID](../../reference/ids-in-aam.md) har avslagits från datainsamling.
* [!DNL Audience Manager] kommer att upphöra med all datainsamling, segmentering eller aktivering som fortsätter för [!DNL CRM] ID:t och det sista enhets-ID:t som är länkat till [!DNL CRM] ID:t,
* [!DNL Audience Manager] delar upp det avvalda [!DNL CRM] ID:t och det sista enhets-ID:t från alla segment,
* [!UICONTROL Destination] partners får en begäran om att dela upp segment för [!DNL CRM] -ID och det sista enhets-ID:t. Osegmentering fungerar för både [realtids](data-privacy-requests.md#aam-partners-with-unsegmentation) - och batchdestinationer.
* Inga historiska data tas bort.

När [!DNL Audience Manager] tar emot en begäran om avanmälan på partnernivå innehåller den [!DNL JSON] som returneras av [!DNL DCS] felkoden 171 [med meddelandet](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), i stället för [!UICONTROL "Encountered opt out tag"][!DNL Audience Manager] användar-ID:t.

Du kan göra en deklarerad ID-avanmälan med `d_cid` - och `d_cid_ic` nyckelvärdepar. Gamla parametrar som `d_dpid` och `d_dpuuid` fungerar fortfarande, men betraktas som inaktuella. Se [CID ersätter DPID och DPUUID](../../reference/cid.md). I exemplen *visar kursiv* en variabelplatshållare.

#### Avanmäl dig med [!DNL CID] och [!DNL CID_IC]

En beskrivning och syntax finns i [URL-variabler och syntax för deklarerade ID:n](../../features/declared-ids.md#variables-and-syntax).

| Avanmäl dig med | Kodexempel |
|--- |--- |
| Ett dataleverantörs-ID och användar-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| En integrationskod och användar-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Flera `d_cid` - och `d_cid_ic` nyckelvärdepar. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Deltagande på partnernivå med enhets-ID-anrop

Genom att avanmäla dig på partnernivå kan du avanmäla dina användare från datainsamling av specifika [!DNL Audience Manager] partner. Du kan avanmäla dig från datainsamling för ett visst enhets-ID för ett varumärke genom att göra följande anrop till [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Avanmäl dig med | Kodexempel |
|--- |--- |
| An [!DNL Audience Manager] ( [!DNL Unique User ID]`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Ett [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Läs mer om `uuid`, `mid` och `imsOrgId` i [index för ID:n i Audience Manager](/help/using/reference/ids-in-aam.md).

Efter en anmälan på partnernivå med ett enhets-ID-anrop:

* Enhets-ID:t har avvalts från datainsamling.
* [!DNL Audience Manager] kommer att upphöra med all datainsamling, segmentering eller aktivering för partnern, och fortsätta med enhets-ID:t.
* [!DNL Audience Manager] delar upp enhets-ID från alla segment,
* Destinationspartners tar emot begäran om att dela upp segment för enhets-ID:t. Osegmentering fungerar för både [realtids](data-privacy-requests.md#aam-partners-with-unsegmentation) - och batchdestinationer.
* Inga historiska data tas bort.

## [!DNL Audience Manager] Partners med osegmenteringsfunktioner {#aam-partners-with-unsegmentation}

För att hjälpa er att automatisera era förfrågningar om sekretess för konsumentdata försöker ni meddela aktiveringspartners om förfrågningar om radering från registrerade genom att skicka dem information om att dela upp (eller ta bort) segment. [!DNL Audience Manager]

Några av våra aktiveringspartners:

1. Kan inte hantera uppsegmenteringsbegäranden från [!DNL Audience Manager] och/eller
2. Kan inte ta emot uppdateringar från [!DNL Audience Manager] oftare än en gång på 30 dagar.

I sådana fall kan du inte skicka borttagningsbegäranden till aktiveringspartners på ett automatiskt sätt via [!DNL Audience Manager].

Se [listan över enhetsbaserade destinationer](/help/using/features/destinations/device-based-destinations-list.md) för att se vilka [!DNL Audience Manager] aktiveringspartners som stöder avsegmentering.

## Begäranden om datakorrigering {#correction}

Eftersom [!DNL Audience Manager] inte är källan till data finns det en begränsad roll för datakorrigering i [!DNL Audience Manager]. Korrigeringen kan innebära att konsumenten har begärt att antingen bli diskvalificerad från ett felaktigt [!UICONTROL trait]/[!UICONTROL segment] eller kvalificerad till det önskade [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] kunderna kan välja att hämta relevanta signaler/egenskaper/segment mot användarprofiler och skicka informationen via [offlinedata](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) till [!DNL Audience Manager]. Observera att användaren fortsätter att kvalificera sig för originalet [!UICONTROL trait] och [!UICONTROL segments] om han/hon upprepar sitt beteende.
