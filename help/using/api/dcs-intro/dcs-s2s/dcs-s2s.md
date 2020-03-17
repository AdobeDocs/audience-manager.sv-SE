---
description: S2S-API:er (Server-to-server) innehåller kod och metoder som gör att du kan skicka och ta emot DCS-användardata och arbeta med den här informationen i dina egna system eller program.
seo-description: S2S-API:er (Server-to-server) innehåller kod och metoder som gör att du kan skicka och ta emot DCS-användardata och arbeta med den här informationen i dina egna system eller program.
seo-title: DCS API:er för överföring av data från server till server
solution: Audience Manager
title: DCS API:er för överföring av data från server till server
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# DCS API:er för överföring av data från server till server{#dcs-apis-for-server-to-server-data-transfers}

Server-till-server ([!UICONTROL S2S]) [!DNL API]innehåller kod och metoder som gör att du kan skicka och ta emot [!UICONTROL DCS] användardata och arbeta med informationen i dina egna system eller program.

## Vanliga användningsfall {#common-use-cases}

[!UICONTROL Server-to-server] överföringar kan hjälpa er att anpassa landningssidor eller andra interaktioner utifrån besökarnas intressen. Några vanliga användningsområden:

* Personalisering på plats: Skräddarsy besökarens upplevelse på webbplatsen genom att dynamiskt lägga till relevant innehåll och uppmaningar till åtgärder baserat på de segment som de tillhör.
* Förbättra kundservicen: Importera [!DNL Audience Manager] segment till ett [!DNL CRM] eller annat system via en server-till-server-dataöverföring. Dessa data kan tillhandahålla samtalstjänster eller onlinechattoperatorer med relevant, personlig information om en kund.

## Krav: Användar-ID och regionala servernamn {#requirements}

Användar-ID:n och region-ID:n [!UICONTROL DCS API] krävs för att validera och utföra dataförfrågningar.

* Användar-ID krävs eftersom du måste koppla data till en viss besökare.
* Regionens ID krävs för att koppla samtal tillbaka till ett servernamn och eftersom användardata lagras i datacenter som är geografiskt närmast webbplatsens besökare.

## Komma igång {#getting-started}

Handboken beskriver för närvarande hur du:

* Hämta användar-ID:n och region-ID:n från de filer som du redan får som [!UICONTROL DCS] [!DNL Audience Manager] kund.

* Hämta användar-ID:n och region-ID:n om du använder [!DNL Visitor ID Service].
* Ring till [!UICONTROL DCS] när du har användar- och region-ID:t.

Vi lägger till nya metoder när de blir tillgängliga. Gå till följande avsnitt för att komma igång.

* [Hämta användar-ID och regioner från ett DCS-svar](dcs-aam-ids.md)
* [Hämta användar-ID och regioner via Experience Cloud-ID..](dcs-mcid-ids.md)
* [Göra DCS API-anrop från server till server](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [API-referens för DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

