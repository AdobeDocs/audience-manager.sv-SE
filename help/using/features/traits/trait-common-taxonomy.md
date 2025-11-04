---
description: I den här artikeln finns en allmän översikt över hur du klassificerar egenskaper med en gemensam taxonomi.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Klassificera egenskaper med en gemensam taxonomi
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# Klassificera egenskaper med en gemensam taxonomi {#classifying-traits-with-a-common-taxonomy}

I den här artikeln finns en allmän översikt över hur du klassificerar egenskaper med en gemensam taxonomi.

## Audience Manager taxonomi

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager]-taxonomin är en valfri funktion som klassificerar egenskaper med enhetliga, logiska och allmänt begripliga namnkonventioner. Det fungerar på plattformsnivå för att säkerställa enhetliga namn i hela ekosystemet [!DNL Audience Manager]. I slutändan är den gemensamma taxonomin utformad för att bättre anpassa vår produkt till branschstandarder när det gäller konsumentintegritet och avanmälningsprocesser.

## Fördelar med Trait Classification

Att göra det möjligt för våra kunder att bygga anpassade segment och datamodeller är avgörande för modellen [!DNL Audience Manager] och för din förmåga att hämta värde från vår plattform. Men det som också krävs är ett robust och skalbart sätt att förmedla information om segment till kunder och partners. Dessutom kräver den här kommunikationen att segmentinformationen delas på ett lättbegripligt och universellt språk samtidigt som du skyddar dina egna varumärke och segmentnamn. Den gemensamma taxonomin [!DNL Audience Manager] tillhandahåller detta språk och denna funktion.

## Taxonomin använder klassificeringskategorier enligt branschstandard

Den gemensamma taxonomin baseras på klassificeringar som har skapats av [!DNL Interactive Advertising Bureau (IAB)]. Mer information om riktlinjer för kvalitetssäkring för nätverk och utbyte finns på [!DNL IAB]webbplatsen[&#x200B; för &#x200B;](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines).

## Taxonomisk organisation

[!DNL Audience Manager]-taxonomin organiserar data i kapslade kategorier som kallas nivåer. Varje kategori kan innehålla upp till tre separata nivåer för dataklassificering. På den högsta nivån grupperar en Tier 1-kategori data i sin mest allmänna form (t.ex. geografi). Efterföljande nivåer ger större specificitet till den högre nivån, allmänna kategorin (t.ex. *geography —> United States —> New York*). Alla kategorier har dock inte tre nivåer, vissa använder bara 2.

## Klassificera egenskaper i datakategorier

Du tilldelar taxonomiska klassificeringar när du skapar eller redigerar egenskaper i [!UICONTROL Add New Trait Wizard] (finns i ***[!UICONTROL Audience Data > Traits]***). Mer information finns i [dokumentationen om att skapa egenskaper](../../features/traits/create-onboarded-rule-based-traits.md).

## Arbeta med taxonomi: Ytterligare överväganden

Om du bestämmer dig för att klassificera egenskaper enligt vår gemensamma taxonomi är det viktigt att komma ihåg:

* Klassificeringen är *valfri*.
* Traits *är inte* tilldelade till en taxonomisk kategori som standard (dvs. traits klassificeras inte som&quot;unknown&quot; eller&quot;uncategoriszed&quot; etc.).
* Traits kan bara tillhöra *en* taxonomiska kategorier (flera klassificeringar och kategoriövergripande klassificeringar tillåts inte).
