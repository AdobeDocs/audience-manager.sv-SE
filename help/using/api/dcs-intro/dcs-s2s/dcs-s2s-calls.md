---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: Göra DCS API-anrop från server till server
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: Anropa syntax, till exempel och parametrar när du gör DCS API-anrop från server till server
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---

# Göra DCS API-anrop från server till server {#making-server-to-server-dcs-api-calls}

Anrop kräver värdnamnet för den regionala DCS-servern och användar-ID:t. Om du inte har rätt användar- och region-id:n läser du [Hämta användar-ID:n och regioner från ett DCS-svar](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) och/eller [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). När du har användar-ID:n och region-ID:n kan du göra server-till-server-anrop till DCS. I det här avsnittet finns syntax och exempel.

>[!NOTE]
>
>I koden och exemplen representerar *italics* en variabelplatshållare. Ersätt ett reellt värde för platshållaren när du anropar servern till [!DNL DCS].

## Samtalssyntax och exempel {#call-syntax-example}

En grundläggande server-till-server-begäran som skickar data till [!DNL DCS] använder syntaxen som visas nedan.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Ett samplingsanrop ser ut ungefär som i följande exempel.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Samtalsparametrar {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Denna del av samtalet innehåller: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Ditt domänalias som tilldelats av <span class="keyword"> Audience Manager</span> (t.ex. <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Måldomänen, som alltid är <i><code> demdex.net</code></i>. Se <a href="../../../reference/demdex-calls.md"> Förstå anrop till Demdex-domänen </a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Den http-huvudvärdparameter som visar namnet på den regionala <span class="wintitle"> DCS</span> -servern. Värdnamnet är kopplat till ett region-ID, vilket är orsaken till att du behöver det här innan du gör dessa typer av samtal. Se <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> ID:n för DCS-region, platser och värdnamn</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Denna del av samtalet: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifierar samtalet som ett händelseanrop. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definierar början på URL-strängen som innehåller data som du vill skicka till DCS. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Detta är den unika användar-ID-nyckeln som innehåller användar-ID:t <span class="keyword"> Audience Manager</span> i ett nyckelvärdepar. </p> <p>Använd <code><i>d_uuid</i></code> om du skickar användar-ID:t <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Detta är den unika användar-ID-nyckeln som innehåller användar-ID:t <span class="keyword"> Experience Cloud</span> i ett nyckelvärdepar. Se även <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Hämta användar-ID från ID-tjänstcookie</a>. </p> <p>Använd <i><code> d_mid</code></i> om du skickar ett <span class="keyword"> Experience Cloud</span> ID som hämtats från <span class="keyword"> Experience Cloud </span> ID-tjänsten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Valfria svarsparametrar. </p> <p> Ingen av dessa krävs för att skicka data till <span class="wintitle"> DCS</span>. Om du vill att <span class="wintitle"> DCS</span> ska returnera ett svar måste du inkludera <i><code> d_rtbd=json</code></i> i din begäran. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempelsvar {#sample-response}

Se [Ta emot data från DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
