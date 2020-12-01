---
description: En allmän översikt över hur Audience Manager utför ett asynkront batchdatautbyte med en tredjepartsleverantör.
seo-description: En allmän översikt över hur Audience Manager utför ett asynkront batchdatautbyte med en tredjepartsleverantör.
seo-title: Beskrivning av satsvis överföring av data
solution: Audience Manager
title: Beskrivning av satsvis överföring av data
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 7%

---


# Beskrivning av satsvis överföring av data {#batch-data-transfer-process-described}

En allmän översikt över hur [!DNL Audience Manager] utför ett asynkront batchdatautbyte med en tredjepartsleverantör.

## Gruppdataintegrering

<!-- c_async.xml -->

Gruppdataintegreringsprocessen sparar besökarinformation på våra servrar och synkroniserar materialet med data som skickas av en leverantör med regelbundna intervall. Den asynkrona dataöverföringsprocessen är användbar när:

* Omedelbara dataöverföringar krävs inte.
* Samla in data för att skapa en stor grupp segmenterade användare.
* Du vill minska datameddelanden och `HTTP` anrop från webbläsaren.

![](assets/s2s_70.png)

## Dataintegreringssteg

1. En användare besöker en kundwebbplats.
1. [!DNL Audience Manager] och tredjepartsleverantören av data tilldelar besökaren ett unikt ID (vanligtvis med en cookie).
1. [!DNL Audience Manager] anropar tredjeparts dataleverantör för att matcha besökar-ID:n.
1. En schemalagd begäran utbyter vanligtvis data om besökarsegment mellan [!DNL Audience Manager] och din tredjepartsleverantör av data.
1. När en inkommande [!UICONTROL Server-to-Server]-fil bearbetas, skickas ett kvitto via e-post till partnerlösningar och, om den är konfigurerad, till partnern. Mer information finns i [Exempelmeddelande till partners efter inkommande bearbetning](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
