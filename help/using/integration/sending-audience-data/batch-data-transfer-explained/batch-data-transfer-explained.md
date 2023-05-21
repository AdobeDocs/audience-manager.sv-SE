---
description: En allmän översikt över hur Audience Manager utför ett asynkront batchdatautbyte med en tredjepartsleverantör.
seo-description: A general overview of how Audience Manager performs an asynchronous batch data exchange with a third-party vendor.
seo-title: Batch Data Transfer Process Described
solution: Audience Manager
title: Beskrivning av satsvis överföring av data
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 5%

---

# Beskrivning av satsvis överföring av data {#batch-data-transfer-process-described}

En allmän översikt över hur [!DNL Audience Manager] utför ett asynkront batchdatautbyte med en tredjepartsleverantör.

## Gruppdataintegrering

<!-- c_async.xml -->

Gruppdataintegreringsprocessen sparar besökarinformation på våra servrar och synkroniserar materialet med data som skickas av en leverantör med regelbundna intervall. Den asynkrona dataöverföringsprocessen är användbar när:

* Omedelbara dataöverföringar krävs inte.
* Samla in data för att skapa en stor grupp segmenterade användare.
* Du vill minska diskrepanser och `HTTP` samtal från webbläsaren.

![](assets/s2s_70.png)

## Dataintegreringssteg

1. En användare besöker en kundwebbplats.
1. [!DNL Audience Manager] och tredjepartsleverantören av data tilldelar besökaren ett unikt ID (vanligtvis med en cookie).
1. [!DNL Audience Manager] anropar tredjeparts dataleverantör för att matcha besökar-ID:n.
1. En schemalagd begäran utbyter vanligtvis data om besökarsegment mellan [!DNL Audience Manager] och din tredjepartsleverantör av data.
1. Vid inkommande [!UICONTROL Server-to-Server] filen bearbetas skickas ett kvitto via e-post till partnerlösningar och, om det är konfigurerat, till partnern. Mer information finns i [Exempelmeddelande till partners efter inkommande bearbetning](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
