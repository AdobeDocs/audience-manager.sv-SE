---
description: Instant Cross-Device Suppression är möjligheten att undertrycka användare på flera enheter som är anslutna till dem när en viss upplevelse inträffar på någon av dessa enheter. Använd funktionen för direkt undertryckning mellan enheter för att leverera en enhetlig upplevelse på olika enheter till användarna. Den här upplevelsen blir möjlig tack vare segmenteringsfunktionerna i realtid i Audience Manager.
seo-description: Instant Cross-Device Suppression är möjligheten att undertrycka användare på flera enheter som är anslutna till dem när en viss upplevelse inträffar på någon av dessa enheter. Använd funktionen för direkt undertryckning mellan enheter för att leverera en enhetlig upplevelse på olika enheter till användarna. Den här upplevelsen blir möjlig tack vare segmenteringsfunktionerna i realtid i Audience Manager.
seo-title: Direkt undertryckning av olika enheter
title: Direkt undertryckning av olika enheter
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 0%

---


# Direkt undertryckning av olika enheter {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] är möjligheten att undertrycka användare på flera enheter som är anslutna till dem när en viss upplevelse inträffar på någon av dessa enheter. Använd funktionen för att leverera en enhetlig upplevelse på olika enheter till användarna. [!UICONTROL Instant Cross-Device Suppression] Den här upplevelsen blir möjlig tack vare segmenteringsfunktionerna i realtid i Audience Manager.

## Översikt {#overview}

[!UICONTROL Instant Cross-Device Suppression] har två viktiga användningsområden: förbättrad användarupplevelse och mediaeffektivitet.

* **En förbättrad användarupplevelse**: Användare som redan har köpt produkten eller tjänsten kommer inte att se samma alternativ som före köpet. I stället kan ni visa merförsäljning eller korsförsäljningsmeddelanden för produkter eller tjänster som ni vet att de inte har köpt.
* **Medieeffektivitet**: Optimera era kampanjutgifter genom att använda ett globalt frekvenstak för alla [!DNL DSP]kanaler. Frekvensbegränsningen kan användas i realtid för flera enheter som tillhör en användare.

De tekniska detaljerna om osegmentering i realtid beskrivs i detalj i [Profilkopplingsregler och Avsegmenteringsprocesser](merge-rule-unsegment.md)för enheter. Läs vidare för det praktiska genomförandet av de användningsfall som beskrivs ovan.

## Gör inte Target när den har konverterats {#do-not-target-once}

Kontrollera att dina användare som redan har konverterat (köpt en produkt, köpt en prenumeration osv.) kommer inte att se samma meddelande som före konverteringen. Du kan hämta detta med hjälp av [!UICONTROL AND NOT] logiken enligt följande.

1. Skapa ett segment med hjälp av två egenskaper och använd [!UICONTROL AND NOT] logiken som visas i bilden nedan. Du måste använda en regelbaserad egenskap för att definiera konverteringshändelsen för det segment som ska aktiveras i realtid. Läs mer om hur du [skapar regelbaserade egenskaper](../traits/create-onboarded-rule-based-traits.md).
2. Mappa segmentet till valfritt antal server-till-server-mål i realtid. Läs mer om hur du lägger till segment till mål [för](../destinations/add-edit-segments.md)server-till-server.

Dina besökare är kvalificerade för segmentet så länge de inte har konverterat. Så fort de kvalificerar sig för konverteringsegenskapen upphör de att följa segmentregeln och tas omedelbart bort från segmentet.

![](assets/and_not_use_case.png)

## Använd inte Target efter x-bilder {#do-not-target-after-x}

Du kan se till att du inte översvämmar dina användare med samma kreativa funktioner genom att ställa in kontroller för senaste och frekvens. I det här scenariot skapar du ett segment med två egenskaper, vilket beskrivs i stegen nedan.

1. Skapa ett segment med hjälp av två egenskaper och använd [!UICONTROL AND] logiken som visas i bilden nedan. Du måste använda en regelbaserad trait för att definiera den intryckshändelse som ska utlösas i realtid. Läs mer om hur du [skapar regelbaserade egenskaper](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Du kan använda [!UICONTROL Actionable Log Files] eller [!UICONTROL Pixel Calls] för att skapa egenskaper baserat på användarintryck. Läs mer om [loggfiler](../../integration/media-data-integration/actionable-log-files.md) och [pixelanrop](../../integration/media-data-integration/impression-data-pixels.md).
2. Använd frekvenskontroller på det andra tradet. Om du vill kan du även lägga till nya kontroller. Läs mer om [hur du använder frekvenskontroller](../segments/recency-and-frequency.md).
3. Mappa segmentet till valfritt antal server-till-server-mål i realtid. Läs mer om hur du lägger till segment till mål [för](../destinations/add-edit-segments.md)server-till-server.

I det här scenariot kommer användarna att tas bort från segmentet när de har samlat in mer än tre exponeringar och de kommer inte att se just det här kreativa.

![](assets/impressions_use_case.png)

## Viktiga aspekter att anteckna - Bearbetning {#processing-notes}

Tänk på följande när det gäller bearbetning:

* För att segmenteringen i realtid ska fungera måste du mappa önskade segment till servermål i realtid.
* För enheter som är anslutna till en enhet via ett [enhetsdiagram](profile-link-use-case.md#recommendations)tillämpar vi en gräns på fyra enheter för utvärdering och segmentering. Den här begränsningen beskrivs i Alternativ för [enhetsdiagram och Osegmentering](merge-rule-unsegment.md#device-graph-options-unsegmentation)av enheter. &#x200B;
* Delningskommandot inkluderas i en gruppfil, som skickas till mål var 24:e timme, för flera enheter som är anslutna via enhetsdiagrammet.
* Enheten måste ses i realtid (på [Edge](../../reference/system-components/components-edge.md) ) för att segmentutvärderingen ska kunna utföras i realtid. För traits som har en [!UICONTROL time-to-live (TTL)] när trait [!DNL TTL] är uppfyllt, kommer enheten automatiskt att segmenteras inom 24 timmar via batchfilen. &#x200B;. Läs mer om hur du [anger ett förfallointervall](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)för trait.
* Om du använder de inbyggda regelbaserade egenskaperna [!UICONTROL DCS API] i realtid kan du aktivera segmentet med hjälp av [!UICONTROL AND NOT] logiken. Läs mer om [att skicka data till DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Viktiga aspekter att anteckna - Timing {#timing-notes}

Tänk på följande när det gäller timing:

* Ett segment kommer att lagras på [Edge](../../reference/system-components/components-edge.md) under samma tidsperiod som en enhetsprofil lagras på [!UICONTROL Edge], nämligen 14 dagar sedan den senaste realtidsinteraktionen. Läs mer om datalagring i Vanliga frågor om [datalagring](../../faq/faq-privacy.md#data-retention-faq).
* Det tar cirka 24 timmar för den avsegmenterade åtgärden att sprida sig över olika [!DNL DCS] regioner. Läs mer om våra [!DNL DCS] regioner [här](../..//reference/system-components/components-data-collection.md) och [här](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
