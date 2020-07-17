---
description: En allmän översikt över hur Audience Manager utför dataöverföringar i realtid med en tredjepartsleverantör av innehåll.
seo-description: En allmän översikt över hur Audience Manager utför dataöverföringar i realtid med en tredjepartsleverantör av innehåll.
seo-title: Dataöverföringsprocessen i realtid beskrivs
solution: Audience Manager
title: Dataöverföringsprocessen i realtid beskrivs
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

En allmän översikt över hur Audience Manager utför dataöverföringar i realtid med en tredjepartsleverantör av innehåll.

<!-- real-time-data-transfer-explained.xml -->

## Dataöverföringar i realtid

Dataöverföringar i realtid skickar och tar emot segment-ID:n när en användare besöker eller vidtar åtgärder på webbplatsen. Synkrona dataöverföringar är vanligtvis användbara när du behöver kvalificera eller segmentera användare direkt när de navigerar i lagret.

## Dataintegreringssteg

Integreringen av data i realtid fungerar på följande sätt:

1. En användare besöker en kunds webbplats som innehåller Audience Manager-kod.
1. Audience Manager läser in en iframe och anropar vår [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. Servern [!DNL DCS] anropar tredjepartsservern (i realtid) för att kontrollera om leverantören har någon segmentinformation om användaren.
1. Innehållsleverantören returnerar segmentinformation om den användaren till Audience Manager.
1. Audience Manager får denna segmentinformation och kan målinrikta och bygga nya egenskaper och segment.

![](assets/rt_reduce70.png)