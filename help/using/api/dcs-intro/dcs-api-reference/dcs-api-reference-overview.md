---
description: Konceptuell information, beskrivningar och definitioner för DCS API-kod, metoder och processer.
seo-description: Konceptuell information, beskrivningar och definitioner för DCS API-kod, metoder och processer i Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview i Adobe Audience Manager (AAM)
title: API-referens för DCS - översikt
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---


# API-referens för DCS - översikt

Konceptuell information, beskrivningar och definitioner för DCS API-kod, metoder och processer.

* [DCS API-metoder](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Skicka data till DCS API med GET- eller POST-metoder.

* [Felkoder, meddelanden och exempel för DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Felkoder och meddelanden som genereras av datainsamlingsservrarna (DCS) listas i numerisk ordning efter kod-ID.

* [ID-övervakning och Neka-lista](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS övervakar de ID som tas emot och lägger till de ID som skickas med ett ovanligt högt pris under en kort tidsperiod till en lista över nekade.

* [DCS-region-ID, -platser och -värdnamn](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   Det regionala DCS-servervärdnamnet krävs för att anropa DCS. Detta beror på att DCS lagrar information i datacenter som ligger geografiskt nära besökarna. Dina frågor fungerar om du skickar dem till fel DCS, men dessa samtal är ineffektiva och kan fördröja svaret. Om du vill göra en DCS-begäran måste du matcha region-ID:t med motsvarande regionalt värdnamn och skapa frågan med rätt värdnamn.

* [Formatera nyckelvärdepar i DCS-anrop](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   När DCS anropar tar det emot nyckelvärdesdata i standard- eller serialiserat format. I det här avsnittet finns information om hur du formaterar standarddata och serialiserade nyckelvärdesdata.

* [Ansiktsvillkor och felhantering](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Beskriver hur du förhindrar konkurrensförhållanden och DCS-felhantering.

* [Attribut som stöds för DCS API-anrop](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Visar och beskriver syntaxen och de attribut (eller nyckelvärdepar) som stöds och som du kan skicka in till datainsamlingsservrarna (DCS). Den här informationen kan hjälpa dig att formatera dina DCS-begäranden och förstå de parametrar som returneras av systemet.
