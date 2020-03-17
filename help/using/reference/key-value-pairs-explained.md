---
description: Definierar och beskriver standard- och serialiserade nyckelvärdepar.
keywords: integration code
seo-description: Definierar och beskriver standard- och serialiserade nyckelvärdepar.
seo-title: Förklaring av nyckelvärdepar
solution: Audience Manager
title: Förklaring av nyckelvärdepar
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Förklaring av nyckelvärdepar{#key-value-pairs-explained}

Definierar och beskriver standard- och serialiserade nyckelvärdepar.

<!-- 

c_key_value_explained.xml

 -->

Ett nyckelvärdepar består av två relaterade dataelement: En nyckel, som är en konstant som definierar datauppsättningen (t.ex. kön, färg, pris) och ett värde, vilket är en variabel som tillhör uppsättningen (t.ex. man/kvinna, grön, 100). Ett nyckelvärdepar kan ha följande format:

* `gender = male`
* `color = green`
* `price > 100`

## Standardpar och serialiserade nyckelvärdepar {#standard-serialized-pairs}

Destinationer tar emot nyckelvärdesdata i *`standard`* eller *`serialized`* format. Med standardformatering ordnas data i separata nyckelvärdepar. Varje nyckel anges explicit, även om den används igen för att definiera ett annat värde. Vid serialiserad formatering komprimeras däremot flera värden till en uppsättning som definieras av en enda tangent. I ett serialiserat par används dessutom en specialindikator för att separera värdena i nyckelvärdesmängden. Slutligen kan standardvärden och serialiserade nyckelvärden innehålla ett eller flera värden. Följande tabell innehåller exempel på standardformat och serienyckelformat.

| Formatering | Enkel nyckel | Nyckelvärdepar |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serialiserad** | `x=1;2` | `x=1;2&y=3;4` |



## Tangenter, avgränsare och avgränsare {#keys-delimiters-separators}

När du arbetar med serialiserade data måste du ange tecknen som avgränsar värden *inom* och *mellan* nyckelvärdepar. Element i nyckelvärdepar definieras enligt följande:

* **Nyckel:** En unik identifierare i nyckelvärdepar.
* **Värdeavgränsare:** Separerar enskilda nyckelvärdepar.
* **Nyckelvärdesavgränsare:** Separerar en nyckel från värdena i ett nyckelvärdepar.
* **Serieavgränsare:** Separerar enskilda värden inom serialiserade nyckelvärdepar.

## Standard- och serialiserade nyckelvärdeselement {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ </th> 
   <th colname="col2" class="entry"> Exempel </th> 
   <th colname="col3" class="entry"> Nyckel </th> 
   <th colname="col4" class="entry"> Avgränsare för nyckelvärde </th> 
   <th colname="col5" class="entry"> Avgränsare för nyckelvärde </th> 
   <th colname="col6" class="entry"> Serieavgränsare </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Enkel tangent</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nyckelvärdepar</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Enkel tangent</b> <p>(seriell) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/a </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Nyckelvärdepar</b> (seriella) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

