---
description: ID-tjänstkunder bör läsa det här avsnittet för information om hur du läser besökarens cookie för de ID som krävs för att göra DCS API-anrop.
seo-description: ID-tjänstkunder bör läsa det här avsnittet för information om hur du läser besökarens cookie för de ID som krävs för att göra DCS API-anrop.
seo-title: Hämta användar-ID:n och regioner via Adobe Experience Platform Identity Service
solution: Audience Manager
title: Hämta användar-ID:n och regioner via Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 8%

---


# Hämta användar-ID:n och regioner via Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID-tjänstkunder bör läsa det här avsnittet för information om hur du läser besökarens cookie för de ID:n som krävs för att göra [!DNL DCS] API-anrop.

## Hämta användar-ID från ID-tjänstens cookie {#get-user-ids-from-service-cookie}

Med [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html) får användare som kommer till din webbplats tillgång till besökar- och region-ID:n. Dessa ID:n identifierar användare i alla lösningar i [!DNL Experience Cloud] och de krävs om du vill ringa [!DNL DCS] samtal.

* Informationen [!UICONTROL user ID] krävs för att identifiera och koppla data till en viss besökare.
* Detta [!UICONTROL region ID] är obligatoriskt eftersom det är kopplat till ett regionalt servernamn som du måste skicka data till [!DNL DCS]. Informationen [!DNL DCS] lagras i datacenter som är geografiskt närmast besökarna. See [DCS Region IDs, Locations, and Host Names](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

ID-tjänstkunder kan extrahera den här informationen från ID-tjänstens cookie eller genom att anropa en funktion. Tabellen nedan beskriver de uppgifter och steg som du behöver utföra för att komma igång.

Kod i *kursiv stil* representerar en variabel platshållare.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Uppgift </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Kontrollera din <span class="keyword"> Experience Cloud</span> -status</b> </p> </td> 
   <td colname="col2"> <p>Du behöver ett <span class="keyword"> Experience Cloud</span> -konto för att kunna använda ID-tjänsten. Om du har ett <span class="keyword"> Experience Cloud</span> -konto, bra! </p> <p> Om du inte är en del av <span class="keyword"> Experience Cloud</span>kan du registrera dig. Vi vill gärna ha dig och det finns alltid plats för mer. Instruktioner om hur du konfigurerar ett konto finns i <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Aktivera dina lösningar för bastjänster</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Konfigurera <span class="keyword"> ID-tjänsten</span></b> </p> </td> 
   <td colname="col2"> <p>ID- <span class="keyword"> tjänsten</span> består av JavaScript-kod som placeras på varje sida som du vill använda för datainsamling. Mer information finns i <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> implementeringsguiderna</a> för ID-tjänster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Läs <span class="keyword"> ID-tjänstens</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>ID-tjänsten <span class="keyword"></span> lagrar användar-ID och region-ID i AMCV-cookien. Det fullständiga cookie-namnet är <code>AMCV_<i>###</i>@AdobeOrg</code>. Elementen är <code><i>###</i></code> platshållare för ditt företags-ID. Mer information finns i <a href="https://docs.adobe.com/content/help/sv-SE/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies och Experience Cloud ID</a> . </p> <p>Tolka AMCV-cookien för följande nyckelvärdepar: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Detta nyckelvärdepar innehåller användar-ID:t för <span class="keyword"> Experience Cloud</span> . </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Detta nyckelvärdepar innehåller region-ID (kallas ibland för <span class="term"> platstips</span>) som är associerat med ett regionalt servernamn. </li> 
     </ul> </p> <p>Du kan ringa till <span class="wintitle"> DCS</span> när du har användar-ID:n och region-ID:n. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Hämta <span class="keyword"> Experience Cloud-ID</span> med getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Valfritt)</i> Den här funktionen returnerar besökar-ID:t för <span class="keyword"> Experience Cloud</span> . Den är utformad för anpassade lösningar och specifika användningsfall. Se <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Arbeta med getMarketingCloudVisitorID</a> nedan och den <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> relaterade dokumentationen</a>för ID-tjänsten. </p> <p>Du behöver inte använda detta om du hämtar användar-ID:n och plats-ID:n från ID-tjänstens cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Arbeta med `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Ett annat sätt att hämta besökar-ID är med `getMarketingCloudVisitorID` funktionen. När funktionen anropas efterfrågas [!DNL ID service] och ett ID returneras. `getMarketingCloudVisitorID` godkänner det valfria `callback` argumentet som visas:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Användning och syfte av återanrop {#callback-usage}

`callback` är valfritt. Den här funktionen fungerar utan den, men returnerar bara ett ID när en besökare har en [!DNL Experience Cloud] cookie i sin webbläsare. Om besökarens cookie saknas, eller om en besökare inte har något ID, returnerar funktionen ett tomt `()` objekt. Detta kan inträffa även efter att sidan har lästs in och besökaren får ett nytt ID. För att undvika detta måste den här funktionen `callback` kontrollera om det finns ett besökar-ID när sidan har lästs in. Utan `callback`det returnerar besökar-ID-funktionen inte ett ID även om det skrivs till besökarens webbläsare senare.

## Nästa steg {#next-steps}

När du har användar-ID och region-ID kan du börja skicka och ta emot [!DNL DCS] data. Se [Göra DCS API-anrop](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).