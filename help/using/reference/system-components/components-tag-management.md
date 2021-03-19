---
description: Bland Audience Manager-tagghanteringskomponenterna finns klientportalen, Adobe Tag Manager (borttagen till förmån för Adobe Dynamic Tag Manager och Adobe Experience Platform Launch), DIL, Akamai och kontrolldatabasen.
seo-description: Bland Audience Manager-tagghanteringskomponenterna finns klientportalen, Adobe Tag Manager (borttagen till förmån för Adobe Dynamic Tag Manager och Adobe Experience Platform Launch), DIL, Akamai och kontrolldatabasen.
seo-title: Tag Management-komponenter
solution: Audience Manager
title: Tag Management-komponenter
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: systemkomponenter
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 5%

---


# Tag Management-komponenter{#tag-management-components}

Bland Audience Manager-tagghanteringskomponenterna finns klientportalen, Adobe Tag Manager (borttagen till förmån för Adobe Dynamic Tag Manager och Adobe Experience Platform Launch), DIL, Akamai och kontrolldatabasen.

<!-- 

c_comptag.xml

 -->

Audience Manager innehåller följande komponenter:

* [Klientportal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-behållare](../../reference/system-components/components-tag-management.md#dil-tim)
* [Datainformationsbibliotek (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Kontrolldatabas](../../reference/system-components/components-tag-management.md#control-database)

## Klientportal {#client-portal}

Klientportalen är det primära användargränssnittet för tagg- och datahantering. Kunderna använder portalen för att arbeta med taggar, bygga egenskaper och segment, konfigurera destinationer och övervaka kampanjresultaten med rapporter.

## DIL/TIM-behållare {#dil-tim}

Med [!UICONTROL DIL]-behållaren kan du distribuera [!DNL Audience Manager] datainsamlingskod till din webbplats. [!UICONTROL TIM] är den borttagna taggiginfogningshanteraren. Den används inte längre av [!DNL Audience Manager]. Använd i stället [Dynamisk tagghantering](https://docs.adobe.com/content/help/sv-SE/dtm/using/dtm-home.html) eller tillägget [!DNL Audience Manager] i [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) för att konfigurera och generera behållarkod som du placerar på sidor i lagret. Behållaren [!UICONTROL DTM] fungerar med [!UICONTROL Data Information Library (DIL)] för att samla in data från din plats och skicka den till [!DNL Audience Manager].

## Data Integration Library (DIL)  {#dil}

[Datainformationsbiblioteket](../../dil/dil-overview.md) (DIL) är en självständig API-modul som samlar in data från din webbplats. [!UICONTROL DIL] hjälper till att eliminera behovet av att skriva särskild kod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata. [!UICONTROL DIL] utför dessa åtgärder automatiskt. Dessutom är [!UICONTROL DIL] kompakt. Det är ett självständigt kodbibliotek som minskar mängden kod som krävs för att samla in information. [!UICONTROL DIL] hjälper dig att integrera [!DNL Audience Manager] med andra produkter i [!DNL Adobe]-Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] använder  [](https://www.akamai.com/us/en/about/) Akamaito som värd och levererar behållarkod från vår egen tagghanteringsplattform, som kallas  [!UICONTROL TIM (Tag Insertion Manager)]. Koddistributionen med [!UICONTROL TIM] har fasats ut till förmån för [!DNL Adobe Dynamic Tag Management] och [!DNL Adobe Experience Platform Launch].

## Kontrolldatabas {#control-database}

Kontrolldatabasen:

* Bearbetar klientindata från portalen (till exempel för att skapa egenskaper och mål).
* Överför data till Akamai, som innehåller data som används för att skapa behållarmallen och målpubliceringens iFrame.
* Returnerar data för UI-rapporteringssystem.

