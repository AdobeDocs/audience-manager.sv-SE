---
description: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren – varför?
seo-description: Vi använder inte programmet, men vi ser Javascript-anrop från Audience Manager i Javascript-felsökaren – varför?
seo-title: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren – varför?
solution: Audience Manager
title: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren – varför?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 91%

---

# Vi är inte Audience Manager-kund, men vi kan se Javascript-anropen för Audience Manager på vår webbplats

## Fråga

Vi använder inte Adobe Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren.

Varför händer det?

## Svar

Det är troligt att egenskapen ni kör [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) på webbplatsen. Om så är fallet behöver inte referensen till Audience Manager innebära att webbplatsen kör Audience Manager. Det innebär i stället att Audience Manager driver tjänsten.

Audience Manager-serveranrop görs vanligtvis för att [synkronisera kund-ID:n](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html).
