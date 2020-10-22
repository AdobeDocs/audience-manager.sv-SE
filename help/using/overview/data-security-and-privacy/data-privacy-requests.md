---
description: Det här dokumentet innehåller teknisk information som rör efterlevnad av datasekretesslagar i Audience Manager.
seo-description: Det här dokumentet innehåller teknisk information som rör efterlevnad av datasekretesslagar i Audience Manager.
seo-title: Förfrågningar om datasekretess
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Förfrågningar om datasekretess
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 58%

---


# Förfrågningar om datasekretess {#data-privacy-requests}

## Översikt {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

Innan du läser den här artikeln rekommenderar vi att du går igenom ordlistorna för [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) och [CCPA](aam-ccpa-glossary.md) för att få en bättre förståelse för den terminologi som används här.

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* Genom gränssnittet för [Privacy Service](https://privacyui.cloud.adobe.io/). Se dokumentationen [här](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Genom **[!DNL Privacy Service API]**. See the documentation [here](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) and the [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)** section, along with their respective namespace IDs (data source IDs).

[Privacy Service](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html) har stöd för två typer av förfrågningar: förfrågningar om dataåtkomst och dataradering.

## Förfrågningar om dataåtkomst {#access-data}

You can send individual data access requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Med användargränssnittet i [Privacy Service](https://privacyui.cloud.adobe.io/) kan du skapa nya jobbförfrågningar genom att använda [!UICONTROL Request Builder] eller överföra en [!DNL JSON]-fil.

Om du vill se hur en giltig [!DNL JSON]-fil ser ut kan du [ ladda ned en JSON-fil som exempel](../data-security-and-privacy/assets/access_request.json).

Vi vet att ni strävar efter att uppfylla förfrågningar om datasekretess inom den tidsperiod som fastställs i lagstiftningen.

## Förfrågningar om dataradering {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Med användargränssnittet i [Privacy Service](https://privacyui.cloud.adobe.io/) kan du skapa nya jobbförfrågningar genom att använda [!UICONTROL Request Builder] eller överföra en [!DNL JSON]-fil.

Om du vill se hur en giltig [!DNL JSON]-fil ser ut kan du [ ladda ned en JSON-fil som exempel](../data-security-and-privacy/assets/access_request.json).

Adobe vet att ni strävar efter att uppfylla förfrågningar om datasekretess inom 30 dagar. For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

When you send declared IDs, such as cross device [!DNL CRM] IDs or [!DNL cookie] IDs, in data privacy requests, [!DNL Audience Manager] will perform the necessary deletion on all the linked devices (up to 100 devices per declared ID).

[!DNL Audience Manager] försöker meddela aktiveringspartners om borttagningsbegäran genom att skicka osegmenterad information om registrerade som begär att vissa data ska tas bort. Vissa aktiveringspartners:

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

I sådana fall kan ni inte skicka automatiska borttagningsförfrågningar till aktiveringspartners via [!DNL Audience Manager].

Download our [Partner Excel sheet](assets/AAM-Partners-October2019.xlsx) to see which [!DNL Audience Manager] activation partners support unsegment.

## Begäran om avanmälan {#opt-out-requests}

[!DNL Audience Manager] stöder branschövergripande standarder när det gäller hantering av avanmälan. Read on for complete information on the types of opt-out supported by [!DNL Audience Manager].

Begäran om åtkomst och borttagning av data hanteras via [Privacy Service](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html), men förfrågningar om avanmälan stöds för närvarande via [!DNL DCS API]. Read on to learn what the opt-out [!DNL API] calls should look like.

### Globala förfrågningar om avanmälan

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. Tabellen nedan visar de metoder som används för global avanmälan:

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
   <td colname="col2"> <p>Sidan <a href="https://www.adobe.com/se/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices </a> innehåller enklicksfunktioner som gör att slutanvändarna kan styra och välja bort datainsamling med annonslösningarna i Adobe Experience Cloud (inklusive Audience Manager). Mer information finns i avsnittet för <a href="https://www.adobe.com/se/privacy/opt-out.html#customeruse" format="http" scope="external"> företagskunder </a> på sidan Privacy Choices. </p> </td> 
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

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

Efter en avanmälan på partnernivå med ett deklarerat ID-anrop:

* [CRM ID](../../reference/ids-in-aam.md) tas bort från datainsamling
* Det sista enhets-ID ([unikt användar-ID för Audience Manager](../../reference/ids-in-aam.md)) som är länkat till [CRM-ID](../../reference/ids-in-aam.md) tas bort från datainsamling.
* [!DNL Audience Manager] kommer att upphöra med all datainsamling, segmentering eller aktivering som fortsätter för [!DNL CRM] ID:t och det sista enhets-ID:t som är länkat till [!DNL CRM] ID:t,
* [!DNL Audience Manager] delar upp det avvalda [!DNL CRM] ID:t och det sista enhets-ID:t från alla segment,
* [!UICONTROL Destination] partners får en begäran om att dela upp segment för [!DNL CRM] -ID och det sista enhets-ID:t. Avsegmentering fungerar för destinationer i [realtid](data-privacy-requests.md#aam-partners-with-unsegmentation) och satsvisa destinationer.
* Inga historiska data tas bort.

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

Du kan göra en deklarerad ID-avanmälan med nyckelvärdesparen `d_cid` och `d_cid_ic`. Gamla parametrar som `d_dpid` och `d_dpuuid` fungerar fortfarande, men betraktas som föråldrade. Se [CID ersätter DPID och DPUUID](../../reference/cid.md). I exemplen visar *kursiv stil* platshållaren för en variabel.

#### Avanmäl dig med [!DNL CID] och [!DNL CID_IC]

En beskrivning och syntax finns i [URL-variabler och syntax för deklarerade ID:n](../../features/declared-ids.md#variables-and-syntax).

| Avanmälan med | Exempel på kod |
|--- |--- |
| Ett dataleverantörs-ID och användar-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| En integreringskod och användar-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Flera `d_cid` - och `d_cid_ic` nyckelvärdepar. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Avanmälan på partnernivå med enhets-ID-anrop

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. Du kan avanmäla datainsamling för ett visst enhets-ID för ett varumärke genom att göra följande anrop till [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Avanmälan med | Exempel på kod |
|--- |--- |
| An [!DNL Audience Manager] ( [!DNL Unique User ID]`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Ett [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Läs mer om `uuid`, `mid` och `imsOrgId` i [index över ID:n i Audience Manager](/help/using/reference/ids-in-aam.md).

Efter en avanmälan på partnernivå med ett enhets-ID-anrop:

* Enhetens ID tas bort från datainsamling.
* [!DNL Audience Manager]All datainsamling, segmentering och aktivering upphör i för partnern för det enhets-ID:t.
* [!DNL Audience Manager] delar upp enhets-ID från alla segment,
* Destinationspartners tar emot begäran om att avsegmentera enhetens ID. Avsegmentering fungerar för destinationer i [realtid](data-privacy-requests.md#aam-partners-with-unsegmentation) och satsvisa destinationer.
* Inga historiska data tas bort.

## [!DNL Audience Manager] Partners med osegmenteringsfunktioner {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

Några av våra aktiveringspartners:

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

I sådana fall kan ni inte skicka automatiska borttagningsförfrågningar till aktiveringspartners via [!DNL Audience Manager].

Consult the [list of device-based destinations](/help/using/features/destinations/device-based-destinations-list.md) to see which [!DNL Audience Manager] activation partners support unsegment.

## Förfrågningar om datakorrigering {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] kunderna kan välja att hämta relevanta signaler/egenskaper/segment mot användarprofiler och skicka informationen via [offlinedata](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) till [!DNL Audience Manager]. Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
