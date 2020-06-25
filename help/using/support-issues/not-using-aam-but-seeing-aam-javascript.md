---
description: Vi använder inte Audience Manager, men vi ser Audience Manager Javascript-anrop i Javascript-felsökaren - varför?
seo-description: Vi använder inte, men vi ser Audience Manager Javascript-anrop i Javascript-felsökaren - varför?
seo-title: Vi använder inte Audience Manager, men vi ser Audience Manager Javascript-anrop i Javascript-felsökaren - varför?
solution: Audience Manager
title: Vi använder inte Audience Manager, men vi ser Audience Manager Javascript-anrop i Javascript-felsökaren - varför?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---


# Vi är ingen Audience Manager-kund, men se Audience Manager Javascript-samtalen på vår webbplats

## Fråga

Vi använder inte Adobe Audience Manager, men vi ser Audience Manager Javascript-anrop i Javascript-felsökaren.

Varför händer detta?

## Svar

Det är troligt att du kör [Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) på din egendom. Om du är det refererar den här Audience Manager-referensen inte nödvändigtvis till egenskapen som kör Audience Manager. Istället innebär det att Audience Manager driver denna tjänst.

Serveranropet till Audience Manager görs vanligtvis för att [synkronisera kund-ID](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html).
