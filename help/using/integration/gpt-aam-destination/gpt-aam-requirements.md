---
description: Du kan skicka kvalificerade segment till DFP antingen via en klient eller via en integration på serversidan. Krav och relaterad information om båda metoderna anges nedan.
seo-description: Du kan skicka kvalificerade segment till DFP antingen via en klient eller via en integration på serversidan. Krav och relaterad information om båda metoderna anges nedan.
seo-title: Krav och metoder för att skicka segment till DFP med Google Publisher-taggar (GPT)
solution: Audience Manager
title: Krav och metoder för att skicka segment till DFP med Google Publisher-taggar (GPT)
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 0%

---


# Krav och metoder för att skicka segment till DFP med Google Publisher-taggar (GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

Du kan skicka kvalificerade segment till [!DNL DFP] antingen via en klient eller via en integration på serversidan. Krav och relaterad information om båda metoderna anges nedan.

## Integrering på klientsidan {#client-side-integration}

För en integrering på klientsidan måste du konfigurera ett [!DNL GPT] mål i Audience Manager. Tänk på följande punkter när du vill konfigurera [!DNL GPT] som mål för Audience Manager:

* **Lägg till[!UICONTROL DIL]:** Distribuera [!UICONTROL Data Integration Library (DIL)] kod på alla sidor som du vill ha som mål. [!UICONTROL DIL] skriver segmentdata och användar-ID:n för Audience Manager till cookies som används [!DNL GPT] för målinriktning.

* **Skapa en[!UICONTROL Cookie Destination]:** [!DNL GPT] måste ställas in som en cookie-baserad destination i Audience Manager.

* **Implementera kod för cookie-kontroll:** Lägg in [!DNL GPT] API-metoden i den `.setTargeting` cookie-kontrollkod [](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)som vi rekommenderar. Den här koden förebygger fel genom att söka efter giltiga AAM-cookies innan `.setTargeting` metoden anropas.

* **Lägg till`AamGpt`funktionen:** Koden hämtar data från Audience Manager-cookies och skickar den till `AamGpt` [!DNL GPT]. Placera [Audience Manager-koden för Google Publisher-taggar](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) högst upp på sidan eller inuti `<head>` kodblocket.

   >[!NOTE]
   >
   >Funktionen är inte nödvändig om du använder din egen kod för att läsa Audience Manager cookie-data. `AamGpt`

* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) ska du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan vara i Raw-format, men varje post måste innehålla Audience Manager `UUID`. Audience Manager kan hämta eller få dessa via [!DNL FTP].

### Endast kvalificerade segment skickas till GPT

Mängden data som skickas till [!DNL GPT] beror på hur många segment en viss användare kvalificerar sig för. Exempel: du skapar 100 Audience Manager-segment. Om en besökare kvalificerar sig för fem av dem skickas endast dessa fem segment till [!DNL GPT] (inte alla 100).

>[!NOTE]
>
>Det finns inga gränser för hur många nyckelvärden som du kan skicka, men begäran [!DNL Google] [!DNL URL] har inte en gräns för hur många tecken som kan accepteras. Se [Ange mål och storlek med GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## Integrering på serversidan {#server-side-integration}

Tala med din Audience Manager-konsult eller kundtjänst om du vill konfigurera en integration på serversidan med [!DNL DFP], med [!DNL GPT]. Du måste ange ditt nätverks-ID och Audience Link-ID för ditt [!DNL DFP] konto.

>[!IMPORTANT]
>
>Om dina webbsidor kör biblioteket [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) måste du använda integreringen på serversidan med Audience Manager. Om du är på [!DNL AMP] och har en klientintegration med [!DNL AMP]måste du migrera till integreringen på serversidan. Kontakta din Audience Manager-konsult eller kundtjänst för att diskutera migrering.

>[!MORELIKETHIS]
>
>* [Referenshandbok för GPT API](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

