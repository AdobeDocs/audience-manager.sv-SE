---
description: Här på Audience Manager är vi ingenjörer, utvecklare och kodar ninjor precis som du. Och precis som du vill vi arbeta med tillförlitlig, korrekt API-dokumentation. Därför skriver vi om vårt API-innehåll i Swagger och flyttar det till en ny plats. Dessa ändringar är utformade för att förbättra din upplevelse av Audience Manager API-kod.
seo-description: Här på Audience Manager är vi ingenjörer, utvecklare och kodar ninjor precis som du. Och precis som du vill vi arbeta med tillförlitlig, korrekt API-dokumentation. Därför skriver vi om vårt API-innehåll i Swagger och flyttar det till en ny plats. Dessa ändringar är utformade för att förbättra din upplevelse av Audience Manager API-kod.
seo-title: API-kodmigrering för Audience Manager
solution: Audience Manager
title: API-kodmigrering för Audience Manager
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# API-kodmigrering för Audience Manager {#audience-manager-api-code-migration}

Här på Audience Manager är vi ingenjörer, utvecklare och kodar ninjor precis som du. Och precis som du vill vi arbeta med tillförlitlig och korrekt [!DNL API] dokumentation. Därför skriver vi om vårt [!DNL API] innehåll i [!DNL Swagger] och flyttar det till en ny plats. Dessa ändringar är utformade för att förbättra din upplevelse av Audience Manager- [!DNL API] koden.

## Flytta uppåt {#code-migration-details}

<!-- api-swagger-migration.xml -->

Webbplatsen [Adobe Audience Manager API Docs](https://bank.demdex.com/portal/swagger/index.html) är det nya hemmet för vårt reviderade [!DNL API] innehåll. Vi ska försöka skriva om och flytta några uppsättningar [!DNL API] metoder med varje release. Det innebär att du måste checka in både den nya platsen och [REST API](../api/rest-api-main/rest-api-main.md) -dokumentationen för att hitta alla tillgängliga metoder. Till slut kommer alla allmänheten att [!DNL API]finnas på [!DNL Audience Manager][!DNL API] dokumentsajten. I följande tabell visas ändrade och migrerade [!DNL API]filer.

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API-typ </th> 
   <th colname="col2" class="entry"> API-metoder </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Algoritmiska modeller</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Algoritmiska modeller</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Dataflöden</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Datafeedbegäran</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Datafeedfinansiering</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Dataflödesplaner</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Prenumerationer på dataflöden</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Datakälla</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Datakällor</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Härledda signaler</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Härledda signaler</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Mappar</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Segmentmappar</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Trait Folders</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Rapportering</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Rapportering</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segment</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Segmenttestgrupper</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> Utkast-API för segmenttestgrupp</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traits</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Traits</a> </p> </td> 
  </tr>
 </tbody>
</table>