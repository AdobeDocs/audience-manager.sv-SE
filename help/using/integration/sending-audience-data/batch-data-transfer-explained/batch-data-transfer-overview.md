---
description: En översikt för tekniska och icke-tekniska kunder som vill överföra data från andra system (offline) till Audience Manager.
keywords: inbound, batch, batch upload, batch data
seo-description: En översikt för tekniska och icke-tekniska kunder som vill överföra data från andra system (offline) till Audience Manager. Det gör du genom att använda alternativet för batchöverföring i Audience Manager.
seo-title: Skicka gruppdata till Audience Manager - översikt
solution: Audience Manager
title: Skicka gruppdata till Audience Manager - översikt
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# Skicka gruppdata till Audience Manager - översikt{#send-batch-data-to-audience-manager-overview}

En översikt för tekniska och icke-tekniska kunder som vill överföra data från andra system (offline) till Audience Manager.

## Fördelar

<!-- c_offline_to_online.xml -->

Du kan göra data från andra system tillgängliga i Audience Manager. Vårt system kan hjälpa er att låsa upp värde och utnyttja användardata som ni har samlat in tidigare. Detta inkluderar information om inköp, kundundersökningar, registreringsdata, [!DNL CRM] databaser etc. Även om varje integrering utgör en egen utmaning delar de alla dessa vanliga steg. Granska materialet för att minska arbetet med att göra offline-data tillgängliga online.

## Steg 1: Synkronisera användar-ID:n

Under synkroniseringen tilldelar Audience Manager unika ID:n till klienter och deras användare. Dessa ID:n kallas [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) respektive [!UICONTROL Unique User ID] ([!UICONTROL UUID]). Audience Manager använder [!UICONTROL DPID] och [!UICONTROL UUID] för att identifiera användare och kvalificera dem för egenskaper, segment, målgruppsgrupper och för rapportering. Dessutom söker vår datainsamlingskod ([!UICONTROL DIL]) efter dessa ID:n för att hämta besöksdata från din webbplats. När det här steget är klart bör Audience Manager och din offlinedatabas innehålla motsvarande ID:n för varje användarpost.

Viktigt att tänka på:

* **Placering av klient-ID:** Audience Manager måste veta var ditt klient-ID finns på webbplatsen (t.ex. lagras det i en cookie, en Analytics-variabel, i sidkod osv.).
* **Exkludera[!DNL PII]:** Användar-ID:n får inte innehålla personligt identifierbar information ([!DNL PII]).
* **Skiftläges- och innehållskänslighet:** Under en datasynkronisering i realtid måste användar-ID:n som hämtas från din webbplats av Audience Manager motsvara ID:n som skickas från din offlinedatabas. Om offlineposter till exempel innehåller information om [!DNL User123], men din webbplats återger det ID:t som, [!DNL USER123]ser Audience Manager dessa som olika besökare. Därför kan inte onlineinformation för den här besökaren kopplas till motsvarande poster i offlinedatabasen. ID:n måste matcha exakt.

Se [ID-synkronisering för inkommande dataöverföringar](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## Steg 2: Datafilformat

Filnamn och innehåll följer strikta riktlinjer. Du *måste* namnge och ordna datafiler enligt dessa specifikationer i den här handboken. Se:

* [Amazon S3-namnkrav för inkommande datafiler](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Innehåll i inkommande datafil: Syntax, variabler och exempel](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Onlinedata finns för offlinemarknadsföringsarbete

När du lägger ut offlinedata online kan du fortfarande använda den här informationen för offlinekampanjer. Det gör du genom att Audience Manager exporterar egenskaper och segmentinformation till en [!DNL FTP] eller [!DNL Amazon S3] en plats som du väljer. Kontakta din Partner Solutions Manager om du vill ha mer information eller hjälp.

## Miljö

Audience Manager har följande miljöer för att ta bort filer:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Miljö </th> 
   <th colname="col02" class="entry"> Tjänst </th> 
   <th colname="col2" class="entry"> Plats </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Produktion</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Beta Environment</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ytterligare teknisk läsning

Systemingenjörer, utvecklare eller tekniker-/implementeringsteam ska granska [batchdataöverföringsprocessen Beskrivna](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) och övriga artiklar i detta avsnitt. Dessa artiklar innehåller information om överföringsprotokoll, filinnehåll och krav på filnamn.