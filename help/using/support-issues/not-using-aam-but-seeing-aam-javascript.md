---
description: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren - Varför?
seo-description: Vi använder inte, men vi ser Javascript-anrop från Audience Manager i Javascript-felsökaren - Varför?
seo-title: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren - Varför?
solution: Audience Manager
title: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren - Varför?
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# Vi är inte en Audience Manager-kund, men se Javascript-anropen för Audience Manager på vår webbplats

## Fråga

Vi använder inte Adobe Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökningsprogrammet.

Varför händer detta?

## Svar

Det är troligt att du kör [Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) på din egendom. Om du är det refererar den här referensen för Audience Manager inte nödvändigtvis till egenskapen som kör Audience Manager. Det innebär i stället att Audience Manager driver den här tjänsten.

Audience Manager-serveranropet görs vanligtvis för att [synkronisera kund-ID:n](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html).
