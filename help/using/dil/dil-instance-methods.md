---
description: Med DIL API:er på instansnivå kan du programmässigt skapa och arbeta med Audience Manager-objekt. Metoderna på förekomstnivå förbättrar API-funktionaliteten som fastställs av klassnivåmetoderna.
keywords: skapa egenskaper;skapa egenskaper
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: DIL-metoder på instansnivå
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 1%

---

# DIL-metoder på instansnivå{#instance-level-dil-methods}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av tillägget [!DNL Data Integration Library (DIL)] och [!DNL DIL].
>
>Befintliga kunder kan fortsätta använda sin [!DNL DIL]-implementering. Adobe kommer dock inte att utveckla [!DNL DIL] efter den här punkten. Kunder uppmuntras att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) för sin långsiktiga datainsamlingsstrategi.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) i stället.

Med API:erna på förekomstnivå [!UICONTROL DIL] kan du skapa och arbeta med Audience Manager-objekt programmatiskt. Metoderna på förekomstnivå förbättrar API-funktionaliteten som fastställs av klassnivåmetoderna.

## Komma igång med DIL-metoder på instansnivå {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

När du arbetar med [!UICONTROL DIL]-API:er på förekomstnivå:

* Åtkomst kräver ett partnernamn och ett behållar-ID (NSID). Kontakta din kontoansvarige på Audience Manager för att få denna information.
* Ersätt eventuell *kursiv*-exempeltext i API-dokumentationen med värde, ID eller annan variabel enligt vad som krävs för den metod du arbetar med.

<!-- 

c_instance_start.xml

 -->

## signaler {#signals}

Lägger till mappningar på kund- och plattformsnivå i frågesträngen för en väntande begäran.

<!-- 

r_dil_signals.xml

 -->

**Funktionssignatur:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Du kan kedja andra API-anrop till den här metoden.
>* Om Adobe Experience Cloud JavaScript-biblioteket finns på sidan väntar `submit()` på att en cookie ska anges i molnet innan en begäran skickas.

**Reserverade begärannycklar**

Följande begärandenycklar är reserverade och kan inte skrivas över av den här metoden:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parametrar**

| Namn | Typ | Beskrivning |
|---|---|---|
| `obj` | Objekt | Ett objekt som representerar nyckelvärdepar för mappningar på plattformsnivå. Parametern accepterar strängar och arrayer som egenskapsvärden i objektet. |
| `prefix` | Sträng | Valfritt. Strängvärdet som är prefixat för varje objektnyckel (ersätter originalnyckeln). |
| `return` | DIL.api | Returnerar API-objektet för aktuell DIL-instans. |

**Svar**

Returnerar API-objektet för aktuell [!UICONTROL DIL]-instans.

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

Lägger till SID:er i frågesträngen för en väntande begäran.

<!-- 

r_dil_traits.xml

 -->

**Funktionssignatur:** `traits:function (sids){}`

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden.

**Parametrar**

| Namn | Typ | Beskrivning |
|---|---|---|
| `sids` | Array | Spåra segment-ID:n i en array. |

**Svar**

Returnerar API-objektet för aktuell [!UICONTROL DIL]-instans.

**Exempelkod**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## loggar {#logs}

Lägg till data i loggfiler i den väntande begäran.

<!-- 

r_dil_logs.xml

 -->

**Funktionssignatur:** `logs: function {key1:value1, key2:value2}`

**Svar**

Returnerar API-objektet för aktuell [!UICONTROL DIL]-instans.

**Exempelkod**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);
</code></pre>

## skicka {#submit}

Skickar alla väntande data till Audience Manager för instansen [!UICONTROL DIL].

<!-- 

r_dil_submit.xml

 -->

**Funktionssignatur:** `submit: function () {}`

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden. Dessutom skriver [!UICONTROL DIL] kodade data till en målcookie. Blanksteg kodas till exempel som `%20` och semikolon som `%3B`.

**Svar**

Returnerar API-objektet för aktuell [!UICONTROL DIL]-instans.

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits(&lbrack; 
<i>123,456, 789</i>&rbrack;).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;).submit();
</code></pre>

## afterResult {#afterresult}

En funktion som körs efter standardåteranropet för målpublicering.

<!-- 

r_dil_after_result.xml

 -->

**Funktionssignatur:** `afterResult: function (fn) {}`

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden.

**Parametrar**

| Namn | Typ | Beskrivning |
|---|---|---|
| `fn` | Funktion | Den funktion som du vill köra efter att JSON har bearbetats av standardåteranropet som hanterar målpublicering. |

**Svar**

Returnerar ett API-objekt för den aktuella [!UICONTROL DIL]-instansen.

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.signals(&lbrace; 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
&rbrace;).afterResult(function(json)&lbrace; 
     //Do something with the JSON data returned from the server. 
&rbrace;).submit();
</code></pre>

## clearData {#cleardata}

Tar bort alla data i en väntande begäran.

<!-- 

r_dil_clear_data.xml

 -->

**Funktionssignatur:** `clearData: function () {}`

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden.

**Svar**

Returnerar API-objektet för aktuell [!UICONTROL DIL]-instans.

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs(&lbrace; 
     file: 'dil.js' 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Lägger till anpassade frågeparametrar som inte uttryckligen definieras av datainsamlingsservern i en väntande begäran.

<!-- 

r_dil_custom_query_params.xml

 -->

**Funktionssignatur:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden.

**Reserverade begärannycklar**

Följande begärandenycklar är reserverade och kan inte skrivas över av den här metoden:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Svar**

Returnerar API-objektet för aktuell DIL-instans.

**Exempelkod**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.customQueryParams(&lbrace; 
     nid: 54231, 
     ntype: 'default' 
&rbrace;); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Returnerar värdet för behållar-NSID för instansen [!UICONTROL DIL]. Användbar för felsökning och felsökning.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Funktionssignatur:** `dil.api.getContainerNSID: function () {}`

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Returnerar kronologiskt sorterade händelseloggdata som en array med strängar. Användbar för felsökning och felsökning.

<!-- 

r_dil_get_event_log.xml

 -->

**Funktionssignatur:** `dil.api.getEventLog: function () {}`

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) &lbrace; 
     alert(log.join('\n')); 
&rbrace;else&lbrace; 
     alert('No log messages'); 
&rbrace;
</code></pre>

## getPartner {#getpartner}

Returnerar partnernamnet för en [!UICONTROL DIL]-instans. Användbar för felsökning och felsökning.

<!-- 

r_dil_get_partner.xml

 -->

**Funktionssignatur:** `dil.api.getPartner: function () {}`

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Returnerar läget för den aktuella [!UICONTROL DIL]-instansen. Användbar för felsökning och felsökning.

<!-- 

r_dil_get_state.xml

 -->

**Funktionssignatur:** `dil.api.getState: function () {}`

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message:'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = &lbrace; 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:&lbrace; 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: &lbrace; 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          &rbrace;, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     &rbrace;, 
     destinationPublishingInfo: &lbrace; 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          &#x200B;+ containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     &rbrace; 
&rbrace; 
*/
</code></pre>

## idSync {#idsync}

Består av två funktioner som gör att datapartners kan utbyta och synkronisera användar-ID mellan sig och Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Funktionssignatur:**

Fungerar med [!UICONTROL DIL] version 2.10 och 3.1 eller senare.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code </th> 
   <th colname="col2" class="entry"> Synkroniserar användar-ID:n </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Mellan olika datapartners och Audience Manager. Partner x använder till exempel detta för att synkronisera ett användar-ID med partner y och sedan skicka det till Audience Manager. </p> <p> <p><b>Viktigt!</b> Den här metoden är föråldrad. Använd metoden <code> idSyncByURL </code> för instansen av Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>När du redan känner till användar-ID:t och vill skicka det till Audience Manager. </p> <p> <p><b>Viktigt!</b> Den här metoden är föråldrad. Använd metoden <code> idSyncByDataSource </code> för instansen av Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync Elements**

`idSync` kan bestå av följande:

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namn </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Sträng </td> 
   <td colname="col3"> <p>Data provider-ID tilldelat av Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Sträng </td> 
   <td colname="col3"> <p>Dataleverantörens unika ID för användaren. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Nummer </td> 
   <td colname="col3"> <p><i>(Valfritt)</i> Anger förfallotid för cookie. Måste vara ett heltal. Standardvärdet är 2 0160 minuter (14 dagar). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> Sträng </td> 
   <td colname="col3"> <p>Mål-URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Makron**

`idSync` accepterar följande makron:

* **`%TIMESTAMP%`:** Skapar en tidsstämpel (i millisekunder). Används för cachebusting.
* **`%DID%`:** Infogar användarens Audience Manager-ID.
* **`%HTTP_PROTO%`:** Anger sidprotokollet ( `http` eller `https`).

**Svar**

Båda funktionerna returnerar `Successfully queued` om de lyckas. De returnerar en felmeddelandesträng om de inte gör det.

**Exempelkod**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync(&lbrace; 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync(&lbrace; 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

## resultat {#result}

Lägger till ett återanrop (som tar emot JSON) i den väntande begäran.

<!-- 

r_dil_result.xml

 -->

**Funktionssignatur:** `result: function (callback) {}`

Det här återanropet ersätter standardåteranropet som hanterar målpublicering.

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden.

**Parametrar**

| Namn | Typ | Beskrivning |
|---|---|---|
| `callback` | Funktion | JavaScript-funktionen som körs av JSONP-återanropet. |

**Svar**

Returnerar API-objektet för aktuell [!UICONTROL DIL]-instans.

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json)&lbrace; 
     //Do something, possibly with the JSON data returned from the server. 
&rbrace;);.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` är en boolesk parameter som styr hur [!UICONTROL DIL] anropar [!UICONTROL Data Collection Servers (DCS)] och Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* När `secureDataCollection= true` (standard) används alltid säkra HTTPS-anrop av [!UICONTROL DIL].

* När `secureDataCollection= false` gör [!UICONTROL DIL] antingen HTTP- eller HTTPS-anrop genom att följa säkerhetsprotokollet som angetts av sidan.

>[!IMPORTANT]
>
>Ange `secureDataCollection= false` om du använder visitorAPI.js och [!UICONTROL DIL] på samma sida. Se kodexemplet nedan.

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     secureDataCollection: false 
&rbrace;);
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` är en boolesk true/false-parameter som styr hur webbläsaren begär resurser från andra domäner.

<!-- 

dil-use-cors-only.xml

 -->

**Översikt**

`useCORSOnly` är false som standard. Falskt innebär att webbläsaren kan utföra resurskontroller med CORS eller JSONP. [!UICONTROL DIL] försöker dock alltid begära resurser med CORS först. Den återgår till JSONP i äldre webbläsare som inte stöder CORS. Om du behöver tvinga webbläsaren att endast använda CORS, till exempel webbplatser som har höga säkerhetskrav, anger du `useCORSOnly:true`.

**Kodexempel**

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     useCORSOnly: true 
&rbrace;);
</code></pre>

>[!IMPORTANT]
>
>* Vi rekommenderar att du bara anger `useCORSOnly: true` när du är säker på att webbplatsens besökare har webbläsare som stöder den här funktionen.
>* När `useCORSOnly: true`, kommer [!UICONTROL DIL] inte att göra ID-anrop från Internet Explorer version 9 eller tidigare.
>

## useImageRequest {#useimagerequest}

Ändrar begärandetypen till bilden `<img>` från skriptet `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Funktionssignatur:** `useImageRequest: function () {}`

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden.

**Svar**

Returnerar ett API-objekt för den aktuella [!UICONTROL DIL]-instansen.

**Exempelkod**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Namnkrav för nyckelvariabler](../features/traits/trait-key-name-requirements.md)
>* [Prefixkrav för nyckelvariabler](../features/traits/trait-variable-prefixes.md)
>* [Synkroniseringsfunktioner i Adobe Experience Platform identitetstjänst](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html?lang=sv-SE)
>* [Skapa DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform identitetstjänst: UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html?lang=sv-SE)
>* [CORS-stöd i Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html?lang=sv-SE)
