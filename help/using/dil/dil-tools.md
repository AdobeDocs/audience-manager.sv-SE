---
description: Beskriver metoder i namnutrymmet DIL.tools. De här verktygen hjälper dig att utföra specifika uppgifter.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL Tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---

# DIL Tools

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av tillägget [!DNL Data Integration Library (DIL)] och [!DNL DIL].
>
>Befintliga kunder kan fortsätta använda sin [!DNL DIL]-implementering. Adobe kommer dock inte att utveckla [!DNL DIL] efter den här punkten. Kunder uppmuntras att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) för sin långsiktiga datainsamlingsstrategi.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) i stället.

Beskriver metoder i namnområdet `DIL.tools`. De här verktygen hjälper dig att utföra specifika uppgifter.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Returnerar söktermer som används för att nå den aktuella sidan.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Syfte med `getSearchReferrer`

I DIL returnerar `getSearchReferrer` sökresultat (namn och nyckelord) som används för att nå din webbplats. Du kan skicka specifika söktermer till den här funktionen eller låta den söka efter de sökmotorer som stöds ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google] och [!DNL Yahoo]) mot `document.referrer` som standard.

### Funktionssignatur

Funktionssignatur: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Funktionsparametrar

`getSearchReferrer` accepterar:

* *`{string}`*: *(Valfritt)* En sträng som innehåller sökwebbadressen (använder `document.referrer` om det är odefinierat).
* *`{object}`*: *(Valfritt)* Ett objekt som innehåller konfigurationen för `hostPattern`, `queryParam` eller `queryPattern`.

Och returnerar:

* `{object}` Ett objekt som innehåller giltiga namn och nyckelord.

### Exempel

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Söktyp </th> 
   <th> Beskrivning </th> 
   <th> Exempel på kod </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Standardsökning</td> 
   <td> Returnerar söktermer som används av sökmotorerna AOL, Ask, Bing, Google och Yahoo. </td> 
   <td>
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Ange en anpassad URL</td> 
   <td>Returnerar sökreferenten baserat på en anpassad URL.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>Matcha URL-värdnamn med en anpassad region</b></td> 
   <td> Ange en anpassad region som matchar värdnamnet för den refererande URL:en. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Matcha sökmönster med en anpassad region</b> </td> 
   <td> Skicka in en anpassad region för att utföra en anpassad sökning. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Disassemblerar en Uniform Resource Identifier ( [!DNL URI]) till dess beståndsdelar: `hash`, `host`, `href`, `pathname`, `protocol`, `search` och `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Funktionssignatur: `DIL.tools.decomposeURI`

### Funktionsparametrar

`decomposeURI` accepterar:

* *`uri {string}`*: *(Valfritt)* En sträng som innehåller URI:n. Standardvärdet är `document.location.href` om inget anges.

Och returnerar:

* *`{object}`*: Ett objekt som innehåller giltiga namn och nyckelord.

### Exempelkod


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTags

Söker efter specifikt innehåll som definieras i metataggar på en webbsida och returnerar data i ett objekt.

<!-- 

r_dil_get_metatags.xml

 -->

### Funktionssignatur

Funktionssignatur: `DIL.tools.getMetaTags( 1 or more parameters)`

### Funktionsparametrar

`getMetaTags` accepterar en eller flera namnparametrar (strängtyp) att söka efter. Returnerar ett objekt som består av nyckelvärdepar.

### Exempelkod

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
