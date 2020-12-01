---
description: Börja här om du vill ha information om hur du gör /event-anrop till DCS. Det här avsnittet innehåller information om anropssyntax, parametrar, formatering och ett exempel på en begäran.
seo-description: Börja här om du vill ha information om hur du gör /event-anrop till DCS. Det här avsnittet innehåller information om anropssyntax, parametrar, formatering och ett exempel på en begäran.
seo-title: Skicka data till DCS
solution: Audience Manager
title: Skicka data till DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 6%

---


# Skicka data till DCS {#send-data-to-the-dcs}

Börja här om du vill ha information om hur du gör `/event`-anrop till [!DNL DCS]. Det här avsnittet innehåller information om anropssyntax, parametrar, formatering och ett exempel på en begäran.

>[!NOTE]
>
>I koden och exemplen representerar *kursiv* en variabelplatshållare. Ersätt ett reellt värde för platshållaren när du skickar data till [!DNL DCS] med den här metoden.

## Anropssyntax {#dcs-call-syntax}

En enkel `URL`-sträng som skickar data till [!DNL DCS] använder syntaxen som visas nedan.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Du kan också skicka data till [!DNL DCS] med metoden `POST`. Anropssyntaxen beskrivs i [DCS API-metoder](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Anropsparametrar {#dcs-call-parameters}

Följande tabell definierar de grundläggande komponenterna i ett enkelt [!DNL DCS]-anrop.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komponent </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Denna del av samtalet innehåller: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Ditt domänalias som tilldelats av <span class="keyword"> Audience Manager</span> (t.ex. <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Måldomänen, som alltid är <code> demdex.net</code>. Se <a href="../../../reference/demdex-calls.md">Förstå anrop till Demdex-domänen</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Denna del av samtalet: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifierar samtalet som ett händelseanrop. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definierar början på URL-strängen som innehåller de data som du vill skicka till <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>En unik identifierare i nyckelvärdepar. </p> <p>Dessa nyckelvärdepar använder ett specifikt prefix för att identifiera den typ av data som du skickar till <span class="wintitle"> DCS</span>. Mer information finns i <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attribut som stöds för DCS API-anrop</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Ett variabelvärde som tillhör en uppsättning som definieras av en nyckel i nyckelvärdepar. </p> <p>När du arbetar med värden: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Omslut strängdata med dubbla citattecken (t.ex. <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Du kan skicka in flera tangenter på ett enda värde (t.ex. <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Se <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatera nyckelvärdepar i DCS-anrop</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Valfria svarsparametrar. </p> <p> Ingen av dessa krävs för att skicka data till <span class="wintitle"> DCS</span>. Om du vill att <span class="wintitle"> DCS</span> ska returnera ett svar måste du inkludera <code> d_rtbd=json</code> i din begäran. </p> <p>Se <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Nyckelvärdepar definierade</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Samtal {#dcs-sample-call}

I det här exemplet visas det fiktiva företaget [!DNL Acme, Inc.] som skickar data till [!DNL DCS] via ett [!DNL HTTP]-anrop. Observera att det här anropet innehåller de valfria parametrarna `d_dst=1`, `d_rtbd=json` och `d_cb=callback`. Dessa indikerar att [!DNL Acme] vill ta emot ett [!DNL JSON]-svar från [!DNL DCS] med en återanropsfunktion. Kom ihåg, detta är bara ett exempel. Klipp inte ut och klistra in koden.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Nästa steg {#dcs-next-steps}

Nu när du är bekant med att skicka data till [!DNL DCS] är det dags att titta på hur du hämtar data tillbaka från den och tolkar informationen. Se [Ta emot data från DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Förklaring av nyckelvärdespar](../../../reference/key-value-pairs-explained.md)

