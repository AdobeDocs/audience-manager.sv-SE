---
description: Du kan skicka kvalificerade segment till Google Ad Manager antingen via en klient eller via en integrering på serversidan. Krav och relaterad information om båda metoderna anges nedan.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Krav och metoder för att skicka segment till Google Ad Manager med Google Publisher Tags (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Krav och metoder för att skicka segment till Google Ad Manager med hjälp av GPT (Google Publisher Tags) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Du kan skicka kvalificerade segment till [!DNL Google Ad Manager] (tidigare DFP) antingen via en klient eller via en integration på serversidan. Krav och relaterad information om båda metoderna anges nedan.

## Integrering på klientsidan {#client-side-integration}

För en integrering på klientsidan måste du konfigurera ett [!DNL GPT]-mål i Audience Manager. Tänk på följande när du vill konfigurera [!DNL GPT] som ett Audience Manager-mål:

* **Lägg till [!UICONTROL DIL]:** Distribuera [!UICONTROL Data Integration Library (DIL)]-kod på alla sidor som du vill ha som mål. [!UICONTROL DIL] skriver Audience Manager segmentdata och användar-ID till cookies som används av [!DNL GPT] för målinriktning.

* **Skapa ett [!UICONTROL Cookie Destination]:** [!DNL GPT] måste konfigureras som ett cookie-baserat mål i Audience Manager.

* **Implementera kod för cookie-kontroll:** Lägg in API-metoden [!DNL GPT] `.setTargeting` i den rekommenderade [koden för cookie-kontroll](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Den här koden förebygger fel genom att söka efter giltiga AAM-cookies innan metoden `.setTargeting` anropas.

* **Lägg till `AamGpt`-funktionen:** Koden `AamGpt` hämtar data från Audience Manager-cookies och skickar den till [!DNL GPT]. Placera [Audience Manager-koden för Google Publisher-taggar](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) högst upp på sidan eller inuti `<head>`-kodblocket.

  >[!NOTE]
  >
  >Funktionen `AamGpt` krävs inte om du använder din egen kod för att läsa Audience Manager cookie-data.

* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) kan du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan ha Raw-format, men varje post måste innehålla Audience Manager `UUID`. Audience Manager kan hämta dessa via [!DNL FTP].

### Endast kvalificerade segment skickas till GPT

Mängden data som skickas till [!DNL GPT] beror på hur många segment en viss användare kvalificerar sig för. Exempel: du skapar 100 Audience Manager-segment. Om en webbplatsbesökare kvalificerar sig för fem av dem skickas endast dessa fem segment till [!DNL GPT] (inte alla 100).

>[!NOTE]
>
>Det finns inga gränser för hur många nyckelvärden som du kan skicka, men [!DNL Google]-begäran [!DNL URL] har inga gränser för hur många tecken som kan accepteras. Se [Ange mål och storlek med GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Integrering på serversidan {#server-side-integration}

Kontakta din Audience Manager-konsult eller kundtjänst om du vill konfigurera en integration på serversidan med [!DNL Google Ad Manager], med [!DNL GPT]. Du måste ange ditt nätverks-ID för [!DNL Google Ad Manager]-kontot och ditt mållänk-ID.

>[!IMPORTANT]
>
>Om dina webbsidor kör biblioteket [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) måste du använda integreringen på serversidan med Audience Manager. Om du är på [!DNL AMP] och har en klientintegration med [!DNL AMP] måste du migrera till serversidans integrering. Kontakta din Audience Manager-konsult eller kundtjänst för att diskutera migrering.

>[!MORELIKETHIS]
>
>* [Referenshandbok för GPT-API](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)
