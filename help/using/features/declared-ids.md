---
description: Hur deklarerade ID:n fungerar, konfigurera procedurer, kodexempel och variabler.
keywords: id sync
seo-description: Hur deklarerade ID:n fungerar, konfigurera procedurer, kodexempel och variabler.
seo-title: Deklarerade ID:n
solution: Audience Manager
title: Deklarerade ID:n
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 0%

---


# [!UICONTROL Declared IDs] {#declared-ids}

Hur du [!UICONTROL declared IDs] arbetar, konfigurerar procedurer, kodexempel och variabler.

## [!UICONTROL Declared ID] Målinriktning {#declared-id-targeting}

Utbyt och synkronisera användar-ID:n med [!DNL Audience Manager] enheter eller webbläsare som inte använder eller accepterar beständiga lagringsmekanismer, som till exempel från tredje part [!DNL cookies].

## Syfte med [!UICONTROL Declared ID] målinriktning {#declared-id-targeting-purpose}

Vissa webbläsare, och de flesta mobila enheter, accepterar inte tredjepartsprogram [!DNL cookies]. Detta gör det svårt att behålla information om webbplatsbesökare eller tilldela beständiga ID:n. För att lösa det här problemet [!DNL Audience Manager] använder [!UICONTROL DIL] för att låta dig logga in [!UICONTROL declared IDs] på ett händelseanrop. En användare [!UICONTROL declared ID] kan också fungera som ett universellt ID som gäller för samma användare för alla lösningar i [!DNL Experience Cloud]. I följande tabell beskrivs ID-målnings-/matchningsprocessen:

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
   <td colname="col2"> <p>För att fungera behöver du <span class="wintitle"> DIL </span> och <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service- </a> koden på sidan. <span class="wintitle"> DIL </span> hämtar <span class="wintitle"> deklarerade ID:n </span> från <code> setVisitorID </code> funktionen som tillhandahålls av <span class="keyword"> Adobe Experience Platform Identity Service </span> och skickar vidare dessa till <span class="keyword"> Audience Manager </span>. </p> </td> 
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

För att komma igång måste du konfigurera [!DNL Experience Cloud] ID-tjänsten och [!UICONTROL DIL] de sidor på webbplatsen som du vill använda för datainsamling. Se [Skapa](../dil/dil-class-overview/dil-create.md#dil-create) och [deklarera ID-variabler](../features/declared-ids.md#declared-id-variables)med DIL.

## Avanmäl samtal {#opt-out-calls}

Processen följer besökarnas preferenser för att avanmäla sig från [!UICONTROL declared ID] [!DNL Audience Manager] målgruppsanpassning på er webbplats. När [!DNL Audience Manager] tar emot en avanmälningsbegäran innehåller den [!DNL JSON] som returneras av [!DNL DCS] felkoden 171, med meddelandet `Encountered opt out tag`, i stället för [!DNL Audience Manager] användar-ID:t.

* [!DNL Audience Manager] kan skicka in en [!UICONTROL declared ID] avanmälan tillsammans med en [!DNL Audience Manager] i [!UICONTROL UUID] [!DNL URL].
* Avanmälningen lagras [!UICONTROL declared ID] per partner i [!UICONTROL Profile Cache Server ([!UICONTROL PCS]). Det finns ingen avanmälan på plattformsnivå med [!UICONTROL declared IDs]. Dessutom [!DNL Audience Manager] avmarkerar användaren från den specifika regionen på kanten (avanmälan omfattar inte flera [!DNL DCS] regioner).

Mer information om att välja bort datainsamling finns i [Dataintegritet](../overview/data-security-and-privacy/data-privacy.md) .

## [!UICONTROL Declared ID] Exempel på avanmälan {#opt-out-examples}

Du kan göra en [!UICONTROL declared ID] avanmälningsbegäran med `d_cid` - och `d_cid_ic` nyckelvärdepar. Gamla parametrar som `d_dpid` och `d_dpuuid` fungerar fortfarande, men betraktas som inaktuella. Se [CID ersätter DPID och DPUUID](../reference/cid.md). I exemplen *visar kursiv* en variabelplatshållare.

### Avanmäl dig med [!UICONTROL CID] och [!UICONTROL CID_IC]

En beskrivning och syntax finns i [URL-variabler och syntax för deklarerade ID:n](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avanmäl dig med </th> 
   <th colname="col2" class="entry"> Kodexempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ett dataleverantörs-ID och användar-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>En integrationskod och användar-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flera <code> d_cid </code> - och <code> d_cid_ic </code> nyckelvärdepar. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Avanmäl dig med [!UICONTROL DPID], [!UICONTROL DPUUID]och [!UICONTROL UUID] (inaktuellt)

Dessa metoder fungerar fortfarande men anses vara föråldrade. Denna information tillhandahålls för äldre syften och referens. Äldre avanmälningar inkluderar:

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avanmäl dig (borttagen) </th> 
   <th colname="col2" class="entry"> Kodexempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> endast </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avanmälan på partnernivå </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>En avanmälan på partnernivå lagras för den senaste mappningen av det här <code> dpid </code> +- <code> dpuuid </code> paret till ett AAM UUID. Om det inte finns någon befintlig mappning kontrollerar Audience Manager om begäran innehåller ett AAM UUID i cookien, och om så är fallet använder den för lagring av avanmälan. I annat fall genererar Audience Manager ett nytt AAM UUID och lagrar avanmälan under det. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> och explicit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> har alltid företräde. Om kombinationen <code> dpid </code> + <code> dpuuid </code> mappas till ett annat AAM UUID, lagras avanmälningen under det AAM UUID som skickas i begäran ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabler och syntax för [!UICONTROL Declared IDs] {#variables-and-syntax}

I följande tabell visas nyckelvärdepar som skickas i ID:t för din [!DNL Audience Manager] dataleverantör och användar-ID eller integreringskoder, om sådana används. Obs! *Kursiv* anger en variabelplatshållare. Blanksteg har lagts till för att göra dem enklare att läsa.

I varje nyckelvärdepar:

* Symbolen `=` skiljer nyckeln från dess relaterade värden.
* Värdena skiljs åt av det icke utskrivbara [!DNL ASCII] tecknet `%01` .

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
   <td colname="col2"> <p>Innehåller ett DataProvider ID och ett associerat unikt användar-ID i ett enda nyckelvärdepar. <code> d_cid </code> ersätter <code> d_dpid </code> och <code> d_dpuuid </code>, som betraktas som inaktuella, men fortfarande stöds. Se <a href="../reference/cid.md"> CID ersätter DPID och DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Innehåller en integreringskod och ett associerat unikt användar-ID i ett enda nyckelvärdepar. <code> d_cid_ic </code> ersätts <code> d_dpid </code> och <code> d_dpuuid </code>, som är borttagna, men fortfarande stöds. Se <a href="../reference/cid.md"> CID ersätter DPID och DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempelhändelseanrop {#sample-event-calls}

Med tanke på dessa nyckelvärdepar och deras obligatoriska syntax gör du händelseanrop enligt nedan.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Evenemangsanropet innehåller </th> 
   <th colname="col2" class="entry"> Kodexempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ett dataleverantörs-ID och användar-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>En integrationskod och användar-ID. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flera <code> d_cid </code> - och <code> d_cid_ic </code> nyckelvärdepar. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variabler {#declared-id-variables}

Beskriver de konfigurationsvariabler som används för att skicka [!UICONTROL declared IDs] vidare [!UICONTROL DIL] till [!DNL Audience Manager.]

## [!UICONTROL DIL] använder [!DNL Adobe Experience Platform Identity Service] till Pass [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

När du använder med [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)behöver du inte längre skicka in [!UICONTROL declared IDs] de borttagna `dpid` och `dpuuid` variablerna. I stället förlitar sig de aktuella versionerna på [!UICONTROL DIL] funktionen `visitorService` för att hämta [!UICONTROL declared IDs] från `setCustomerIDs` funktionen i [!UICONTROL Adobe Experience Platform Identity Service]. Mer information finns i [Kund-ID och autentiseringstillstånd](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Du ringer `visitorService` in `DIL.create` enligt nedan.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

I nyckelvärdepar `namespace` är det ditt `MCORG` [!DNL Experience Cloud] organisations-ID. Om du inte har det här ID:t kan du hitta det i [!UICONTROL Administration] avsnittet på [!DNL Experience Cloud] instrumentpanelen. Du behöver administratörsbehörighet för att kunna visa den här instrumentpanelen. Se [Administration: Bastjänster](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Föråldrade funktioner {#deprecated-functions}

Med de senaste versionerna av [!UICONTROL DIL] (6.2+) behöver du inte använda dessa nyckelvärdepar för att skicka [!UICONTROL declared IDs]. Det beror på att [!UICONTROL DIL] nu är beroende av den `visitorService` funktion som visas i kodexemplet ovan. Den här funktionen kommer [!UICONTROL declared IDs] från [!UICONTROL Adobe Experience Platform Identity Service]. Men vi refererar till dessa variabler här av historiska och äldre skäl. I koden nedan finns ett exempel på hur du konfigurerar `DIL.create` för att hämta ett [!UICONTROL declared ID] från [!UICONTROL Visitor ID Service].
I följande tabell beskrivs de äldre variablerna som används av `declaredId` objektet:

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

### [!UICONTROL DPID] och [!UICONTROL DPUUID]

[!DNL Audience Manager] jämför och matchar det kombinerade `DPID` och `DPUUID` ett motsvarande användar-ID i vårt system. Om det inte finns något ID skapar [!DNL Audience Manager] ett nytt användar-ID och synkroniserar det med `DPID/DPUUID` kombinationen. När [!DNL Audience Manager] matchar eller skapar ett användar-ID ( `UUID`) returnerar det ID:t i [!DNL JSON] svaret på [!DNL cookie] klientens domän (första part [!DNL cookie]) eller annan lokal lagring.

Anropa den här funktionen när du använder [!UICONTROL DIL] v6.1 eller tidigare. Den här funktionen har dock ersatts med den nya versionen som kommer [!UICONTROL declared IDs] från [!DNL Adobe Experience Platform Identity Service].

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
>Du måste programmässigt utveckla koden som tillhandahåller ID-värden för `d_dpuuid` och `d_dpid` nycklar.

### Skicka ID:n efter [!UICONTROL DIL] förekomster

>[!NOTE]
>
>Om du ringer ett [!DNL API] samtal med en annan `declaredID` kombination används den nya kombinationen endast för det samtalet. Ytterligare vanliga händelseanrop använder den ursprungliga `DIL.create``declaredID` kombinationen.

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

Svaret returnerar Audience Manager-ID (t.ex. `UUID`) som är skrivet till en cookie från en annan leverantör i siddomänen.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Ring inte Target och avanmäl dig {#do-not-target}

Processen följer besökarnas preferenser för att avanmäla sig från [!UICONTROL declared ID] [!DNL Audience Manager] målgruppsanpassning på er webbplats. När [!DNL Audience Manager] tar emot en avanmälningsbegäran [!DNL DCS] returneras ett tomt [!DNL JSON] objekt i stället för [!DNL Audience Manager] användar-ID.

>[!MORELIKETHIS]
>
>* [CID ersätter DPID och DPUUID](../reference/cid.md)

