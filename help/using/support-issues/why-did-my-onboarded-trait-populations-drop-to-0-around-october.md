---
description: Runt den 14 oktober 2019 märkte jag att mina registrerade trait-populationer för diagrammet med enhets-ID hade sjunkit till 0, trots att de var mycket högre förut.
seo-description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-title: Why did my Onboarded trait populations drop to 0 around October 15th?
solution: Audience Manager
title: Varför sjönk mina registrerade trait-populationer till 0 runt den 15 oktober?
feature: Support
exl-id: e93cee15-7d05-4f81-8f14-a3e03f214542
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 100%

---

# Varför sjönk mina registrerade trait-populationer till 0 runt den 15 oktober? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Fråga

Runt den 14 oktober 2019 märkte jag att mina registrerade trait-populationer för diagrammet med enhets-ID hade sjunkit till 0, trots att de var mycket högre förut. Varför hände det?

![Bild på minskning av enhets-ID](assets/device_id_populationdrop.png)

## Svar

Den 15 oktober ändrades reglerna för profilsammanslagning i Audience Manager så att registrerade data som hänför sig till ett CRM ID som överförts till en enhetsövergripande datakälla inte längre motsvarar enhets-ID.  Tidigare arbetade Audience Manager både med enhetsövergripande ID (eller CRM ID) och kopierade dessa till tillhörande Audience Manager UUID (enhets-ID).  Ändringen gjordes för att mer exakt återspegla karaktären hos trait-data och profiler.

Om du vill visa realiserade traits väljer du alternativet Cross-Device ID i listrutan överst till höger i Trait-vyn.

![Visa realiseringar efter enhetsövergripande ID](assets/deviceid-crossdevice.png)
