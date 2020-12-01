---
description: Översikt för tekniska och icke-tekniska kunder som vill hämta data från andra system (offline) till Audience Manager.
keywords: inbound, batch, batch upload, batch data
seo-description: Översikt för tekniska och icke-tekniska kunder som vill hämta data från andra system (offline) till Audience Manager. Om du vill göra det använder du alternativet för batchöverföring i Audience Manager.
seo-title: Översikt över att skicka satsvisa data till Audience Manager
solution: Audience Manager
title: Översikt över att skicka satsvisa data till Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 5%

---


# Skicka gruppdata till [!DNL Audience Manager] Översikt {#send-batch-data-to-audience-manager-overview}

En översikt för tekniska och icke-tekniska kunder som vill överföra data från andra system (offline) till [!DNL Audience Manager].

## Fördelar

Du kan göra data från andra system tillgängliga i [!DNL Audience Manager]. Vårt system kan hjälpa er att låsa upp värde och utnyttja användardata som ni har samlat in tidigare. Detta inkluderar information om inköp, kundundersökningar, registreringsdata, [!DNL CRM]-databaser osv. Även om varje integrering utgör en egen utmaning delar de alla dessa vanliga steg. Granska materialet för att minska arbetet med att göra offline-data tillgängliga online.

## Steg 1: Synkronisera användar-ID:n

Under synkroniseringen tilldelar [!DNL Audience Manager] unika ID:n till klienter och deras användare. Dessa ID:n kallas [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) respektive [!UICONTROL Unique User ID] ([!UICONTROL UUID]). [!DNL Audience Manager] använder  [!UICONTROL DPID] och  [!UICONTROL UUID] för att identifiera användare och kvalificera dem för  [!UICONTROL traits],  [!UICONTROL segments], målgruppsgrupper och för rapportering. Dessutom söker vår datainsamlingskod ([!UICONTROL DIL]) efter dessa ID:n för att hämta besöksdata från din webbplats. När det här steget är klart ska [!DNL Audience Manager] och offlinedatabasen innehålla motsvarande ID:n för varje användarpost.

Viktigt att tänka på:

* **Placering av klient-ID:** [!DNL Audience Manager] måste veta var ditt klient-ID finns på webbplatsen (t.ex. lagras det i en cookie, en Analytics-variabel, i sidkod osv.).
* **Exkludera  [!DNL PII]:** Användar-ID:n får inte innehålla personligt identifierbar information ([!DNL PII]).
* **Skiftläges- och innehållskänslighet:** Under en realtidsdatasynkronisering  [!DNL Audience Manager] måste användar-ID:n som hämtas från din webbplats motsvara ID:n som skickas från din offlinedatabas. Om offlineposter till exempel innehåller information om [!DNL User123], men din webbplats återger detta ID som [!DNL USER123], ser [!DNL Audience Manager] dessa som olika besökare. Därför kan inte onlineinformation för den här besökaren kopplas till motsvarande poster i offlinedatabasen. ID:n måste matcha exakt.

Se [ID-synkronisering för inkommande dataöverföringar](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Steg 2: Datafilformat

Filnamn och innehåll följer strikta riktlinjer. Du *måste* namnge och ordna datafiler enligt dessa specifikationer i den här handboken. Se:

* [Krav på Amazon S3-namn och filstorlekar för inkommande datafiler](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Innehåll i inkommande datafil: Syntax, variabler och exempel](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Onlinedata finns för offlinemarknadsföringsarbete

När du lägger ut offlinedata online kan du fortfarande använda den här informationen för offlinekampanjer. För att göra detta exporterar [!DNL Audience Manager] trait- och segmentinformation till en [!DNL FTP]- eller [!DNL Amazon S3]-plats som du väljer. Kontakta din Partner Solutions Manager om du vill ha mer information eller hjälp.

## Miljö

[!DNL Audience Manager] innehåller följande miljöer för att ta bort filer:

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
   <td colname="col1" morerows="1"> <b>Beta-miljö</b> </td> 
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

Systemingenjörer, utvecklare eller tekniker-/implementeringsteam bör granska [batchdataöverföringsprocessen som beskrivs](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) och de andra artiklarna i detta avsnitt. Dessa artiklar innehåller information om överföringsprotokoll, filinnehåll och krav på filnamn.
