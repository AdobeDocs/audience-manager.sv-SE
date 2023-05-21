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
source-wordcount: '297'
ht-degree: 9%

---

# DCS API:er för överföring av data från server till server{#dcs-apis-for-server-to-server-data-transfers}

Server-till-server ([!UICONTROL S2S]) [!DNL API]tillhandahåller kod och metoder som gör att du kan skicka och ta emot [!DNL DCS] användardata och arbeta med den här informationen i dina egna system eller tillämpningar.

## Vanliga användningsfall {#common-use-cases}

[!UICONTROL Server-to-server] överföringar kan hjälpa er att anpassa landningssidor eller andra interaktioner utifrån besökarnas intressen. Några vanliga användningsområden:

* Personalisering på plats: Skräddarsy besökarens upplevelse på webbplatsen genom att dynamiskt lägga till relevant innehåll och uppmaningar till åtgärder baserat på de segment som de tillhör.
* Förbättra kundservicen: Importera [!DNL Audience Manager] segment i [!DNL CRM] eller andra system via en server-till-server-dataöverföring. Dessa data kan tillhandahålla samtalstjänster eller onlinechattoperatorer med relevant, personlig information om en kund.

## Krav: Användar-ID och regionala servernamn {#requirements}

The [!UICONTROL DCS API] kräver användar-ID:n och region-ID:n för att validera och göra dataförfrågningar.

* Användar-ID krävs eftersom du måste koppla data till en viss besökare.
* Regionens ID krävs för att koppla samtal tillbaka till ett servernamn och eftersom användardata lagras i datacenter som är geografiskt närmast webbplatsens besökare.

## Komma igång {#getting-started}

Handboken beskriver för närvarande hur du:

* Hämta användar-ID:n och region-ID:n från [!DNL DCS] filer som du redan får som [!DNL Audience Manager] kund.

* Hämta användar-ID:n och region-ID:n om du använder [!DNL Visitor ID Service].
* Ring [!DNL DCS] efter att du har användar-ID och region-ID.

Vi lägger till nya metoder när de blir tillgängliga. Gå till följande avsnitt för att komma igång.

* [Hämta användar-ID:n och regioner från ett DCS-svar](dcs-aam-ids.md)
* [Hämta användar-ID:n och regioner via Experience Cloud-ID..](dcs-mcid-ids.md)
* [Göra DCS API-anrop från server till server](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [API-referens för DCS ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

