---
description: Konceptuell information, beskrivningar och definitioner för DCS API-kod, metoder och processer.
seo-description: Konceptuell information, beskrivningar och definitioner för DCS API-kod, metoder och processer i Adobe Audience Manager (AAM).
seo-title: API-referens för DCS i Adobe Audience Manager (AAM)
title: Översikt över API-referens för DCS
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 13%

---


# Översikt över API-referens för DCS

Konceptuell information, beskrivningar och definitioner för [!DNL DCS API] kod, metoder och processer.

* [DCS API-metoder](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Skicka data till [!DNL DCS API] med GET- eller POST-metoder.

* [Felkoder, meddelanden och exempel för DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Felkoder och meddelanden som genereras av datainsamlingsservrarna (DCS) listas i numerisk ordning efter kod-ID.

* [ID-övervakning och Blockeringslistning](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS övervakar ID:n som tas emot och lägger till ID:n som skickas med en ovanligt hög hastighet under en kort tidsperiod till blockeringslista.

* [ID:n för DCS-regioner, -platser och -värdnamn](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Det regionala DCS-servervärdnamnet krävs för att anropa DCS. Detta beror på att DCS lagrar information i datacenter som ligger geografiskt nära besökarna. Dina frågor fungerar om du skickar dem till fel DCS, men dessa samtal är ineffektiva och kan fördröja svaret. Om du vill göra en DCS-begäran måste du matcha region-ID:t med motsvarande regionalt värdnamn och skapa frågan med rätt värdnamn.

* [Formatera nyckelvärdespar i DCS-anrop](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   När DCS anropar tar det emot nyckelvärdesdata i standard- eller serialiserat format. I det här avsnittet finns information om hur du formaterar standarddata och serialiserade nyckelvärdesdata.

* [Överbelastning och felhantering](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Beskriver hur du förhindrar konkurrensförhållanden och DCS-felhantering.

* [Attribut som stöds för DCS API-anrop](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Visar och beskriver syntaxen och de attribut (eller nyckelvärdepar) som stöds och som du kan skicka in till datainsamlingsservrarna (DCS). Den här informationen kan hjälpa dig att formatera dina DCS-begäranden och förstå de parametrar som returneras av systemet.
