---
description: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren - Varför?
seo-description: Vi använder inte, men vi ser Javascript-anrop från Audience Manager i Javascript-felsökaren - Varför?
seo-title: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren - Varför?
solution: Audience Manager
title: Vi använder inte Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökaren - Varför?
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# Vi är inte en Audience Manager-kund, men se Javascript-anropen för Audience Manager på vår webbplats

## Fråga

Vi använder inte Adobe Audience Manager, men vi ser Javascript-anrop till Audience Manager i Javascript-felsökningsprogrammet.  Varför skulle detta hända?

## Svar

Det är troligt att du kör tjänsten för besöks-ID på din egenskap. Om du gör det refererar AAM-referensen inte nödvändigtvis till egenskapen som kör Audience Manager, men det betyder att Audience Manager faktiskt driver den här tjänsten.

Observera att AAM-anropet vanligtvis görs för att synkronisera Set customer IDs.
