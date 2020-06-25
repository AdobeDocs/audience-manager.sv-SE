---
description: Runt den 14 oktober 2019 märkte jag att mina populationer av trait-egenskaper för Device ID-diagrammet har sjunkit till 0, där de tidigare var mycket högre.
seo-description: Runt den 14 oktober 2019 märkte jag att mina populationer av trait-egenskaper för Device ID-diagrammet har sjunkit till 0, där de tidigare var mycket högre.
seo-title: Varför sjönk mina populationer i Trait-klassen till 0 runt den 15 oktober?
solution: Audience Manager
title: Varför sjönk mina populationer i Trait-klassen till 0 runt den 15 oktober?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---


# Varför sjönk mina populationer i Trait-klassen till 0 runt den 15 oktober? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Fråga

Runt den 14 oktober 2019 märkte jag att mina populationer av trait-egenskaper för Device ID-diagrammet har sjunkit till 0, där de tidigare var mycket högre. Varför hände det här?

![Bild av släppning av enhets-ID](assets/device_id_populationdrop.png)

## Svar

Den 15 oktober ändrades funktionen för sammanfogningsregel i Audience Manager till där inbäddade data från ett CRM-ID som överförts till en datakälla för olika enheter inte längre realiseras mot enhets-ID.  Tidigare arbetade Audience Manager både med korsenhets-ID (eller CRM-ID) och kopierade dessa implementeringar till associerade Audience Manager UID (enhets-ID).  Ändringen gjordes för att mer exakt återspegla karaktären på de trait-data och profiler som realiseras.

Om du vill visa implementeringar av trait väljer du alternativet&quot;Cross-Device ID&quot; i listrutan i det övre högra hörnet av svällningsvyn.

![Visa realisationer efter enhets-ID](assets/deviceid-crossdevice.png)