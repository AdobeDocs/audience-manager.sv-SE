---
description: Konceptuell information, beskrivningar och definitioner för DCS API-kod, metoder och processer.
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: API-referens för DCS - översikt
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 0%

---

# API-referens för DCS - översikt

Konceptuell information, beskrivningar och definitioner för [!DNL DCS API]-kod, metoder och processer.

* [DCS API-metoder](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

  Skicka data till [!DNL DCS API] med GET- eller POST-metoder.

* [Felkoder, meddelanden och exempel för DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

  Felkoder och meddelanden som genereras av datainsamlingsservrarna (DCS) listas i numerisk ordning efter kod-ID.

* [ID-övervakning och Blockeringslistning](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

  DCS övervakar ID:n som tas emot och lägger till ID:n som skickas med en ovanligt hög hastighet under en kort tidsperiod till blockeringslista.

* [DCS-region-ID, -platser och -värdnamn](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

  Det regionala DCS-servervärdnamnet krävs för att anropa DCS. Detta beror på att DCS lagrar information i datacenter som ligger geografiskt nära besökarna. Dina frågor fungerar om du skickar dem till fel DCS, men dessa samtal är ineffektiva och kan fördröja svaret. Om du vill göra en DCS-begäran måste du matcha region-ID:t med motsvarande regionalt värdnamn och skapa frågan med rätt värdnamn.

* [Formatera nyckelvärdepar i DCS-anrop](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

  När DCS anropar tar det emot nyckelvärdesdata i standard- eller serialiserat format. I det här avsnittet finns information om hur du formaterar standarddata och serialiserade nyckelvärdesdata.

* [Ansiktsvillkor och felhantering](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

  Beskriver hur du förhindrar konkurrensförhållanden och DCS-felhantering.

* [Attribut som stöds för DCS API-anrop](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

  Visar och beskriver syntaxen och de attribut (eller nyckelvärdepar) som stöds och som du kan skicka in till datainsamlingsservrarna (DCS). Den här informationen kan hjälpa dig att formatera dina DCS-begäranden och förstå de parametrar som returneras av systemet.
