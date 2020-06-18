---
description: En allmän översikt över hur Audience Manager utför ett asynkront batchdatautbyte med en tredjepartsleverantör.
seo-description: En allmän översikt över hur Audience Manager utför ett asynkront batchdatautbyte med en tredjepartsleverantör.
seo-title: Beskriver batchdataöverföringsprocessen
solution: Audience Manager
title: Beskriver batchdataöverföringsprocessen
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---


# Beskriver batchdataöverföringsprocessen {#batch-data-transfer-process-described}

En allmän översikt över hur [!DNL Audience Manager] utför ett asynkront batchdatautbyte med en tredjepartsleverantör.

## Gruppdataintegrering

<!-- c_async.xml -->

Gruppdataintegreringsprocessen sparar besökarinformation på våra servrar och synkroniserar materialet med data som skickas av en leverantör med regelbundna intervall. Den asynkrona dataöverföringsprocessen är användbar när:

* Omedelbara dataöverföringar krävs inte.
* Samla in data för att skapa en stor grupp segmenterade användare.
* Du vill minska datameddelanden och `HTTP` samtal från webbläsaren.

![](assets/s2s_70.png)

## Dataintegreringssteg

1. En användare besöker en kundwebbplats.
1. Audience Manager och tredjepartsleverantören av data tilldelar besökaren ett unikt ID (vanligtvis med en cookie).
1. Audience Manager anropar en tredjeparts dataleverantör för att matcha besökar-ID:n.
1. En schemalagd begäran utbyter vanligtvis data om besökarsegment mellan Audience Manager och din tredjepartsleverantör.
1. När en inkommande [!UICONTROL Server-to-Server] fil bearbetas skickas ett kvitto via e-post till partnerlösningar och, om konfigurationen är konfigurerad, till partnern. Mer information finns i [Exempelmeddelande till partners efter inkommande bearbetning](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).