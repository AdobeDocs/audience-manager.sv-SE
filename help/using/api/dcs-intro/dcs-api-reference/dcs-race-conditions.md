---
description: Beskriver hur du förhindrar konkurrensförhållanden och DCS-felhantering.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Ansiktsvillkor och felhantering
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Ansiktsvillkor, hastighetsbegränsning och felhantering {#race-conditions-and-error-handling}

Beskriver hur du förhindrar konkurrensförhållanden och [!DNL DCS] felhantering.

## Förhindra utrymmesvillkor {#prevent-race-conditions}

Ett tävlingsvillkor kan uppstå om du skickar flera anrop samtidigt (eller i snabb följd) till [!DNL DCS] innan det slutar svara på de inledande frågorna och skriver data till användarens cookie. Ett konkurrensvillkor är inte önskvärt eftersom det kan vara skadat eller felaktigt skriva över cookie-data. Som en god vana bör du tänka på följande metoder för att undvika det här problemet:

* Ring inte samtidiga samtal, eller anrop i snabb följd, till [!DNL DCS] från samma användare.
* Vänta tills varje svar har kommit tillbaka innan du gör efterföljande anrop.

## Hastighetsbegränsning {#rate-limiting}

Adobe kan införa hastighetsbegränsning om det upptäcker för många DCS API-anrop som kan ha en negativ inverkan på tjänstens tillgänglighet.

Om hastighetsbegränsning är aktiverat kan du få en `429 Too Many Requests` HTTP-svarsstatuskod för dina DCS-anrop. När du får det här HTTP-svaret kan du försöka med API-anropen igen senare.

## Felhantering {#error-handling}

Felhanteringen är begränsad för ogiltiga eller dåligt formade frågor. En ogiltig begäran returnerar ett `HTTP 200 OK`-svar och inga data. Dessutom slutar [!DNL DCS] bearbeta en begäran, raderar trait-data och returnerar ett `HTTP 200 OK`-svar när en användare:

* Spåra inte på Audience Manager- eller partnernivå.
* Kommer från en ogiltig/omarkerad geografisk region.
* Inaktiverar cookies för webbläsare (antingen alla eller tredje part).

Se även [DCS-felkoder, meddelanden och exempel](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
