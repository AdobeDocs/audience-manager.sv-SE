---
description: Det här dokumentet innehåller tekniker som rör efterlevnad av datasekretessregler för Audience Manager.
seo-description: Det här dokumentet innehåller tekniker som rör efterlevnad av datasekretessregler för Audience Manager.
seo-title: Begäranden om dataintegritet
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Begäranden om dataintegritet
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 39e0224d97d1d27c2b1dcee8e3b0d2d21847551b

---


# Begäranden om dataintegritet {#data-privacy-requests}

## Översikt {#overview}

Det här dokumentet innehåller en översikt över hur du hanterar enskilda dataintegritetsfrågor och avanmälningsbegäranden som du kan skicka till Audience Manager via användargränssnittet [för](https://privacyui.cloud.adobe.io/) sekretesstjänsten och **[!DNL Privacy Service API]**.

Med dessa verktyg kan du skicka förfrågningar om sekretess för konsumentdata som gjorts i enlighet med GDPR och CCPA.

Innan vi läser den här artikeln rekommenderar vi att du går igenom ordlistan för [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) och [CCPA-ordlistan](aam-ccpa-glossary.md)för att få en bättre förståelse för den terminologi som används här.

Du kan skicka enskilda förfrågningar för att få tillgång till och ta bort konsumentdata från Audience Manager på två sätt:

* Genom gränssnittet för [integritetstjänsten](https://privacyui.cloud.adobe.io/). Se dokumentationen [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Genom **[!DNL Privacy Service API]**. Läs dokumentationen [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) och API-referensen [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

När du skickar individuella förfrågningar om dataintegritet kan du skicka alla identifierare (ID) för Audience Manager som beskrivs i avsnittet Identifierare **[för](data-privacy-ids.md)**Audience Manager tillsammans med deras respektive ID för namnrymd (datakälla).

Integritetstjänsten [](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) stöder två typer av förfrågningar: förfrågningar om dataåtkomst och dataradering.

## Begäranden om dataåtkomst {#access-data}

Du kan skicka enskilda förfrågningar om dataåtkomst via [sekretessgränssnittet](https://privacyui.cloud.adobe.io/) (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) eller genom att ringa [!DNL Privacy Service API] (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) och [!DNL API] referens [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Med [sekretessgränssnittet](https://privacyui.cloud.adobe.io/) kan du skapa nya jobbförfrågningar genom att använda [!UICONTROL Request Builder] eller överföra en [!DNL JSON] fil.

Om du vill se hur en giltig [!DNL JSON] fil ser ut kan du [hämta ett exempel på JSON](../data-security-and-privacy/assets/access_request.json).

Vi förstår att ni strävar efter att uppfylla era förfrågningar om dataintegritet inom den tidsperiod som fastställs i lagstiftningen.

## Begäranden om borttagning av data{#delete-data}

Du kan skicka begäranden om borttagning av data via [sekretesstjänstens gränssnitt](https://privacyui.cloud.adobe.io/) (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) eller genom att ringa till [!DNL Privacy Service API] (dokumentation [här](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) och API-referens [här](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Med [sekretessgränssnittet](https://privacyui.cloud.adobe.io/) kan du skapa nya jobbförfrågningar genom att använda [!UICONTROL Request Builder] eller överföra en [!DNL JSON] fil.

Om du vill se hur en giltig [!DNL JSON] fil ser ut kan du [hämta ett exempel på JSON](../data-security-and-privacy/assets/access_request.json).

Adobe förstår att ni strävar efter att uppfylla era kundförfrågningar om datasekretess inom 30 dagar. Därför är Adobe fast beslutet att behandla din begäran om borttagning av data så snart som möjligt.

Som svar på era förfrågningar om borttagning av konsumentdata tar Audience Manager bort egenskaper och segment som är kopplade till Audience Manager-identifieraren som ingår i begäran. Dessutom kommer respektive Audience Manager-identifierare för den person som avanmälde sig från ytterligare datainsamling av Audience Manager och respektive ID-mappningar att tas bort.

När du skickar deklarerade ID:n, t.ex. [!DNL CRM] enhets-ID:n eller cookie-ID:n, i datasekretessförfrågningar utför Audience Manager den nödvändiga borttagningen på alla länkade enheter (upp till 100 enheter per deklarerat ID).

Audience Manager kommer att försöka meddela aktiveringspartners om borttagningsbegäranden genom att skicka dem information om att dela upp segment för registrerade som begär att vissa data ska tas bort. Vissa aktiveringspartners:

1. Det går inte att använda stöd för att dela upp segment (eller ta bort segment) från Audience Manager och/eller
2. Kan inte ta emot uppdateringar från Audience Manager med en frekvens på mindre än 30 dagar. I sådana fall kan Audience Manager-kunder inte skicka begäranden om borttagning till aktiveringspartners på ett automatiserat sätt via Audience Manager.

I sådana fall kan du inte skicka borttagningsbegäranden till aktiveringspartners på ett automatiserat sätt via Audience Manager.

Ladda ned vårt [Partner Excel-blad](assets/AAM-Partners-October2019.xlsx) för att se vilka Audience Manager-aktiveringspartners som stöder unsegment.

## Avanvisningsbegäranden {#opt-out-requests}

Audience Manager stöder branschövergripande standarder för hantering av avanmälan. Läs vidare för att få fullständig information om vilka typer av undantag som Audience Manager har stöd för.

Begäran om åtkomst och borttagning av data hanteras via [sekretesstjänsten](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), men avanmälningsbegäranden stöds för närvarande via DCS API. Läs vidare för att lära dig hur avanmälnings-API-anropen ska se ut.

### Globala avanmälningsbegäranden

Den globala avanmälningen representerar en avanmälan för Audience Manager och andra Adobe Experience Cloud-lösningar för alla varumärken. Tabellen nedan visar de metoder som används för global avanmälan:

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
   <td colname="col2"> <p>Sidan <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices </a> innehåller enklicksfunktioner som gör att slutanvändarna kan styra och välja bort datainsamling med annonslösningarna i Adobe Experience Cloud (inklusive Audience Manager). Mer information finns i avsnittet om <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> företagskunder </a> på sidan Sekretessalternativ. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkta API-anrop till Audience Manager </p> </td> 
   <td colname="col2"> <p>Användarna kan avanmäla sig från datainsamling av alla Audience Manager-varumärken genom att ringa till DCS API nedan och inkludera användar-ID:t för <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Därför kommer vi att ange <code>demdex=NOTARGET</code> och <code>dextp=NOTARGET</code> cookies för det användar-ID som skickats för Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobila enheter </p> </td> 
   <td colname="col2"> <p>Se avanmälnings- och sekretessinställningarna för: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android-enheter </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS-enheter </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Dina slutanvändare kan också avanmäla sig från global datainsamling genom att besöka våra branschstandardpartners webbplatser.

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Efter de avanmälningsbegäranden som beskrivs ovan:

* Audience Manager upphör med all datainsamling, segmentering eller aktivering så länge användaren inte rensar sina webbläsarcookies.
* Historiska data tas bort från användarprofilen efter 120 dagar.

### Deltagande på partnernivå med deklarerade ID-anrop

Genom att avanmäla dig på partnernivå kan du avanmäla dina användare från datainsamling av specifika Audience Manager-partners. Du kan skicka avanmälningsbegäranden på partnernivå för enhets-ID:n, inklusive CRM-ID:n och hashade e-postadresser.

Efter en avanmälan på partnernivå med ett deklarerat ID-anrop:

* ID:t för [kreditriskreducering](../../reference/ids-in-aam.md) tas bort från datainsamlingen.
* Det sista enhets-ID (Unikt användar-ID[för](../../reference/ids-in-aam.md)Audience Manager) som är länkat till [CRM-ID](../../reference/ids-in-aam.md) har avslagits från datainsamling.
* Audience Manager kommer att upphöra med all datainsamling, segmentering eller aktivering som pågår för CRM-id:t och det sista enhets-ID:t som är kopplat till CRM-id:t.
* Audience Manager delar upp det valda CRM-ID:t och det sista enhets-ID:t från alla segment.
* Destinationspartners tar emot begäran om att dela upp segment för CRM-ID:t och det senaste enhets-ID:t. Osegmentering fungerar för både [realtids](data-privacy-requests.md#aam-partners-with-unsegmentation) - och batchdestinationer.
* Inga historiska data tas bort.

När Audience Manager tar emot en begäran om avanmälan på partnernivå innehåller den JSON som returneras av DCS [felkoden 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), med meddelandet [!UICONTROL "Encountered opt out tag"], i stället för användar-ID:t för Audience Manager.

Du kan göra en deklarerad ID-avanmälan med `d_cid` - och `d_cid_ic` nyckelvärdepar. Gamla parametrar som `d_dpid` och `d_dpuuid` fungerar fortfarande, men betraktas som inaktuella. Se [CID ersätter DPID och DPUUID](../../reference/cid.md). I exemplen *visar kursiv* en variabelplatshållare.

#### Avanmäl dig med CID och CID_IC

En beskrivning och syntax finns i [URL-variabler och syntax för deklarerade ID:n](../../features/declared-ids.md#variables-and-syntax).

| Avanmäl dig med | Kodexempel |
|--- |--- |
| Ett dataleverantörs-ID och användar-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| En integrationskod och användar-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Flera d_cid- och d_cid_ic-nyckelvärdepar. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Deltagande på partnernivå med enhets-ID-anrop

Genom att avanmäla dig på partnernivå kan du avanmäla dina användare från datainsamling av specifika Audience Manager-partners. Du kan avanmäla dig från datainsamling för ett visst enhets-ID för ett varumärke genom att göra följande anrop till [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Avanmäl dig med | Kodexempel |
|--- |--- |
| Ett unikt användar-ID (`uuid`) för Audience Manager. | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Ett Experience Cloud-ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Läs mer om `uuid`, `mid` och `imsOrgId` i [index för ID:n i Audience Manager](/help/using/reference/ids-in-aam.md).

Efter en anmälan på partnernivå med ett enhets-ID-anrop:

* Enhets-ID:t har avvalts från datainsamling.
* Audience Manager upphör med all datainsamling, segmentering eller aktivering för partnern, och fortsätter sedan med enhets-ID:t.
* Audience Manager delar upp enhets-ID:t från alla segment.
* Destinationspartners tar emot begäran om att dela upp segment för enhets-ID:t. Osegmentering fungerar för både [realtids](data-privacy-requests.md#aam-partners-with-unsegmentation) - och batchdestinationer.
* Inga historiska data tas bort.

## Audience Manager-partners med osegmenteringsfunktioner {#aam-partners-with-unsegmentation}

För att hjälpa er att automatisera era förfrågningar om sekretess för konsumentdata kommer Audience Manager att försöka meddela aktiveringspartners om förfrågningar om radering från registrerade genom att skicka dem information om att dela upp (eller ta bort) segment.

Några av våra aktiveringspartners:

1. Det går inte att använda uppsegmenteringsbegäranden från Audience Manager och/eller
2. Kan inte ta emot uppdateringar från Audience Manager oftare än en gång på 30 dagar.

I sådana fall kan du inte skicka borttagningsbegäranden till aktiveringspartners på ett automatiserat sätt via Audience Manager.

Se i [listan över enhetsbaserade mål](/help/using/features/destinations/device-based-destinations-list.md) vilka Audience Manager-aktiveringspartners som stöder unsegment.

## Begäranden om datakorrigering {#correction}

Eftersom Audience Manager inte är källan till data finns det en begränsad roll för datakorrigering i Audience Manager. Korrigeringen kan innebära att konsumenten har begärt att antingen bli diskvalificerad från en felaktig egenskap/ett felaktigt segment eller kvalificerad till önskad egenskap/segment.

Audience Manager-kunder kan välja att samla in relevanta signaler/egenskaper/segment mot användarprofiler och skicka informationen via [offlinedata](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) till Audience Manager. Observera att användaren fortsätter att kvalificera sig för den ursprungliga egenskapen och segmenten om de upprepar sitt beteende.
