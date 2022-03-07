---
description: Översikt för tekniska och icke-tekniska kunder som vill hämta data från andra system (offline) till Audience Manager.
keywords: inkommande, batch, batchöverföring, batchdata
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Översikt över att skicka satsvisa data till Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 4%

---

# Skicka batchdata till [!DNL Audience Manager] Översikt {#send-batch-data-to-audience-manager-overview}

En översikt för tekniska och icke-tekniska kunder som vill överföra data från andra system (offline) till [!DNL Audience Manager].

## Fördelar

Du kan göra data från andra system tillgängliga i [!DNL Audience Manager]. Vårt system kan hjälpa er att låsa upp värde och utnyttja användardata som ni har samlat in tidigare. Detta inkluderar information om inköp, kundundersökningar, registreringsdata, [!DNL CRM] databaser etc. Även om varje integrering utgör en egen utmaning delar de alla dessa vanliga steg. Granska materialet för att minska arbetet med att göra offline-data tillgängliga online.

## Steg 1: Synkronisera användar-ID:n

Under synkroniseringen [!DNL Audience Manager] tilldelar unika ID:n till klienter och deras användare. Dessa ID:n kallas [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) och [!UICONTROL Unique User ID] ([!UICONTROL UUID]). [!DNL Audience Manager] använder [!UICONTROL DPID] och [!UICONTROL UUID] identifiera användare och kvalificera dem för [!UICONTROL traits], [!UICONTROL segments], målgruppsgrupper och för rapportering. Dessutom har vår datainsamlingskod ([!UICONTROL DIL]) söker efter dessa ID:n för att hämta besöksdata från din webbplats. När det här steget är klart [!DNL Audience Manager] och din offlinedatabas ska innehålla motsvarande ID:n för varje användarpost.

Viktigt att tänka på:

* **Placering av klient-ID:** [!DNL Audience Manager] behöver veta var ditt klient-ID finns på din webbplats (t.ex. lagras det i en cookie, en Analytics-variabel, i sidkod osv.).
* **Exkludera [!DNL PII]:** Användar-ID:n får inte innehålla personligt identifierbar information ([!DNL PII]).
* **Skiftläges- och innehållskänslighet:** Under en datasynkronisering i realtid fångas användar-ID in från din webbplats av [!DNL Audience Manager] måste motsvara ID:n som skickas från din offlinedatabas. Om offlineposter innehåller information om [!DNL User123], men din webbplats återger detta ID som [!DNL USER123], [!DNL Audience Manager] ser dessa som olika besökare. Därför kan inte onlineinformation för den här besökaren kopplas till motsvarande poster i offlinedatabasen. ID:n måste matcha exakt.

Se [ID-synkronisering för inkommande dataöverföringar](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Steg 2: Datafilformat

Filnamn och innehåll följer strikta riktlinjer. Du *måste* namnge och ordna datafiler enligt dessa specifikationer i den här handboken. Se:

* [Krav på Amazon S3-namn och filstorlekar för inkommande datafiler](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Innehåll i inkommande datafil: Syntax, variabler och exempel](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Onlinedata finns för offlinemarknadsföringsarbete

När du lägger ut offlinedata online kan du fortfarande använda den här informationen för offlinekampanjer. För att göra detta [!DNL Audience Manager] exporterar information om egenskaper och segment till en [!DNL FTP] eller [!DNL Amazon S3] var du vill. Kontakta din Partner Solutions Manager om du vill ha mer information eller hjälp.

## Miljö

[!DNL Audience Manager] innehåller följande miljöer för att ta bort filer:

| Miljö | Tjänst | Plats |
|---------|----------|---------|
| Produktion | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Betaversion | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Ytterligare teknisk läsning

Systemingenjörer, utvecklare eller tekniker-/implementeringsteam bör granska [Beskriver batchdataöverföringsprocessen](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) och de andra artiklarna i detta avsnitt. Dessa artiklar innehåller information om överföringsprotokoll, filinnehåll och krav på filnamn.
