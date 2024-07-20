---
description: Översikt för tekniska och icke-tekniska kunder som vill hämta data från andra system (offline) till Audience Manager.
keywords: inkommande, batch, batchöverföring, batchdata
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Skicka batchdata till Audience Manager - översikt
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 2%

---

# Skicka gruppdata till [!DNL Audience Manager] - översikt {#send-batch-data-to-audience-manager-overview}

En översikt för tekniska och icke-tekniska kunder som vill överföra data från andra system (offline) till [!DNL Audience Manager].

## Fördelar

Du kan göra data från andra system tillgängliga i [!DNL Audience Manager]. Vårt system kan hjälpa er att låsa upp värde och utnyttja användardata som ni har samlat in tidigare. Detta inkluderar information om inköp, kundundersökningar, registreringsdata, [!DNL CRM] databaser osv. Även om varje integrering utgör en egen utmaning delar de alla dessa vanliga steg. Granska materialet för att minska arbetet med att göra offline-data tillgängliga online.

## Steg 1: Synkronisera användar-ID:n

Under synkroniseringen tilldelar [!DNL Audience Manager] unika ID:n till klienter och deras användare. Dessa ID:n kallas [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) respektive [!UICONTROL Unique User ID] ([!UICONTROL UUID]). [!DNL Audience Manager] använder [!UICONTROL DPID] och [!UICONTROL UUID] för att identifiera användare och kvalificera dem för [!UICONTROL traits], [!UICONTROL segments], målgruppsgrupper och för rapportering. Dessutom söker vår datainsamlingskod ([!UICONTROL DIL]) efter dessa ID:n för att hämta besöksdata från din webbplats. När det här steget är klart ska [!DNL Audience Manager] och offlinedatabasen innehålla motsvarande ID:n för varje användarpost.

Viktigt att tänka på:

* **Placering av klient-ID:** [!DNL Audience Manager] behöver veta var ditt klient-ID visas på din webbplats (t.ex. lagras det i en cookie, en analysvariabel, i sidkod osv.).
* **Uteslut [!DNL PII]:** Användar-ID:n får inte innehålla personligt identifierbar information ([!DNL PII]).
* **Skiftläges- och innehållskänslighet:** Under en realtidsdatasynkronisering måste användar-ID:n som [!DNL Audience Manager] har hämtat från din webbplats motsvara ID:n som har skickats från din offlinedatabas. Om offlineposter till exempel innehåller information om [!DNL User123], men din webbplats återger det ID:t som [!DNL USER123], ser [!DNL Audience Manager] dessa som olika besökare. Därför kan inte onlineinformation för den här besökaren kopplas till motsvarande poster i offlinedatabasen. ID:n måste matcha exakt.

Se [ID-synkronisering för inkommande dataöverföringar](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Steg 2: Datafilformat

Filnamn och innehåll följer strikta riktlinjer. Du *måste* namnge och ordna datafiler enligt dessa specifikationer i den här handboken. Se:

* [Krav på Amazon S3-namn och filstorlekar för inkommande datafiler](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Innehåll i inkommande datafil: Syntax, Variables, and Examples](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Onlinedata finns för offlinemarknadsföringsarbete

När du lägger ut offlinedata online kan du fortfarande använda den här informationen för offlinekampanjer. För att göra detta exporterar [!DNL Audience Manager] trait- och segmentinformation till en [!DNL FTP]- eller [!DNL Amazon S3]-plats som du väljer. Kontakta din Partner Solutions Manager om du vill ha mer information eller hjälp.

## Miljö

[!DNL Audience Manager] innehåller följande miljöer för att ta bort filer:

| Miljö | Tjänst | Plats |
|---------|----------|---------|
| Produktion | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Beta | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## Ytterligare teknisk läsning

Systemingenjörer, utvecklare eller tekniker-/implementeringsteam bör granska [batchdataöverföringsprocessen som beskrivs](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) och de andra artiklarna i det här avsnittet. Dessa artiklar innehåller information om överföringsprotokoll, filinnehåll och krav på filnamn.
