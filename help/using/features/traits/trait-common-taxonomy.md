---
description: I den här artikeln finns en allmän översikt över hur du klassificerar egenskaper med en gemensam taxonomi.
keywords: DIL
seo-description: I den här artikeln finns en allmän översikt över hur du klassificerar egenskaper med en gemensam taxonomi.
seo-title: Klassificera egenskaper med en gemensam taxonomi
solution: Audience Manager
title: Klassificera egenskaper med en gemensam taxonomi
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---


# Klassificera egenskaper med en gemensam taxonomi {#classifying-traits-with-a-common-taxonomy}

I den här artikeln finns en allmän översikt över hur du klassificerar egenskaper med en gemensam taxonomi.

## Audience Manager taxonomi

<!-- c_common_taxonomy_about.xml -->

Taxonomin är en valfri funktion som klassificerar egenskaper med hjälp av enhetliga, logiska och allmänt begripliga namnkonventioner. [!DNL Audience Manager] Det fungerar på plattformsnivå för att säkerställa enhetliga namn i hela [!DNL Audience Manager] ekosystemet. I slutändan är den gemensamma taxonomin utformad för att bättre anpassa vår produkt till branschstandarder när det gäller konsumentintegritet och avanmälningsprocesser.

## Fördelar med Trait Classification

Att göra det möjligt för våra kunder att bygga anpassade segment och datamodeller är avgörande för [!DNL Audience Manager] modellen och för er förmåga att hämta in värde från vår plattform. Men det som också krävs är ett robust och skalbart sätt att förmedla information om segment till kunder och partners. Dessutom kräver den här kommunikationen att segmentinformationen delas på ett lättbegripligt och universellt språk samtidigt som du skyddar dina egna varumärke och segmentnamn. Den [!DNL Audience Manager] vanliga taxonomin tillhandahåller detta språk och denna funktion.

## Taxonomin använder klassificeringskategorier enligt branschstandard

Den vanliga taxonomin baseras på de klassificeringar som skapas av [!DNL Interactive Advertising Bureau (IAB)]. Mer information om riktlinjer för kvalitetssäkring för nätverk och utbyte finns på [!DNL IAB]dess [webbplats](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) .

## Taxonomisk organisation

I [!DNL Audience Manager] taxonomin ordnas data i kapslade kategorier som kallas nivåer. Varje kategori kan innehålla upp till tre separata nivåer för dataklassificering. På den högsta nivån grupperar en Tier 1-kategori data i sin mest allmänna form (t.ex. geografi). Efterföljande nivåer ger större specificitet till den högre nivån, allmänna kategorin (t.ex. *geography —> United States —> New York*). Alla kategorier har dock inte tre nivåer, vissa använder bara 2.

## Klassificera egenskaper i datakategorier

Du tilldelar taxonomiska klassificeringar när du skapar eller redigerar egenskaper i [!UICONTROL Add New Trait Wizard] (finns i * **[!UICONTROL Audience Data > Traits]***). Mer information finns i [dokumentationen om hur du skapar egenskaper](../../features/traits/create-onboarded-rule-based-traits.md) .

## Arbeta med taxonomin: Ytterligare överväganden

Om du bestämmer dig för att klassificera egenskaper enligt vår gemensamma taxonomi är det viktigt att komma ihåg:

* Klassificering är *valfritt*.
* Fällor *tilldelas inte* som standard till en taxonomisk kategori (dvs. traits klassificeras inte som&quot;unknown&quot; eller&quot;uncategoriszed&quot; etc.).
* Traits kan tillhöra endast *en* taxonomisk kategori (flera och kategoriövergripande klassificeringar tillåts inte).