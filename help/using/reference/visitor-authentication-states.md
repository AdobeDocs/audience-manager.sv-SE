---
description: Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.
keywords: dpm.demdex.net
seo-description: Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.
seo-title: Autentiseringstillstånd för besökare i Audience Manager
solution: Audience Manager
title: Autentiseringstillstånd för besökare i Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---


# Autentiseringstillstånd för besökare i Audience Manager{#visitor-authentication-states-in-audience-manager}

Statusen för besöksautentisering i Audience Manager avgör om den nya trait-informationen skrivs till besökarens autentiserade profil eller till enhetsprofilen, där data samlades in från. Audience Manager hanterar autentiseringsstatusarna för besökar-ID UNKNOWN och LOGGED_OUT i händelseanrop på samma sätt.

Från och med [!DNL Experience Cloud] ID-tjänsten v1.5+ innehåller metoden det valfria `setCustomerID` `AuthState` objektet. `AuthState` identifierar besökare utifrån deras [autentiseringsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] hanterar de realiserade egenskaperna på olika sätt, beroende på vilken autentiseringsstatus som skickas i anropet och vilken [profilkopplingsregel](../features/profile-merge-rules/merge-rules-dashboard.md) du använder för segmentering.

## Autentiseringsstatus: OKÄND {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Begäranvärde </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Läs</b> information från den autentiserade profilen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Skriv</b> nya egenskaper i den autentiserade profilen </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Ja, om kopplingsregeln för autentiserade alternativ = "Senaste autentiserade profiler". </p> </td> 
   <td colname="col3" morerows="1"> <p>Nej, trait-data läggs till i enhetsprofilen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nej, om kopplingsregeln för autentiserade alternativ = "Aktuella autentiserade profiler" eller "Ingen autentiserad profil". </p> </td> 
  </tr> 
 </tbody> 
</table>

Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Autentiseringsstatus: AUTENTISERAD {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Begäranvärde </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Läs</b> information från den autentiserade profilen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Skriv</b> nya egenskaper i den autentiserade profilen </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Ja, om kopplingsregeln för autentiserade alternativ = "Aktuella autentiserade profiler" eller "Senaste autentiserade profiler". </p> </td> 
   <td colname="col3" morerows="1"> <p>Ja, trait-data läggs till i den autentiserade profilen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nej, om kopplingsregeln för autentiserade alternativ = "Ingen autentiserad profil". </p> </td> 
  </tr> 
 </tbody> 
</table>

Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Autentiseringsstatus: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Begäranvärde </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Läs</b> information från den autentiserade profilen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Skriv</b> nya egenskaper i den autentiserade profilen </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Ja, om kopplingsregeln för autentiserade alternativ = "Senaste autentiserade profiler" </td> 
   <td colname="col3" morerows="1"> <p>Nej, trait-data skrivs till enhetsprofilen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Nej, om kopplingsregeln för autentiserade alternativ = "Aktuella autentiserade profiler" eller "Ingen autentiserad profil" </td> 
  </tr> 
 </tbody> 
</table>

Exempelanrop (det begärandevärde som motsvarar autentiseringsstatusen markeras):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] utför en ID-synkronisering mellan [CID och UUID](../reference/ids-in-aam.md) i alla tre fallen.

>[!MORELIKETHIS]
>
>* [Kund-ID:n och autentiseringstillstånd](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

