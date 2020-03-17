---
description: Beskriver metoder i namnutrymmet DIL.tools. De här verktygen hjälper dig att utföra specifika uppgifter.
seo-description: Beskriver metoder i namnutrymmet DIL.tools. De här verktygen hjälper dig att utföra specifika uppgifter.
seo-title: DIL Tools
solution: Audience Manager
title: DIL Tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# DIL Tools

Beskriver metoder i `DIL.tools` namnutrymmet. De här verktygen hjälper dig att utföra specifika uppgifter.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Returnerar söktermer som används för att nå den aktuella sidan.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Syfte med `getSearchReferrer`

I DIL `getSearchReferrer` returneras sökresultat (namn och nyckelord) som används för att nå din webbplats. Du kan skicka specifika söktermer till den här funktionen eller låta den söka efter de sökmotorer som stöds ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google]och [!DNL Yahoo]) `document.referrer` som standard.

### Funktionssignatur

Funktionssignatur: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Funktionsparametrar

`getSearchReferrer` godkänner:

* *`{string}`*: *(Valfritt)* En sträng som innehåller sökwebbadressen (används `document.referrer` om det är odefinierat).
* *`{object}`*: *(Valfritt)* Ett objekt som innehåller konfigurationen för `hostPattern`, `queryParam`eller `queryPattern`.

Och returnerar:

* `{object}` Ett objekt som innehåller giltiga namn och nyckelord.

### Exempel

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Söktyp </th> 
   <th> Beskrivning </th> 
   <th> Kodexempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Standardsökning</td> 
   <td> Returnerar söktermer som används av sökmotorerna AOL, Ask, Bing, Google och Yahoo. </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
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
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Matcha sökmönster med en anpassad region</b> </td> 
   <td> Skicka in en anpassad region för att utföra en anpassad sökning. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Disassemblerar en Uniform Resource Identifier ( [!DNL URI]) till dess beståndsdelar: `hash`, `host`, `href`, `pathname`, `protocol`, `search`och `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Funktionssignatur: `DIL.tools.decomposeURI`

### Funktionsparametrar

`decomposeURI` godkänner:

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

`getMetaTags` använder en eller flera namnparametrar (strängtyp) som ska sökas efter. Returnerar ett objekt som består av nyckelvärdepar.

### Exempelkod

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
