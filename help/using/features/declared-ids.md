---
description: Hur deklarerade ID:n fungerar, konfigurera procedurer, kodexempel och variabler.
keywords: id sync
seo-description: Hur deklarerade ID:n fungerar, konfigurera procedurer, kodexempel och variabler.
seo-title: Deklarerade ID:n
solution: Audience Manager
title: Deklarerade ID:n
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
translation-type: tm+mt
source-git-commit: 29708d5fc528ac9da08f4c5a7f2bcaa11b240d8b
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 9%

---


# [!UICONTROL Declared IDs] {#declared-ids}

Hur [!UICONTROL declared IDs] fungerar, ställer in procedurer, kodexempel och variabler.

## [!UICONTROL Declared ID] Målinriktning  {#declared-id-targeting}

Utbyt och synkronisera användar-ID:n med [!DNL Audience Manager] från enheter eller webbläsare som inte använder eller accepterar beständiga lagringsmekanismer, till exempel [!DNL cookies] från tredje part.

## Syfte med [!UICONTROL Declared ID] {#declared-id-targeting-purpose}

Vissa webbläsare, och de flesta mobila enheter, accepterar inte [!DNL cookies] från tredje part. Detta gör det svårt att behålla information om webbplatsbesökare eller tilldela beständiga ID:n. För att lösa det här problemet använder [!DNL Audience Manager] [!UICONTROL DIL] så att du kan skicka [!UICONTROL declared IDs] i ett händelseanrop. Dessutom kan en [!UICONTROL declared ID] fungera som ett universellt ID som gäller för samma användare i alla lösningar i [!DNL Experience Cloud]. I följande tabell beskrivs ID-målnings-/matchningsprocessen:

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Process </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Händelseanrop</b> </td> 
   <td colname="col2"> <p>För att fungera behöver du <span class="wintitle"> DIL </span> och <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a> på sidan. <span class="wintitle"> DIL  </span> får  <span class="wintitle"> deklarerade ID:n  </span> från  <code> setVisitorID </code> funktionen som tillhandahålls av  <span class="keyword"> Adobe Experience Platform identitetstjänst  </span> och skickar dem vidare till  <span class="keyword"> Audience Manager  </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Matcha ID</b> </td> 
   <td colname="col2"> <p>Audience Manager försöker matcha klient- och besökar-ID med ett motsvarande ID i vårt system. Om det inte finns något matchande ID skapar Audience Manager ett nytt ID och associerar det med klient- och besökar-ID:t. </p> <p> <p>Obs!  Den senaste mappningen används om ditt ID mappar till mer än ett Audience Manager-ID. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Returnr</b> </td> 
   <td colname="col2"> <p>Audience Manager skriver sitt synkroniserade ID till en cookie (eller annat adresserbart lagringsutrymme) i klientdomänen eller -programmet. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Efterföljande händelseanrop</b> </td>
   <td colname="col2"> <p>Ytterligare händelseanrop läser Audience Manager-ID från klientens domän och skickar det till Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

För att komma igång måste du konfigurera ID-tjänsten [!DNL Experience Cloud] och [!UICONTROL DIL] för de sidor på webbplatsen som du vill använda för datainsamling. Se [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) och [Deklarerade ID-variabler](../features/declared-ids.md#declared-id-variables).

## Anrop till avanmälan {#opt-out-calls}

[!UICONTROL declared ID]-processen följer besökarens inställningar för att avanmäla [!DNL Audience Manager]-mål på din webbplats. När [!DNL Audience Manager] tar emot en avanmälningsbegäran innehåller [!DNL JSON] som returneras av [!DNL DCS] felkoden 171, med meddelandet `Encountered opt out tag`, i stället för användar-ID:t för [!DNL Audience Manager].

* [!DNL Audience Manager] kan skicka in en  [!UICONTROL declared ID] avanmälan tillsammans med en  [!DNL Audience Manager] [!UICONTROL UUID] i  [!DNL URL].
* Avanmälningen för [!UICONTROL declared ID] sparas i [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) per partner. Det finns ingen avanmälan på plattformsnivå med [!UICONTROL declared IDs]. Dessutom avmarkerar [!DNL Audience Manager] användaren från den specifika regionen på kanten (avanmälan korsar inte [!DNL DCS]-regioner).

Mer information om att avanmäla dig från datainsamling finns i [Dataintegritet](../overview/data-security-and-privacy/data-privacy.md).

## [!UICONTROL Declared ID] Exempel på avanmälan  {#opt-out-examples}

Du kan göra en [!UICONTROL declared ID]-avanmälningsbegäran med nyckelvärdepar för `d_cid` och `d_cid_ic`. Gamla parametrar som `d_dpid` och `d_dpuuid` fungerar fortfarande, men betraktas som föråldrade. Se [CID ersätter DPID och DPUUID](../reference/cid.md). I exemplen visar *kursiv stil* platshållaren för en variabel.

### Opt-Outs With [!UICONTROL CID] and [!UICONTROL CID_IC]

En beskrivning och syntax finns i [URL-variabler och syntax för deklarerade ID:n](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avanmälan med </th> 
   <th colname="col2" class="entry"> Exempel på kod </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ett dataleverantörs-ID och användar-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>En integreringskod och användar-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flera <code> d_cid </code> och <code> d_cid_ic </code> nyckelvärdepar. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-Outs With [!UICONTROL DPID], [!UICONTROL DPUUID], and [!UICONTROL UUID] (Deprecated)

Dessa metoder fungerar fortfarande men anses vara föråldrade. Denna information tillhandahålls för äldre syften och referens. Äldre avanmälningar inkluderar:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avanmäl dig (borttagen) </th> 
   <th colname="col2" class="entry"> Exempel på kod </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> endast </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avanmälan på partnernivå </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>En avanmälan på partnernivå sparas för den senaste mappningen av det här <code> dpid </code> + <code> dpuuid </code>-paret till ett AAM UUID. Om det inte finns någon befintlig mappning kontrollerar Audience Manager om begäran innehåller en AAM UUID i cookien, och om den gör det använder den för lagring av avanmälan. I annat fall genererar Audience Manager ett nytt AAM UUID och lagrar avanmälan under det. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> och explicit  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> har alltid företräde. Om kombinationen <code> dpid </code> + <code> dpuuid </code> mappar till ett annat AAM UUID, lagras avanmälan under det AAM UUID som skickades i begäran ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabler och syntax för [!UICONTROL Declared IDs] {#variables-and-syntax}

I följande tabell visas nyckelvärdepar som skickas i [!DNL Audience Manager]-dataleverantörs-ID och användar-ID eller integreringskoder, om sådana används. Obs! *kursiv* anger en variabelplatshållare. Blanksteg har lagts till för att göra dem enklare att läsa.

I varje nyckelvärdepar:

* Symbolen `=` skiljer nyckeln från dess relaterade värden.
* Värdet som inte skrivs ut är [!DNL ASCII]-tecknet `%01`.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Innehåller ett DataProvider ID och ett associerat unikt användar-ID i ett enda nyckelvärdepar. <code> d_cid </code> ersätter  <code> d_dpid </code> och  <code> d_dpuuid </code>, som betraktas som inaktuella, men fortfarande stöds. Se <a href="../reference/cid.md">CID ersätter DPID och DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Innehåller en integreringskod och ett associerat unikt användar-ID i ett enda nyckelvärdepar. <code> d_cid_ic </code> ersätter  <code> d_dpid </code> och  <code> d_dpuuid </code>, som är borttagna, men fortfarande stöds. Se <a href="../reference/cid.md">CID ersätter DPID och DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempelhändelseanrop {#sample-event-calls}

Med tanke på dessa nyckelvärdepar och deras obligatoriska syntax gör du händelseanrop enligt nedan.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Evenemangsanropet innehåller </th> 
   <th colname="col2" class="entry"> Exempel på kod </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ett dataleverantörs-ID och användar-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>En integreringskod och användar-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flera <code> d_cid </code> och <code> d_cid_ic </code> nyckelvärdepar. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variabler  {#declared-id-variables}

Beskriver de konfigurationsvariabler som används för att skicka [!UICONTROL declared IDs] till [!UICONTROL DIL] till [!DNL Audience Manager.]

## [!UICONTROL DIL] använder  [!DNL Adobe Experience Platform Identity Service] till Pass  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

När du använder med [Adobe Experience Platform identitetstjänst](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html) behöver du inte längre skicka in [!UICONTROL declared IDs] med de inaktuella variablerna `dpid` och `dpuuid`. I stället förlitar sig de aktuella versionerna av [!UICONTROL DIL] på funktionen `visitorService` för att hämta [!UICONTROL declared IDs] från funktionen `setCustomerIDs` i [!UICONTROL Adobe Experience Platform Identity Service]. Mer information finns i [Kund-ID och autentiseringstillstånd](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Du anropar `visitorService` i `DIL.create` enligt nedan.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

I `namespace`-nyckelvärdepar är `MCORG` ditt [!DNL Experience Cloud] organisations-ID. Om du inte har det här ID:t kan du hitta det i [!UICONTROL Administration]-avsnittet på kontrollpanelen [!DNL Experience Cloud]. Du behöver administratörsbehörighet för att kunna visa den här instrumentpanelen. Se [Administration: Huvudtjänster](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Föråldrade funktioner {#deprecated-functions}

Med de senaste versionerna av [!UICONTROL DIL] (6.2+) behöver du inte använda dessa nyckelvärdepar för att skicka [!UICONTROL declared IDs]. Det beror på att [!UICONTROL DIL] nu förlitar sig på funktionen `visitorService` som visas i kodexemplet ovan. Den här funktionen hämtar [!UICONTROL declared IDs] från [!UICONTROL Adobe Experience Platform Identity Service]. Men vi refererar till dessa variabler här av historiska och äldre skäl. I koden nedan finns ett exempel på hur du konfigurerar `DIL.create` för att hämta en [!UICONTROL declared ID] från [!UICONTROL Visitor ID Service].
I följande tabell beskrivs de äldre variablerna som används av objektet `declaredId`:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namn </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Sträng </td> 
   <td colname="col3"> <p>Datapartnerns ID tilldelat av Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Sträng </td> 
   <td colname="col3"> <p>Dataleverantörens unika ID för användaren. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] och  [!UICONTROL DPUUID]

[!DNL Audience Manager] jämför och matchar det kombinerade  `DPID` och  `DPUUID` ett motsvarande användar-ID i vårt system. Om det inte finns något ID skapar [!DNL Audience Manager] ett nytt användar-ID och synkroniserar det med kombinationen `DPID/DPUUID`. När [!DNL Audience Manager] matchar eller skapar ett användar-ID (`UUID`) returnerar det ID:t i [!DNL JSON]-svaret på [!DNL cookie] i klientens domän (first-party [!DNL cookie]) eller annan lokal lagring.

Anropa den här funktionen när du använder [!UICONTROL DIL] v6.1 eller tidigare. Den här funktionen har ersatts med den nya versionen som får [!UICONTROL declared IDs] från [!DNL Adobe Experience Platform Identity Service].

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>Du måste programmässigt utveckla koden som tillhandahåller ID-värden för tangenterna `d_dpuuid` och `d_dpid`.

### Skicka ID:n efter [!UICONTROL DIL]-instanser

>[!NOTE]
>
>Om du gör ett [!DNL API]-anrop med en annan `declaredID`-kombination används den nya kombinationen endast för det anropet. Ytterligare reguljära händelseanrop använder den ursprungliga kombinationen `DIL.create` `declaredID`.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exempel på begäran/svar {#request-response-examples}

Begäran skickar en DataProvider och ett användar-ID till [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

Svaret returnerar Audience Manager-ID (t.ex. `UUID`) som är skrivet till en cookie för första part i siddomänen.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Använd inte anrop för mål och avanmälan {#do-not-target}

[!UICONTROL declared ID]-processen följer besökarens inställningar för att avanmäla [!DNL Audience Manager]-mål på din webbplats. När [!DNL Audience Manager] tar emot en avanmälningsbegäran returnerar [!DNL DCS] ett tomt [!DNL JSON]-objekt i stället för användar-ID:t för [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [CID ersätter DPID och DPUUID](../reference/cid.md)

