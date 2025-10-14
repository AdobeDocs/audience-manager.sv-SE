---
description: Instant Cross-Device Suppression är möjligheten att undertrycka användare på flera enheter som är anslutna till dem när en viss upplevelse inträffar på någon av dessa enheter. Använd funktionen för direkt undertryckning mellan enheter för att leverera en enhetlig upplevelse på olika enheter till användarna. Detta blir möjligt tack vare segmenteringsfunktionerna i realtid i Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Direkt undertryckning av olika enheter
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

---

# Direkt undertryckning av olika enheter {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] är möjligheten att inaktivera användare på flera enheter som är anslutna till dem när en viss upplevelse inträffar på någon av dessa enheter. Använd funktionen [!UICONTROL Instant Cross-Device Suppression] för att leverera en enhetlig upplevelse på olika enheter till dina användare. Detta blir möjligt tack vare segmenteringsfunktionerna i realtid i Audience Manager.

## Översikt {#overview}

[!UICONTROL Instant Cross-Device Suppression] har två viktiga användningsexempel: förbättrad användarupplevelse och mediaeffektivitet.

* **En förbättrad användarupplevelse**: Användare som redan har köpt din produkt eller tjänst kommer inte att se samma kreatörer som innan köpet. I stället kan ni visa merförsäljning eller korsförsäljningsmeddelanden för produkter eller tjänster som ni vet att de inte har köpt.
* **Medieeffektivitet**: Optimera kampanjutgifterna genom att använda ett globalt frekvenstak för alla [!DNL DSP]-aktiviteter. Frekvensbegränsningen kan användas i realtid för flera enheter som tillhör en användare.

De tekniska detaljerna om osegmentering i realtid beskrivs i detalj i [Regler för profilsammanslagning och icke-segmenteringsprocesser för enheter](merge-rule-unsegment.md). Läs vidare för det praktiska genomförandet av de användningsfall som beskrivs ovan.

## Använd inte som mål när du har konverterat {#do-not-target-once}

Kontrollera att de användare som redan har konverterat (köpt en produkt, köpt en prenumeration osv.) inte ser samma meddelande som före konverteringen. Du kan hämta detta med hjälp av logiken [!UICONTROL AND NOT] enligt följande.

1. Skapa ett segment med hjälp av två egenskaper och använd logiken [!UICONTROL AND NOT], som visas i bilden nedan. Du måste använda en regelbaserad egenskap för att definiera konverteringshändelsen för det segment som ska aktiveras i realtid. Läs mer om hur du [skapar regelbaserade egenskaper](../traits/create-onboarded-rule-based-traits.md).
2. Mappa segmentet till valfritt antal server-till-server-mål i realtid. Läs vidare om hur du lägger till segment till [server-till-server-mål](../destinations/add-edit-segments.md).

Dina besökare är kvalificerade för segmentet så länge de inte har konverterat. Så fort de kvalificerar sig för konverteringsegenskapen upphör de att följa segmentregeln och tas omedelbart bort från segmentet.

![](assets/and_not_use_case.png)

## Använd inte mål efter x-exponeringar {#do-not-target-after-x}

Du kan se till att du inte översvämmar dina användare med samma kreativa funktioner genom att ställa in kontroller för senaste och frekvens. I det här scenariot skapar du ett segment med två egenskaper, vilket beskrivs i stegen nedan.

1. Skapa ett segment med hjälp av två egenskaper och använd logiken [!UICONTROL AND], som visas i bilden nedan. Du måste använda en regelbaserad trait för att definiera den intryckshändelse som ska utlösas i realtid. Läs mer om hur du [skapar regelbaserade egenskaper](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Du kan använda [!UICONTROL Actionable Log Files] eller [!UICONTROL Pixel Calls] för att skapa egenskaper baserat på användarexponeringar. Läs mer om [Aktiverbara loggfiler](../../integration/media-data-integration/actionable-log-files.md) och [Pixelanrop](../../integration/media-data-integration/impression-data-pixels.md).
2. Använd frekvenskontroller på det andra tradet. Om du vill kan du även lägga till nya kontroller. Läs mer om [hur du använder kontroller för senaste och frekvens](../segments/recency-and-frequency.md).
3. Mappa segmentet till valfritt antal server-till-server-mål i realtid. Läs vidare om hur du lägger till segment till [server-till-server-mål](../destinations/add-edit-segments.md).

I det här scenariot kommer användarna att tas bort från segmentet när de har samlat in mer än tre exponeringar och de kommer inte att se just det här kreativa.

![](assets/impressions_use_case.png)

## Viktiga aspekter att anteckna - Bearbetning {#processing-notes}

Tänk på följande när det gäller bearbetning:

* För att segmenteringen i realtid ska fungera måste du mappa önskade segment till servermål i realtid.
* För enheter som är anslutna till en enhet med ett [enhetsdiagram](profile-link-use-case.md#recommendations) tillämpar vi en gräns på fyra enheter för utvärdering och segmentering. Den här begränsningen beskrivs i [Alternativ för enhetsgrafik och Osegmentering av enhet](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* Delningskommandot inkluderas i en gruppfil, som skickas till mål var 24:e timme, för flera enheter som är anslutna via enhetsdiagrammet.
* Enheten måste ses i realtid (på [Edge](../../reference/system-components/components-edge.md)) för att aktivera segmentutvärdering i realtid. För egenskaper som har [!UICONTROL time-to-live (TTL)] när trait [!DNL TTL] är uppfyllt, kommer enheten automatiskt att segmenteras upp inom 24 timmar via batchfilen. &#x200B;. Läs mer om hur du [anger ett förfallointervall för trait &#x200B;](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Om du använder [!UICONTROL DCS API] för inbyggda regelbaserade egenskaper i realtid kan du utlösa segmentet med hjälp av logiken [!UICONTROL AND NOT]. Läs mer om att [skicka data till DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Viktiga aspekter att anteckna - Timing {#timing-notes}

Tänk på följande när det gäller timing:

* Ett segment lagras på [Edge](../../reference/system-components/components-edge.md) under samma tidsperiod som en enhetsprofil lagras på [!UICONTROL Edge], det vill säga 14 dagar sedan den senaste realtidsinteraktionen. Läs mer om datalagring i våra [Vanliga frågor om datalagring](../../faq/faq-privacy.md#data-retention-faq).
* Det tar cirka 24 timmar för den avsegmenterade åtgärden att spridas över [!DNL DCS] regioner. Läs mer om våra [!DNL DCS] regioner [här](../../reference/system-components/components-data-collection.md) och [här](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
