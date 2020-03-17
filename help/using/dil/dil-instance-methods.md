---
description: Med DIL-API:erna på instansnivå kan du programmässigt skapa och arbeta med Audience Manager-objekt. Metoderna på förekomstnivå förbättrar API-funktionaliteten som fastställs av klassnivåmetoderna.
keywords: create traits;create trait
seo-description: Med DIL-API:erna på instansnivå kan du programmässigt skapa och arbeta med Audience Manager-objekt. Metoderna på förekomstnivå förbättrar API-funktionaliteten som fastställs av klassnivåmetoderna.
seo-title: DIL-metoder på förekomstnivå
solution: Audience Manager
title: DIL-metoder på förekomstnivå
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# DIL-metoder på förekomstnivå{#instance-level-dil-methods}

Med [!UICONTROL DIL] API:erna på instansnivå kan du programmässigt skapa och arbeta med Audience Manager-objekt. Metoderna på förekomstnivå förbättrar API-funktionaliteten som fastställs av klassnivåmetoderna.

## Komma igång med DIL-metoder på förekomstnivå {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

När du arbetar med [!UICONTROL DIL] API:er på förekomstnivå:

* Åtkomst kräver ett partnernamn och ett behållarnamnområdes-ID (NSID). Kontakta din Audience Manager-kontohanterare för att få den här informationen.
* Ersätt valfri *kursiv* text i API-dokumentationen med värde, ID eller annan variabel enligt den metod du arbetar med.

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
>* Om Adobe Experience Cloud JavaScript-biblioteket finns på sidan väntar `submit()` på att molnet ska ange en cookie innan en begäran skickas.


**Reserverade begärandenycklar**

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
| `return` | DIL.api | Returnerar API-objektet för den aktuella DIL-instansen. |

**Svar**

Returnerar API-objektet för den aktuella [!UICONTROL DIL] instansen.

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
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

Returnerar API-objektet för den aktuella [!UICONTROL DIL] instansen.

**Exempelkod**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## loggar {#logs}

Lägg till data i loggfiler i den väntande begäran.

<!-- 

r_dil_logs.xml

 -->

**Funktionssignatur:** `logs: function {key1:value1, key2:value2}`

**Svar**

Returnerar API-objektet för den aktuella [!UICONTROL DIL] instansen.

**Exempelkod**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## skicka {#submit}

Skickar alla väntande data till Audience Manager för [!UICONTROL DIL] instansen.

<!-- 

r_dil_submit.xml

 -->

**Funktionssignatur:** `submit: function () {}`

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden. Skriver även kodade data till en målcookie [!UICONTROL DIL] . Blanksteg kodas till exempel som `%20` och semikolon som `%3B`.

**Svar**

Returnerar API-objektet för den aktuella [!UICONTROL DIL] instansen.

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
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
| `fn` |  -funktion | Den funktion som du vill köra efter att JSON har bearbetats av standardåteranropet som hanterar målpublicering. |

**Svar**

Returnerar ett API-objekt för den aktuella [!UICONTROL DIL] instansen.

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
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

Returnerar API-objektet för den aktuella [!UICONTROL DIL] instansen.

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
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

**Reserverade begärandenycklar**

Följande begärandenycklar är reserverade och kan inte skrivas över av den här metoden:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Svar**

Returnerar API-objektet för den aktuella DIL-instansen.

**Exempelkod**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Returnerar värdet för behållar-NSID för [!UICONTROL DIL] instansen. Användbar för felsökning och felsökning.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Funktionssignatur:** `dil.api.getContainerNSID: function () {}`

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
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
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

Returnerar partnernamnet för en [!UICONTROL DIL] instans. Användbar för felsökning och felsökning.

<!-- 

r_dil_get_partner.xml

 -->

**Funktionssignatur:** `dil.api.getPartner: function () {}`

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Returnerar den aktuella [!UICONTROL DIL] instansens tillstånd. Användbar för felsökning och felsökning.

<!-- 

r_dil_get_state.xml

 -->

**Funktionssignatur:** `dil.api.getState: function () {}`

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
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
   <td colname="col2"> <p>Mellan olika datapartners och Audience Manager. Partner x använder till exempel detta för att synkronisera ett användar-ID med partner y och sedan skicka det till Audience Manager. </p> <p> <p><b>Viktigt:</b>  Den här metoden är inaktuell. Använd metoden <code> idSyncByURL </code> för instansen av Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>När du redan känner till användar-ID:t och vill skicka det till Audience Manager. </p> <p> <p><b>Viktigt:</b>  Den här metoden är inaktuell. Använd metoden <code> idSyncByDataSource </code> för instansen av Adobe Experience Platform Identity Service. </p> </p> </td> 
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

`idSync` använder följande makron:

* **`%TIMESTAMP%`:**Skapar en tidsstämpel (i millisekunder). Används för cachebusting.
* **`%DID%`:**Infogar användarens Audience Manager-ID.
* **`%HTTP_PROTO%`:**Anger sidprotokollet (`http`eller`https`).

**Svar**

Båda funktionerna returneras `Successfully queued` om de lyckas. De returnerar i annat fall en felmeddelandesträng.

**Exempelkod**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
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
| `callback` |  -funktion | JavaScript-funktionen som körs av JSONP-återanropet. |

**Svar**

Returnerar API-objektet för den aktuella [!UICONTROL DIL] instansen.

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` är en boolesk parameter som styr hur [!UICONTROL DIL] anrop till [!UICONTROL Data Collection Servers (DCS)] och Akamai görs.

<!-- 

dil-secure-data-collection.xml

 -->

* När `secureDataCollection= true` (standard), [!UICONTROL DIL] sker alltid säkra HTTPS-anrop.

* När `secureDataCollection= false`detta inträffar [!UICONTROL DIL] gör antingen HTTP- eller HTTPS-anrop genom att följa det säkerhetsprotokoll som angetts av sidan.

>[!IMPORTANT]
>
>Ange `secureDataCollection= false` om du använder visitorAPI.js och [!UICONTROL DIL] på samma sida. Se kodexemplet nedan.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` är en boolesk true/false-parameter som styr hur webbläsaren begär resurser från andra domäner.

<!-- 

dil-use-cors-only.xml

 -->

**Översikt**

`useCORSOnly` är false som standard. Falskt innebär att webbläsaren kan utföra resurskontroller med CORS eller JSONP. Men försöker [!UICONTROL DIL] alltid begära resurser med CORS först. Den återgår till JSONP i äldre webbläsare som inte stöder CORS. Om du behöver tvinga webbläsaren att endast använda CORS, till exempel webbplatser som har höga säkerhetskrav, anges `useCORSOnly:true`.

**Kodexempel**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* Vi rekommenderar att du anger `useCORSOnly: true` bara när du är säker på att webbplatsens besökare har webbläsare som stöder den här funktionen.
>* När `useCORSOnly: true`detta inträffar [!UICONTROL DIL] inga ID-anrop från Internet Explorer version 9 eller tidigare.
>



## useImageRequest {#useimagerequest}

Ändrar begärandetypen till bild `<img>` från skript `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Funktionssignatur:** `useImageRequest: function () {}`

>[!NOTE]
>
>Du kan kedja andra API-anrop till den här metoden.

**Svar**

Returnerar ett API-objekt för den aktuella [!UICONTROL DIL] instansen.

**Exempelkod**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Namnkrav för nyckelvariabler](../features/traits/trait-key-name-requirements.md)
>* [Prefixkrav för nyckelvariabler](../features/traits/trait-variable-prefixes.md)
>* [Synkroniseringsfunktioner i Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)
>* [DIL skapa](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform Identity Service: AnvändCORSOnly](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [CORS-stöd i Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/reference/cors.html)

