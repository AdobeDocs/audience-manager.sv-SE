---
description: Beskriver hur du förhindrar konkurrensförhållanden och DCS-felhantering.
seo-description: Beskriver hur du förhindrar konkurrensförhållanden och DCS-felhantering.
seo-title: Överbelastning och felhantering
solution: Audience Manager
title: Överbelastning och felhantering
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# Överbelastning och felhantering {#race-conditions-and-error-handling}

Beskriver hur du förhindrar konkurrensförhållanden och [!DNL DCS] felhantering.

## Förhindrar att ansiktsvillkor {#prevent-race-conditions}

Ett tävlingsvillkor kan uppstå om du skickar flera anrop samtidigt (eller i snabb följd) till [!DNL DCS] innan det slutar svara på de initiala frågorna och skriver data till användarens cookie. Ett konkurrensvillkor är inte önskvärt eftersom det kan vara skadat eller felaktigt skriva över cookie-data. Som en god vana bör du tänka på följande metoder för att undvika det här problemet:

* Ring inte samtidiga samtal eller samtal i snabb följd till [!DNL DCS] från samma användare.
* Vänta tills varje svar har kommit tillbaka innan du gör efterföljande anrop.

## Felhantering {#error-handling}

Felhanteringen är begränsad för ogiltiga eller dåligt formade frågor. En ogiltig begäran returnerar ett `HTTP 200 OK`-svar och inga data. Dessutom avbryter [!DNL DCS] bearbetningen av en begäran, tar bort trait-data och returnerar ett `HTTP 200 OK`-svar när en användare:

* Spårning på Audience Manager- eller partnernivå är inte längre tillgängligt.
* Kommer från en ogiltig/omarkerad geografisk region.
* Inaktiverar cookies för webbläsare (antingen alla eller tredje part).

Se även [DCS-felkoder, meddelanden och exempel](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).