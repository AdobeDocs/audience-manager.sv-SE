---
description: Beskriver hur du förhindrar konkurrensförhållanden och DCS-felhantering.
seo-description: Beskriver hur du förhindrar konkurrensförhållanden och DCS-felhantering.
seo-title: Ansiktsvillkor och felhantering
solution: Audience Manager
title: Ansiktsvillkor och felhantering
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ansiktsvillkor och felhantering {#race-conditions-and-error-handling}

Beskriver hur du förhindrar tävlingsförhållanden och [!UICONTROL DCS] felhantering.

## Förhindra utrymmesvillkor {#prevent-race-conditions}

Ett tävlingsvillkor kan uppstå om du skickar flera anrop samtidigt (eller i snabb följd) till användaren [!UICONTROL DCS] innan den slutar svara på de första frågorna och skriver data till användarens cookie. Ett konkurrensvillkor är inte önskvärt eftersom det kan vara skadat eller felaktigt skriva över cookie-data. Som en god vana bör du tänka på följande metoder för att undvika det här problemet:

* Ring inte samtidiga samtal, eller samtal i snabb följd, till [!UICONTROL DCS] användaren.
* Vänta tills varje svar har kommit tillbaka innan du gör efterföljande anrop.

## Felhantering {#error-handling}

Felhanteringen är begränsad för ogiltiga eller dåligt formade frågor. En ogiltig begäran returnerar ett `HTTP 200 OK` svar och inga data. Dessutom [!UICONTROL DCS] avbryts bearbetningen av en begäran, trait-data ignoreras och ett `HTTP 200 OK` svar returneras när en användare:

* Optimerar spårningen på Audience Manager- eller partnernivå.
* Kommer från en ogiltig/omarkerad geografisk region.
* Inaktiverar cookies för webbläsare (antingen alla eller tredje part).

Se även [Felkoder, meddelanden och exempel](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)för DCS.