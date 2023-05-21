---
description: ID-tjänstkunder bör läsa det här avsnittet för information om hur du läser besökarens cookie för de ID som krävs för att göra DCS API-anrop.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Hämta användar-ID:n och regioner via Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 4%

---

# Hämta användar-ID:n och regioner via Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID-tjänstkunder bör läsa detta avsnitt för information om hur de läser besökarens cookie för de ID:n som krävs för att skapa [!DNL DCS] API-anrop.

## Hämta användar-ID från ID-tjänstens cookie {#get-user-ids-from-service-cookie}

The [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) tilldelar besökar- och region-ID till användare som kommer till din webbplats. Dessa ID:n identifierar användare i alla lösningar i [!DNL Experience Cloud] och de är obligatoriska om du vill skapa [!DNL DCS] samtal.

* The [!UICONTROL user ID] krävs för att identifiera och koppla uppgifter till en viss besökare.
* The [!UICONTROL region ID] krävs eftersom det är knutet till ett regionalt servernamn som du måste skicka data till [!DNL DCS]. The [!DNL DCS] lagrar information i datacenter som är geografiskt närmast besökarna. Se [DCS-region-ID, -platser och -värdnamn](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

ID-tjänstkunder kan extrahera den här informationen från ID-tjänstens cookie eller genom att anropa en funktion. Tabellen nedan beskriver de uppgifter och steg som du behöver utföra för att komma igång.

Kod i *kursiv* representerar en variabelplatshållare.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Uppgift </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Kontrollera <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>Du behöver en <span class="keyword"> Experience Cloud</span> konto för att använda ID-tjänsten. Om du har en <span class="keyword"> Experience Cloud</span> bra konto! </p> <p> Om du inte är en del av <span class="keyword"> Experience Cloud</span>och sedan registrera sig. Vi vill gärna ha dig och det finns alltid plats för mer. Instruktioner om hur du konfigurerar ett konto finns i <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Möjliggör för era lösningar för bastjänster</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Konfigurera <span class="keyword"> ID-tjänst</span></b> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> ID-tjänst</span> består av JavaScript-kod som placeras på varje sida som du vill använda för datainsamling. Se ID-tjänsten <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> implementeringsguider</a> för mer information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Läs <span class="keyword"> ID-tjänst</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> ID-tjänst</span> lagrar användar-ID och region-ID i AMCV-cookien. Det fullständiga cookie-namnet är <code>AMCV_<i>###</i>@AdobeOrg</code>. The <code><i>###</i></code> är platshållare för ditt företags-ID. Se <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies och Experience Cloud ID</a> för mer information. </p> <p>Tolka AMCV-cookien för följande nyckelvärdepar: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Detta nyckelvärdepar innehåller <span class="keyword"> Experience Cloud</span> användar-ID. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Detta nyckelvärdepar innehåller region-ID (kallas ibland <span class="term"> platstips</span>) som är associerat med ett regionalt servernamn. </li> 
     </ul> </p> <p>Du kan ringa <span class="wintitle"> DCS</span> när du har användar-ID:n och region-ID:n. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Hämta <span class="keyword"> Experience Cloud ID</span> med getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Valfritt)</i> Den här funktionen returnerar <span class="keyword"> Experience Cloud</span> besökar-ID. Den är utformad för anpassade lösningar och specifika användningsfall. Se <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Arbeta med getMarketingCloudVisitorID</a> nedan och <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> relaterad dokumentation för ID-tjänster</a>. </p> <p>Du behöver inte använda detta om du hämtar användar-ID:n och plats-ID:n från ID-tjänstens cookie. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Arbeta med `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Ett annat sätt att få besökar-ID är med `getMarketingCloudVisitorID` funktion. När den anropas frågar den här funktionen efter [!DNL ID service] och returnerar ett ID. `getMarketingCloudVisitorID` godkänner det valfria `callback` argument som visas:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Användning och syfte av återanrop {#callback-usage}

`callback` är valfritt. Den här funktionen fungerar utan den, men returnerar bara ett ID när en besökare har en [!DNL Experience Cloud] cookie i webbläsaren. Om besökarens cookie saknas, eller om en besökare inte har något ID, returnerar funktionen ett tomt `()` -objekt. Detta kan inträffa även efter att sidan har lästs in och besökaren får ett nytt ID. För att undvika detta `callback` tvingar den här funktionen att söka efter ett besökar-ID när sidan har lästs in. Utan `callback`, returnerar besökar-ID-funktionen inte ett ID även om det skrivs till besökarens webbläsare senare.

## Nästa steg {#next-steps}

När du har användar-ID och region-ID kan du börja skicka och ta emot [!DNL DCS] data. Se [Göra DCS API-anrop](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
