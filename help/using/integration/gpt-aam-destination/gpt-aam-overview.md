---
description: Översikt över hur du integrerar DFP med Google Publisher Tags (GPT).
seo-description: Översikt över hur du integrerar DFP med Google Publisher Tags (GPT) i Adobe Audience Manager (AAM).
seo-title: Integrera DFP med Google Publisher Tags (GPT) i Adobe Audience Manager (AAM)
title: Integrera DFP med Google Publisher Tags (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---


# Integrera DFP med Google Publisher Tags (GPT)

I artiklarna nedan finns en översikt över hur du integrerar DFP med Google Publisher Tags (GPT). Du kan använda en integration på serversidan eller konfigurera GPT som ett mål för att skicka segmentdata från Audience Manager till DFP. Du får också lära dig hur du importerar DFP-loggfiler för rapportering i Audience Manager.

* [Krav och metoder för att skicka segment till DFP med Google Publisher-taggar (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Du kan skicka kvalificerade segment till DFP antingen via en klient eller via en integration på serversidan. Krav och relaterad information om båda metoderna anges nedan.

* [Skapa ett GPT-mål](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Du kan skicka kvalificerade segment till DFP via en integrering på klientsidan (webbläsarsidan) eller via en integrering på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för Google Publisher-taggar i Audience Manager.

* [Ändra GPT-API-anropet setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Lägg till en if-programsats för att kontrollera om det finns Audience Manager-cookies innan du anropar Google Publisher-taggen .setTargeting-metoden.

* [Audience Manager Code for Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt är en JavaScript-funktion som läser Audience Manager cookie-data och skickar informationen till Google Publisher-taggar.
