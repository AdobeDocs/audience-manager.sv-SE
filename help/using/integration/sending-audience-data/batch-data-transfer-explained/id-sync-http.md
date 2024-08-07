---
description: Beskriver syntaxen och parametrarna som används i det inledande HTTP-anropet för att synkronisera användar-ID:n mellan en leverantör och Audience Manager. Synkronisering av ID kan påbörjas när du har skickat din datataxonomi till Audience Manager.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: ID-synkronisering för inkommande dataöverföringar
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 1%

---

# ID-synkronisering för inkommande dataöverföringar {#id-synchronization-for-inbound-data-transfers}

Beskriver syntaxen och parametrarna som används i det första `HTTP`-anropet för att synkronisera användar-ID:n mellan en leverantör och [!DNL Audience Manager]. Synkronisering av ID kan påbörjas när du har skickat din datataxonomi till [!DNL Audience Manager].

ID-synkronisering är det första steget i den inkommande, asynkrona dataöverföringsprocessen. I det här steget jämför och matchar [!DNL Audience Manager] och leverantören ID:n för sina respektive webbplatsbesökare. En [!DNL Audience Manager]-kund kan till exempel känna en användare med ID 123. Din datapartner kan dock identifiera den här användaren med ID 456. Med synkroniseringsprocessen kan [!DNL Audience Manager] och en dataleverantör stämma av dessa olika ID:n och identifiera användare i sina respektive system. När det är klart ska [!DNL Audience Manager] och din tredjepartspartner ha motsvarande ID:n för varje unik användare som visas i våra nätverk.

Du kan använda följande metoder för att hämta data till [!DNL Audience Manager]:

* [HTTP-begäran om synkronisering av ID](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Deklarerad ID-händelse](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID-synkronisering från en e-postinbäddad bild](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID-synkroniseringsbegäran `HTTP` {#id-sync-http}

I en ID-utbyte ska en korrekt formaterad [!DNL URL]-sträng se ut så här:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>Unikt ID för innehållsleverantören (tilldelad av <span class="keyword"> Audience Manager </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (procent) för den kodade representationen av ditt unika användar-ID. Förutom kodning av reserverade ASCII-tecken bör alla tecken som inte är ASCII-tecken kodas i procent baserat på teckenkodningstabellen UTF-8. </p> <p>Mer information finns på webbplatsen <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>En kodad URL-omdirigering med makrot <code> ${DD_UUID}</code> inbäddat i. </p> <p>Obs! Tillagd endast när innehållsleverantören initierar anropet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Valfritt. Lägg till den här parametern om du använder plugin-programmet <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager för IAB TCF.</a></p> <p><code> gdpr</code> kan vara 0 (GDPR gäller inte) eller 1 (GDPR gäller). </p> <p> <b>Obs!</b> Den här parametern kan bara användas tillsammans med <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Valfritt. Lägg till den här parametern om du använder plugin-programmet <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager för IAB TCF.</a></p> <p><code>gdpr_consent</code> är den URL-säkra base64-kodade GDPR-medgivandesträngen (se <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-specifikation </a>). </p> <p> <b>Obs!</b> Den här parametern kan bara användas tillsammans med <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Händelsen [!UICONTROL Declared ID] {#declared-id-event}

Mer information finns i [Deklarerade ID:n](../../../features/declared-ids.md).

## ID-synkronisering från en e-postinbäddad bild {#id-sync-email-image}

Formatet för att matcha ID:n via en e-postbild är detsamma som visas ovan. Observera dock att bilder i ett e-postmeddelande måste aktiveras för att det här ska fungera. Detta kan påverka ID-synkroniseringen via e-post eftersom de flesta e-postsystem som standard inaktiverar bilder.

>[!MORELIKETHIS]
>
>* [Datainsamlingskomponenter](../../../reference/system-components/components-data-collection.md)
