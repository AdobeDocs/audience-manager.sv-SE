---
description: Instant Cross-Device Suppression är möjligheten att undertrycka användare på flera enheter som är anslutna till dem när en viss upplevelse inträffar på någon av dessa enheter. Använd funktionen för direkt undertryckning mellan enheter för att leverera en enhetlig upplevelse på olika enheter till användarna. Den här upplevelsen blir möjlig tack vare segmenteringsfunktionerna i realtid i Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Omgående enhetsövergripande undertryckning
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---

# Omgående enhetsövergripande undertryckning {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] är möjligheten att undertrycka användare på flera enheter som är anslutna till dem när en viss upplevelse inträffar på någon av dessa enheter. Använd [!UICONTROL Instant Cross-Device Suppression] möjlighet att leverera en enhetlig upplevelse på olika enheter till användarna. Den här upplevelsen blir möjlig tack vare segmenteringsfunktionerna i realtid i Audience Manager.

## Översikt {#overview}

[!UICONTROL Instant Cross-Device Suppression] har två viktiga användningsområden: förbättrad användarupplevelse och mediaeffektivitet.

* **En förbättrad användarupplevelse**: Användare som redan har köpt produkten eller tjänsten kommer inte att se samma alternativ som före köpet. I stället kan ni visa merförsäljning eller korsförsäljningsmeddelanden för produkter eller tjänster som ni vet att de inte har köpt.
* **Medieeffektivitet**: Optimera kampanjutgifterna genom att använda ett globalt frekvenstak för alla [!DNL DSP]s. Frekvensbegränsningen kan användas i realtid för flera enheter som tillhör en användare.

De tekniska detaljerna för segmenteringen i realtid beskrivs i detalj i [Regler för profilsammanslagning och icke-segmenteringsprocesser för enheter](merge-rule-unsegment.md). Läs vidare för det praktiska genomförandet av de användningsfall som beskrivs ovan.

## Använd inte som mål när du har konverterat {#do-not-target-once}

Kontrollera att dina användare som redan har konverterat (köpt en produkt, köpt en prenumeration osv.) kommer inte att se samma meddelande som före konverteringen. Du kan få detta med [!UICONTROL AND NOT] logik, enligt följande.

1. Skapa ett segment med två egenskaper och använd [!UICONTROL AND NOT] logik, vilket visas i bilden nedan. Du måste använda en regelbaserad egenskap för att definiera konverteringshändelsen för det segment som ska aktiveras i realtid. Läs mer om hur [skapa regelbaserade egenskaper](../traits/create-onboarded-rule-based-traits.md).
2. Mappa segmentet till valfritt antal server-till-server-mål i realtid. Läs vidare om hur du lägger till segment i [server-till-server-mål](../destinations/add-edit-segments.md).

Dina besökare är kvalificerade för segmentet så länge de inte har konverterat. Så fort de kvalificerar sig för konverteringsegenskapen upphör de att följa segmentregeln och tas omedelbart bort från segmentet.

![](assets/and_not_use_case.png)

## Använd inte mål efter x-exponeringar {#do-not-target-after-x}

Du kan se till att du inte översvämmar dina användare med samma kreativa funktioner genom att ställa in kontroller för senaste och frekvens. I det här scenariot skapar du ett segment med två egenskaper, vilket beskrivs i stegen nedan.

1. Skapa ett segment med två egenskaper och använd [!UICONTROL AND] logik, vilket visas i bilden nedan. Du måste använda en regelbaserad trait för att definiera den intryckshändelse som ska utlösas i realtid. Läs mer om hur [skapa regelbaserade egenskaper](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Du kan använda [!UICONTROL Actionable Log Files] eller [!UICONTROL Pixel Calls] för att skapa egenskaper baserat på användarnas intryck. Läs mer om [Åtgärdsbara loggfiler](../../integration/media-data-integration/actionable-log-files.md) och [Pixelanrop](../../integration/media-data-integration/impression-data-pixels.md).
2. Använd frekvenskontroller på det andra tradet. Om du vill kan du även lägga till nya kontroller. Läs mer om [hur du använder kontroller för aktuell frekvens och frekvens](../segments/recency-and-frequency.md).
3. Mappa segmentet till valfritt antal server-till-server-mål i realtid. Läs vidare om hur du lägger till segment i [server-till-server-mål](../destinations/add-edit-segments.md).

I det här scenariot kommer användarna att tas bort från segmentet när de har samlat in mer än tre exponeringar och de kommer inte att se just det här kreativa.

![](assets/impressions_use_case.png)

## Viktiga aspekter att anteckna - Bearbetning {#processing-notes}

Tänk på följande när det gäller bearbetning:

* För att segmenteringen i realtid ska fungera måste du mappa önskade segment till servermål i realtid.
* För enheter som är anslutna till en enhet via en [enhetsdiagram](profile-link-use-case.md#recommendations)använder vi en gräns på fyra enheter för utvärdering och osegmentering. Denna begränsning beskrivs i [Alternativ för enhetsdiagram och osegmentering av enheter](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* Delningskommandot inkluderas i en gruppfil, som skickas till mål var 24:e timme, för flera enheter som är anslutna via enhetsdiagrammet.
* Enheten måste ses i realtid (på [Edge](../../reference/system-components/components-edge.md) för att möjliggöra segmentutvärdering i realtid. För egenskaper som har en [!UICONTROL time-to-live (TTL)]  när egenskapen [!DNL TTL] är uppfyllt, kommer enheten automatiskt att segmenteras upp inom 24 timmar via batchfilen. &#x200B; Läs mer om hur [Ange ett förfallointervall för trait](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Om du använder [!UICONTROL DCS API] till inbyggda regelbaserade egenskaper i realtid kan du aktivera segmentet med [!UICONTROL AND NOT] logik. Läs mer om [skicka data till DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Viktiga aspekter att anteckna - Timing {#timing-notes}

Tänk på följande när det gäller timing:

* Ett segment sparas på [Edge](../../reference/system-components/components-edge.md) under samma tidsperiod som en enhetsprofil lagras på [!UICONTROL Edge], det vill säga 14 dagar sedan den senaste realtidsinteraktionen. Läs mer om datalagring i våra [Vanliga frågor om datalagring](../../faq/faq-privacy.md#data-retention-faq).
* Det tar cirka 24 timmar för den avsegmenterade åtgärden att spridas över [!DNL DCS] regioner. Läs mer om våra [!DNL DCS] regioner [här](../../reference/system-components/components-data-collection.md) och [här](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
