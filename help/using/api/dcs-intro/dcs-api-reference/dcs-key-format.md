---
description: När DCS anropar tar det emot nyckelvärdesdata i standard- eller serialiserat format. I det här avsnittet finns information om hur du formaterar standarddata och serialiserade nyckelvärdesdata.
seo-description: När DCS anropar tar det emot nyckelvärdesdata i standard- eller serialiserat format. I det här avsnittet finns information om hur du formaterar standarddata och serialiserade nyckelvärdesdata.
seo-title: Formatera nyckelvärdepar i DCS-anrop
solution: Audience Manager
title: Formatera nyckelvärdepar i DCS-anrop
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Formatera nyckelvärdepar i DCS-anrop {#formatting-key-value-pairs-in-dcs-calls}

När användaren gör ett anrop tar [!UICONTROL DCS] användaren emot nyckelvärdesdata i standard- eller serialiserat format. I det här avsnittet finns information om hur du formaterar standarddata och serialiserade nyckelvärdesdata.

## Standardpar och serialiserade nyckelvärdepar {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nyckelvärdestyp </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
   <th colname="col3" class="entry"> Exempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Ett standardpar med nyckelvärden består av en enda nyckel och ett värde. I den här strukturen ordnas data i separata nyckelvärdepar. Varje nyckel anges explicit, även när den används igen för att definiera ett annat värde. Detta är det vanligaste sättet att skicka data till DCS. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Serialiserad</b> </td> 
   <td colname="col2"> <p>Ett serialiserat nyckelvärdepar består av en enda nyckel och flera värden. Detta kan vara ett effektivt sätt att ordna data, men serialiserade nyckelvärdepar kräver särskilda symboler för att separera varje nyckel och varje nyckelvärdesuppsättning. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Avgränsare och avgränsare för serialiserade nyckelvärdepar {#delimiters-separators}

Med serialiserade nyckelvärdepar måste du ange markörerna som avgränsar värden inom och mellan dessa variabler. Audience Manager kräver följande avgränsare och avgränsare:

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Krav för </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Separerar enskilda </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Avgränsare</b> </td> 
   <td colname="col2"> et &amp; </td> 
   <td colname="col3"> <p>Nyckelvärdepar: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Avgränsare</b> </td> 
   <td colname="col2"> Komma , </td> 
   <td colname="col3"> <p>Värden i nyckelvärdepar: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Skicka data till DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Nyckelvärdesprefix och variabler som stöds av DCS](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Förklaring av nyckelvärdepar](../../../reference/key-value-pairs-explained.md)

