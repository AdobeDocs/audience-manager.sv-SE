---
description: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren – varför?
seo-description: Vi använder inte programmet, men vi ser Javascript-anrop från Audience Manager i Javascript-felsökaren – varför?
seo-title: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren – varför?
solution: Audience Manager
title: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren – varför?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 100%

---


# Vi är inte Audience Manager-kund, men vi kan se Javascript-anropen för Audience Manager på vår webbplats

## Fråga

Vi använder inte Adobe Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren.

Varför händer det?

## Svar

Det är troligt att egenskapen ni kör [Experience Cloud Identity Service](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html) på webbplatsen. Om så är fallet behöver inte referensen till Audience Manager innebära att webbplatsen kör Audience Manager. Det innebär i stället att Audience Manager driver tjänsten.

Audience Manager-serveranrop görs vanligtvis för att [synkronisera kund-ID:n](https://docs.adobe.com/content/help/sv-SE/id-service/using/id-service-api/methods/setcustomerids.html).
