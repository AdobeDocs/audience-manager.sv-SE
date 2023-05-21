---
description: Översikt över hur du integrerar Google Ad Manager med Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Integrera Google Ad Manager med Google Publisher Tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# Integrera [!DNL Google Ad Manager] (tidigare DFP) med Google Publisher Tags (GPT)

I artiklarna nedan finns en översikt över hur du integrerar [!DNL Google Ad Manager] med Google Publisher Tags (GPT). Du kan använda en integration på serversidan eller konfigurera GPT som ett mål för att skicka segmentdata från Audience Manager till [!DNL Google Ad Manager]. Du får också lära dig hur du importerar [!DNL Google Ad Manager] loggfiler för rapportering i Audience Manager.

* [Krav och metoder för att skicka segment till Google Ad Manager med hjälp av Google Publisher-taggar (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Du kan skicka kvalificerade segment till [!DNL Google Ad Manager] antingen via en klientsida eller via en integration på serversidan. Krav och relaterad information om båda metoderna anges nedan.

* [Skapa en GPT-destination](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Du kan skicka kvalificerade segment till [!DNL Google Ad Manager] via en integrering på klientsidan (webbläsare) eller en integration på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för Google Publisher-taggar i Audience Manager.

* [Ändra API-anropet GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Lägg till en if-sats för att kontrollera om det finns Audience Manager-cookies innan du anropar Google Publisher-taggen .setTargeting-metoden.

* [Audience Manager-kod för Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt är en JavaScript-funktion som läser Audience Manager cookie-data och skickar informationen till Google Publisher-taggar.
