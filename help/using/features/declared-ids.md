---
description: Hur deklarerade ID:n fungerar, konfigurera procedurer, kodexempel och variabler.
keywords: id-synkronisering
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: Deklarerade ID:n
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Hur [!UICONTROL declared IDs] arbeta, konfigurera procedurer, kodexempel och variabler.

## [!UICONTROL Declared ID] Målinriktning {#declared-id-targeting}

Exchange and synchronize user IDs with [!DNL Audience Manager] från enheter eller webbläsare som inte använder eller accepterar beständiga lagringsmekanismer, t.ex. [!DNL cookies].

## Syfte med [!UICONTROL Declared ID] Målinriktning {#declared-id-targeting-purpose}

Vissa webbläsare, och de flesta mobila enheter, accepterar inte tredjepartsprogram [!DNL cookies]. Detta gör det svårt att behålla information om webbplatsbesökare eller tilldela beständiga ID:n. För att lösa problemet [!DNL Audience Manager] använder [!UICONTROL DIL] så att du kan skicka in [!UICONTROL declared IDs] på ett eventsamtal. Dessutom har [!UICONTROL declared ID] kan fungera som ett universellt ID som gäller för samma användare för alla lösningar i [!DNL Experience Cloud]. I följande tabell beskrivs ID-målnings-/matchningsprocessen:

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
   <td colname="col2"> <p>För att kunna arbeta behöver du <span class="wintitle"> DIL </span> och <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a> på sidan. <span class="wintitle"> DIL </span> hämtar <span class="wintitle"> deklarerade ID:n </span> från <code> setVisitorID </code> av <span class="keyword"> Adobe Experience Platform Identity Service </span> och skickar vidare <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Matcha ID</b> </td> 
   <td colname="col2"> <p>Audience Manager försöker matcha klient- och besökar-ID med ett motsvarande ID i vårt system. Om det inte finns något matchande ID skapar Audience Manager ett nytt ID och associerar det med klient- och besökar-ID:t. </p> <p> <p>Obs! Den senaste mappningen används om ditt ID mappar till mer än ett Audience Manager-ID. </p> </p> </td> 
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

För att komma igång måste du konfigurera [!DNL Experience Cloud] ID-tjänst och [!UICONTROL DIL] på de sidor på webbplatsen som du vill använda för datainsamling. Se [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) och [Deklarerade ID-variabler](../features/declared-ids.md#declared-id-variables).

## Avanmäl samtal {#opt-out-calls}

The [!UICONTROL declared ID] processen följer besökarens inställningar för att avanmäla sig från [!DNL Audience Manager] för er webbplats. När [!DNL Audience Manager] tar emot en begäran om avanmälan, [!DNL JSON] returneras av [!DNL DCS] innehåller felkoden 171, med meddelandet `Encountered opt out tag`i stället för [!DNL Audience Manager] användar-ID.

* [!DNL Audience Manager] kan skicka in en [!UICONTROL declared ID] avanmäla dig tillsammans med en [!DNL Audience Manager] [!UICONTROL UUID] i [!DNL URL].
* The [!UICONTROL declared ID] avanmälan sparas i [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) per partner. Det finns ingen avanmälan på plattformsnivå som använder [!UICONTROL declared IDs]. Dessutom [!DNL Audience Manager] väljer att användaren ska vara borta från den specifika regionen på kanten (avanmälan korsar inte) [!DNL DCS] regioner).

Se [Dataintegritet](../overview/data-security-and-privacy/data-privacy.md) om du vill ha mer information om att avanmäla dig från datainsamling.

## [!UICONTROL Declared ID] Exempel på avanmälan {#opt-out-examples}

Du kan skapa en [!UICONTROL declared ID] avanmälningsbegäranden med `d_cid` och `d_cid_ic` nyckelvärdepar. Gamla parametrar som `d_dpid` och `d_dpuuid` fungerar fortfarande, men betraktas som föråldrade. Se [CID ersätter DPID och DPUUID](../reference/cid.md). I exemplen visar *kursiv stil* platshållaren för en variabel.

### Opt-out with [!UICONTROL CID] och [!UICONTROL CID_IC]

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

### Opt-out with [!UICONTROL DPID], [!UICONTROL DPUUID]och [!UICONTROL UUID] (Föråldrat)

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>En avanmälan på partnernivå sparas för den senaste mappningen av detta <code> dpid </code> + <code> dpuuid </code> till en AAM UUID. Om det inte finns någon befintlig mappning kontrollerar Audience Manager om begäran innehåller en AAM UUID i cookien, och om den gör det använder den för lagring av avanmälan. I annat fall genererar Audience Manager ett nytt AAM UUID och lagrar avanmälan under det. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> och explicit <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> har alltid företräde. Om <code> dpid </code> + <code> dpuuid </code> kombinationen mappas till en annan AAM UUID, lagras avanmälan under AAM UUID som skickas i begäran ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabler och syntax för [!UICONTROL Declared IDs] {#variables-and-syntax}

I följande tabell visas nyckelvärdepar som skickas i [!DNL Audience Manager] DataProvider ID och användar-ID eller integreringskoder, om sådana används. Obs! *kursiv* används för att ange en variabelplatshållare. Blanksteg har lagts till för att göra dem enklare att läsa.

I varje nyckelvärdepar:

* The `=` används för att skilja tangenten från dess relaterade värden.
* De ej utskrivbara [!DNL ASCII] tecken `%01` avgränsar värdena.

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
   <td colname="col2"> <p>Innehåller ett DataProvider ID och ett associerat unikt användar-ID i ett enda nyckelvärdepar. <code> d_cid </code> Ersätter <code> d_dpid </code> och <code> d_dpuuid </code>, som betraktas som inaktuella, men fortfarande stöds. Se <a href="../reference/cid.md">CID ersätter DPID och DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Innehåller en integreringskod och ett associerat unikt användar-ID i ett enda nyckelvärdepar. <code> d_cid_ic </code> Ersätter <code> d_dpid </code> och <code> d_dpuuid </code>, som är inaktuella, men fortfarande stöds. Se <a href="../reference/cid.md">CID ersätter DPID och DPUUID </a>. </p> </td> 
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

## [!UICONTROL Declared ID] Variabler {#declared-id-variables}

Beskriver de konfigurationsvariabler som används för att skicka [!UICONTROL declared IDs] via [!UICONTROL DIL] till [!DNL Audience Manager.]

## [!UICONTROL DIL] använder [!DNL Adobe Experience Platform Identity Service] till pass [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Vid användning med [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html)behöver du inte längre skicka in [!UICONTROL declared IDs] med den borttagna `dpid` och `dpuuid` variabler. I stället är de aktuella versionerna av [!UICONTROL DIL] använder `visitorService` funktion för att hämta [!UICONTROL declared IDs] från `setCustomerIDs` funktionen i [!UICONTROL Adobe Experience Platform Identity Service]. Mer information finns i [Kund-ID och autentiseringstillstånd](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). Du skulle ringa `visitorService` in `DIL.create` enligt nedan.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

I `namespace` nyckelvärdepar, `MCORG` är din [!DNL Experience Cloud] Organisations-ID. Om du inte har detta ID kan du hitta det i [!UICONTROL Administration] i [!DNL Experience Cloud] kontrollpanel. Du behöver administratörsbehörighet för att kunna visa den här instrumentpanelen. Se [Administration: Centrala tjänster](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## Föråldrade funktioner {#deprecated-functions}

Med de senaste versionerna av [!UICONTROL DIL] (6.2+) behöver du inte använda dessa nyckelvärdepar för att skicka [!UICONTROL declared IDs]. Det är för att [!UICONTROL DIL] använder `visitorService` som visas i kodexemplet ovan. Den här funktionen får [!UICONTROL declared IDs] från [!UICONTROL Adobe Experience Platform Identity Service]. Men vi refererar till dessa variabler här av historiska och äldre skäl. Se koden nedan för ett exempel på hur du konfigurerar `DIL.create` för att få [!UICONTROL declared ID] från [!UICONTROL Visitor ID Service].
I följande tabell beskrivs de äldre variablerna som används i `declaredId` objekt:

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

[!DNL Audience Manager] jämför och matchar de kombinerade `DPID` och `DPUUID` till ett motsvarande användar-ID i vårt system. Om ett ID inte finns, [!DNL Audience Manager] skapar ett nytt användar-ID och synkroniserar det med `DPID/DPUUID` kombinationen. En gång [!DNL Audience Manager] matchar eller skapar ett användar-ID ( `UUID`) returneras det ID som finns i [!DNL JSON] svar på [!DNL cookie] i klientens domän (första part [!DNL cookie]) eller annan lokal lagring.

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
>Du måste programmässigt utveckla koden som tillhandahåller ID-värdena för `d_dpuuid` och `d_dpid` nycklar.

### Skicka ID efter [!UICONTROL DIL] Instansierar

>[!NOTE]
>
>Om du skapar en [!DNL API] samtal med en annan `declaredID` den nya kombinationen används endast för det anropet. Ytterligare vanliga händelseanrop använder originalet `DIL.create`  `declaredID` kombinationen.

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

Svaret returnerar Audience Manager-ID (t.ex. `UUID`) som skrivs till en cookie från en annan tillverkare i siddomänen.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Anrop för inte mål och avanmäl {#do-not-target}

The [!UICONTROL declared ID] processen följer besökarens inställningar för att avanmäla sig från [!DNL Audience Manager] för er webbplats. När [!DNL Audience Manager] tar emot en begäran om avanmälan, [!DNL DCS] returnerar en tom [!DNL JSON] i stället för [!DNL Audience Manager] användar-ID.

>[!MORELIKETHIS]
>
>* [CID ersätter DPID och DPUUID](../reference/cid.md)

