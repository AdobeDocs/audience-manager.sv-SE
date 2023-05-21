---
description: Du kan skicka kvalificerade segment till Google Ad Manager antingen via en klient eller via en integrering på serversidan. Krav och relaterad information om båda metoderna anges nedan.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Krav och metoder för att skicka segment till Google Ad Manager med hjälp av Google Publisher-taggar (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Krav och metoder för att skicka segment till Google Ad Manager med hjälp av GPT (Google Publisher Tags) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Du kan skicka kvalificerade segment till [!DNL Google Ad Manager] (tidigare DFP) antingen via en klient eller via en integration på serversidan. Krav och relaterad information om båda metoderna anges nedan.

## Integrering på klientsidan {#client-side-integration}

För en integrering på klientsidan måste du konfigurera en [!DNL GPT] mål i Audience Manager. Tänk på följande när du vill konfigurera [!DNL GPT] som mål för Audience Manager:

* **Lägg till [!UICONTROL DIL]:** Distribuera [!UICONTROL Data Integration Library (DIL)] på alla sidor som du vill ha som mål. [!UICONTROL DIL] skriver segmentdata och användar-ID:n för Audience Manager till cookies som används av [!DNL GPT] för målinriktning.

* **Skapa en [!UICONTROL Cookie Destination]:** [!DNL GPT] måste ställas in som en cookie-baserad destination i Audience Manager.

* **Implementera kod för cookie-kontroll:** Lägg [!DNL GPT] `.setTargeting` API-metod i våra rekommenderade [cookie-kontrollkod](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). Med den här koden kan du förhindra fel genom att söka efter giltiga AAM cookies före `.setTargeting` metoden anropas.

* **Lägg till `AamGpt` Funktion:** The `AamGpt` koden hämtar data från Audience Manager cookies och skickar den till [!DNL GPT]. Placera [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) högst upp på sidan eller i `<head>` kodblock.

   >[!NOTE]
   >
   >The `AamGpt` -funktionen är inte nödvändig om du använder din egen kod för att läsa Audience Manager cookie-data.

* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) ska du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan ha Raw-format, men varje post måste innehålla Audience Manager `UUID`. Audience Manager kan hämta dessa via [!DNL FTP].

### Endast kvalificerade segment skickas till GPT

Mängden data som skickas till [!DNL GPT] beror på hur många segment en viss användare är berättigad till. Exempel: du skapar 100 Audience Manager-segment. Om en besökare kvalificerar sig för fem av dem skickas endast dessa fem segment till [!DNL GPT] (inte alla 100).

>[!NOTE]
>
>Det finns inga gränser för hur många nyckelvärden du kan skicka, men [!DNL Google] förfrågan [!DNL URL] har begränsningar för hur många tecken som kan accepteras. Se [Ange mål och storlek med GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integrering på serversidan {#server-side-integration}

Tala med din Audience Manager-konsult eller kundtjänst om du vill konfigurera en integration på serversidan med [!DNL Google Ad Manager], använda [!DNL GPT]. Du måste ange [!DNL Google Ad Manager] nätverks-ID för konto och publikens länk-ID.

>[!IMPORTANT]
>
>Om dina webbsidor körs på [Accelererade mediesidor](https://www.ampproject.org/) ([!DNL AMP]) måste du använda integreringen på serversidan med Audience Manager. Om du är på [!DNL AMP] och har en integrering på klientsidan med [!DNL AMP]måste du migrera till integreringen på serversidan. Kontakta din Audience Manager-konsult eller kundtjänst för att diskutera migrering.

>[!MORELIKETHIS]
>
>* [Referenshandbok för GPT API](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

