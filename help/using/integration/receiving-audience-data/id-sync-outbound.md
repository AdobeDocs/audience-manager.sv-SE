---
description: Beskriver syntaxen och parametrarna som används i det inledande HTTP-anropet för att synkronisera användar-ID:n mellan Audience Manager och en tredjepartsleverantör av data. Kontakta Adobe Audience Manager-konsulten innan du försöker synkronisera ditt första ID.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: ID-synkronisering för utgående dataöverföringar
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 1%

---

# ID-synkronisering för utgående dataöverföringar{#id-synchronization-for-outbound-data-transfers}

Beskriver syntaxen och parametrarna som används i det första `HTTP`-anropet för att synkronisera användar-ID:n mellan Audience Manager och en tredjepartsleverantör av data. Kontakta Adobe Audience Manager-konsulten innan du försöker synkronisera ditt första ID.

<!-- c_id_sync_out.xml -->

## Syfte med ID-synkronisering

ID-synkronisering är det första steget i den utgående, asynkrona dataöverföringsprocessen. I det här steget jämför och matchar [!DNL Audience Manager] och leverantören ID:n för sina respektive webbplatsbesökare. En [!DNL Audience Manager]-kund kan till exempel känna en användare med ID 123. Din datapartner kan dock identifiera den här användaren med ID 456. Med synkroniseringsprocessen kan [!DNL Audience Manager] och en dataleverantör stämma av dessa olika ID:n och identifiera användare i sina respektive system. När det är klart ska [!DNL Audience Manager] och tredjepartsdataleverantören ha motsvarande ID:n för varje unik användare som visas i våra nätverk.

## URL-syntax

I en ID-utbyte ska en korrekt formaterad [!DNL URL]-sträng se ut så här:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-parametrar

[!DNL URL] för ditt inkommande ID-synkroniseringsanrop ska innehålla variabler som beskrivs i tabellen nedan.

>[!NOTE]
>
>Ersätt kursivt innehåll med faktiska parametervärden.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">Unikt ID för dataleverantören (tilldelad av <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Unikt användar-ID. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">En kodad URL-omdirigering med makrot <code> ${DD_UUID}</code> inbäddat i. <p><b>Obs!</b> Tillagd endast när dataprovidern initierar anropet. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> kan vara 0 (GDPR gäller inte) eller 1 (GDPR gäller).</p><p><b>Obs!</b> <ul><li>Parametrarna <code>gdpr</code> och <code>gdpr_consent</code> introduceras gradvis i URL:er för ID-synkronisering med aktiveringspartners. Se Aktiveringspartners som stöder IAB TCF i <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in för IAB TCF.</a></li><li>Den här parametern kan bara användas tillsammans med <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> är den URL-säkra base64-kodade GDPR-medgivandesträngen (se <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-specifikation </a>).</p><p><b>Obs!</b> Den här parametern kan bara användas tillsammans med <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [API-metoder och kod för datainsamlingsserver (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Datainsamlingskomponenter](../../reference/system-components/components-data-collection.md)
