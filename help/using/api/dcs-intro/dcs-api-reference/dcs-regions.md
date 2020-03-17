---
description: Det regionala DCS-servervärdnamnet krävs för att anropa DCS. Detta beror på att DCS lagrar information i datacenter som ligger geografiskt nära besökarna. Dina frågor fungerar om du skickar dem till fel DCS, men dessa samtal är ineffektiva och kan fördröja svaret. Om du vill göra en DCS-begäran måste du matcha region-ID:t med motsvarande regionalt värdnamn och skapa frågan med rätt värdnamn.
seo-description: Det regionala DCS-servervärdnamnet krävs för att anropa DCS. Detta beror på att DCS lagrar information i datacenter som ligger geografiskt nära besökarna. Dina frågor fungerar om du skickar dem till fel DCS, men dessa samtal är ineffektiva och kan fördröja svaret. Om du vill göra en DCS-begäran måste du matcha region-ID:t med motsvarande regionalt värdnamn och skapa frågan med rätt värdnamn.
seo-title: DCS-region-ID, -platser och -värdnamn
solution: Audience Manager
title: DCS-region-ID, -platser och -värdnamn
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS-region-ID, -platser och -värdnamn {#dcs-region-ids-locations-and-host-names}

Det regionala [!UICONTROL DCS] servervärdnamnet krävs för att anropa [!UICONTROL DCS]. Detta beror på att informationen [!UICONTROL DCS] lagras i datacenter som är geografiskt nära besökarna. Dina frågor fungerar om du skickar dem till fel [!UICONTROL DCS], men dessa samtal är ineffektiva och kan fördröja svaret. Om du vill göra en [!UICONTROL DCS] begäran måste du matcha region-ID:t med dess motsvarande regionala värdnamn och skapa frågan med rätt värdnamn.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS-region-ID (dcs_region) </th> 
   <th colname="col2" class="entry"> Region (och plats) </th> 
   <th colname="col3" class="entry"> Värdnamn </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Sydostasien (Singapore) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>Sydamerika (São Paulo, Brasilien) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublin, Irland) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>US East (Virginia, USA) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Södra Stilla havet/Oceanien (Sydney, Australien) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>Västra USA (Oregon, USA) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Asien (Tokyo, Japan) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>Indien </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Du kan också använda [!DNL API] metoder för att hämta en lista över tillgängliga [!UICONTROL DCS] regioner. Se API-metoder för [DCS-regioner](../../../api/rest-api-main/aam-api-dcs-regions.md).