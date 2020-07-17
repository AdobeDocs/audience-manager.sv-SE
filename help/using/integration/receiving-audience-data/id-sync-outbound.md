---
description: Beskriver syntaxen och parametrarna som används i det inledande HTTP-anropet för att synkronisera användar-ID:n mellan Audience Manager och en tredjepartsleverantör av data. Kontakta din Adobe Audience Manager-konsult innan du försöker synkronisera ditt första ID.
seo-description: Beskriver syntaxen och parametrarna som används i det inledande HTTP-anropet för att synkronisera användar-ID:n mellan Audience Manager och en tredjepartsleverantör av data. Kontakta din Adobe Audience Manager-konsult innan du försöker synkronisera ditt första ID.
seo-title: ID-synkronisering för utgående dataöverföringar
solution: Audience Manager
title: ID-synkronisering för utgående dataöverföringar
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 11%

---


# ID-synkronisering för utgående dataöverföringar{#id-synchronization-for-outbound-data-transfers}

Beskriver syntaxen och parametrarna som används i det första `HTTP` anropet för att synkronisera användar-ID:n mellan Audience Manager och en tredjepartsleverantör av data. Kontakta din Adobe Audience Manager-konsult innan du försöker synkronisera ditt första ID.

<!-- c_id_sync_out.xml -->

## Syfte med ID-synkronisering

ID-synkronisering är det första steget i den utgående, asynkrona dataöverföringsprocessen. I det här steget jämför [!DNL Audience Manager] och leverantören ID:n för sina respektive webbplatsbesökare. En kund kan till exempel känna en användare med ID 123. [!DNL Audience Manager] Din datapartner kan dock identifiera den här användaren med ID 456. Med synkroniseringsprocessen kan [!DNL Audience Manager] och en dataleverantör stämma av dessa olika ID:n och identifiera användare i sina respektive system. När allt är klart [!DNL Audience Manager] och tredjepartsleverantören av data bör ha motsvarande ID:n för varje unik användare som visas i våra nätverk.

## URL-syntax

I en ID-växling ska en korrekt formaterad [!DNL URL] sträng se ut så här:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-parametrar

Anropet [!DNL URL] för synkronisering av inkommande ID ska innehålla variabler som beskrivs i tabellen nedan.

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
   <td colname="col2">En kodad URL omdirigeras med makrot <code> ${DD_UUID}</code> inbäddat. <p><b>Obs!</b> Tillagd endast när DataProvider initierar anropet. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> kan vara 0 (GDPR gäller inte) eller 1 (GDPR gäller).</p><p><b>Obs!</b> <ul><li>Parametrarna <code>gdpr</code> och <code>gdpr_consent</code> parametrarna introduceras gradvis i URL:er för ID-synkronisering med aktiveringspartners. Se Aktiveringspartners som har stöd för IAB TCF i <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager-plugin för IAB TCF.</a></li><li>Den här parametern kan bara användas tillsammans med <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> is the URL-safe base64-encoded GDPR consent string (see <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specification</a>).</p><p><b>Obs!</b> Den här parametern kan bara användas tillsammans med <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [API-metoder och -kod för datainsamlingsservrar (DCS) ](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Datainsamlingskomponenter](../../reference/system-components/components-data-collection.md)

