---
description: Audience Manager och Adobe Experience Platform Identity Service anropar och tar emot data från domänen demdex.net. Det kan verka som att Adobe arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett demdex.net-anrop.
seo-description: Audience Manager och Adobe Experience Platform Identity Service anropar och tar emot data från domänen demdex.net. Det kan verka som att Adobe arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett demdex.net-anrop.
seo-title: Förstå anrop till Demdex-domänen
solution: Audience Manager
title: Förstå anrop till Demdex-domänen
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Förstå anrop till Demdex-domänen{#understanding-calls-to-the-demdex-domain}

Audience Manager och Adobe Experience Platform Identity Service anropar och tar emot data från domänen demdex.net. Det kan verka som att Adobe arbetar med en ovanlig tredjepartsdomän, men så är inte fallet. I det här avsnittet beskrivs elementen i ett demdex.net-anrop.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Samtalselement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Detta är en äldre domän som styrs av <span class="keyword"> Adobe</span>. Det återspeglar <span class="keyword"> Audience Managers</span>ursprungliga förvärvningsnamn (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> förvärvade <span class="keyword"> Demdex</span> 2011 och gav företaget ett nytt varumärke som <span class="keyword"> Audience Manager</span>. Det är svårt att ändra den här domänen eftersom den är djupt sammankopplad med Audience Manager <span class="keyword"> ,</span>ID-tjänsten <span class="wintitle"></span>och vår installerade användarbas. Se <a href="../overview/aam-overview.md#history-and-background"> Historik och Bakgrund</a>. </p> <p>Du kan se andra prefix som är kopplade till äldre <code> demdex.net</code> samtal (t.ex. <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>osv.). Oberoende av prefix <code><i>something</i>.demdex.net</code> är ett anrop till alltid ett anrop till <span class="keyword"> Adobe</span> och inte till någon okänd eller misstänkt tredjepartsdomän. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> är en förkortning för <span class="wintitle"> Data Provider Match</span>. Den talar om för interna, <span class="keyword"> Adobe</span> -system att ett anrop från <span class="keyword"> Audience Manager</span> eller <span class="wintitle"> ID-tjänsten</span> skickar kunddata för synkronisering eller begär ett ID. Det här är det vanligaste <code> demdex.net</code> anropet du kan se från <span class="keyword"> Audience Manager</span> eller <span class="wintitle"> ID-tjänsten</span>. </p> <p><span class="wintitle"> Grundläggande om DPM</span> -anrop: </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Ett <span class="wintitle"> DPM</span> -anrop från <span class="keyword"> Audience Manager</span> skickar data till <span class="wintitle"> datainsamlingsservrarna</span> och <span class="wintitle"> profilcacheservrarna</span>. Se <a href="../reference/system-components/components-data-collection.md"> Datainsamlingskomponenter</a>. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> ID-tjänst</span> </b>: Ett <span class="wintitle"> DPM</span> -anrop från <span class="wintitle"> ID-tjänsten</span> är en begäran om ett besökar-ID. Se <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies och Adobe Experience Platform Identity Service</a> och <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> How the Adobe Experience Platform Identity Service Requests and Sets ID</a>. </li> 
     </ul> </p> <p> <p>Obs!  <span class="wintitle"> ID-tjänstens</span> kunder kan ändra <span class="wintitle"> DPM</span> -prefixet i domännamnet. Se <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> auditionManager Server och auditionManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookies för Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

