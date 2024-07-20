---
description: S2S-API:er (Server-to-server) innehåller kod och metoder som gör att du kan skicka och ta emot DCS-användardata och arbeta med den här informationen i dina egna system eller program.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: DCS API:er för överföring av data från server till server
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# DCS API:er för överföring av data från server till server{#dcs-apis-for-server-to-server-data-transfers}

Server-till-server ([!UICONTROL S2S]) [!DNL API] innehåller kod och metoder som gör att du kan skicka och ta emot [!DNL DCS] användardata och arbeta med den här informationen i dina egna system eller program.

## Vanliga användningsfall {#common-use-cases}

[!UICONTROL Server-to-server] överföringar kan hjälpa dig att anpassa landningssidor eller andra interaktioner baserat på besökarens intressen. Några vanliga användningsområden:

* Personalisering på plats: Skräddarsy besökarens upplevelse på er webbplats genom att dynamiskt lägga till relevant innehåll och uppmana till åtgärder baserat på de segment som de tillhör.
* Förbättra kundtjänst: Importera [!DNL Audience Manager] segment till ett [!DNL CRM] eller annat system via en server-till-server-dataöverföring. Dessa data kan tillhandahålla samtalstjänster eller onlinechattoperatorer med relevant, personlig information om en kund.

## Krav: Användar-ID och regionala servernamn {#requirements}

[!UICONTROL DCS API] kräver användar-ID:n och region-ID:n för att validera och göra dataförfrågningar.

* Användar-ID krävs eftersom du måste koppla data till en viss besökare.
* Regionens ID krävs för att koppla samtal tillbaka till ett servernamn och eftersom användardata lagras i datacenter som är geografiskt närmast webbplatsens besökare.

## Komma igång {#getting-started}

Handboken beskriver för närvarande hur du:

* Hämta användar- och region-ID:n från de [!DNL DCS]-filer som du redan får som [!DNL Audience Manager]-kund.

* Hämta användar-ID och region-ID:n om du använder [!DNL Visitor ID Service].
* Anropa [!DNL DCS] efter att du har användar-ID och region-ID.

Vi lägger till nya metoder när de blir tillgängliga. Gå till följande avsnitt för att komma igång.

* [Hämta användar-ID och regioner från ett DCS-svar](dcs-aam-ids.md)
* [Hämta användar-ID:n och regioner via Experience Cloud-ID..](dcs-mcid-ids.md)
* [Göra DCS API-anrop från server till server](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [API-referens för DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
