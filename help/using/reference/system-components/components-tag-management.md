---
description: Bland komponenterna för Audience Manager-tagghantering finns klientportalen, Adobe Tag Manager (borttaget till förmån för Adobe Dynamic Tag Manager och Adobe Experience Platform Launch), DIL, Akamai och kontrolldatabasen.
seo-description: Bland komponenterna för Audience Manager-tagghantering finns klientportalen, Adobe Tag Manager (borttaget till förmån för Adobe Dynamic Tag Manager och Adobe Experience Platform Launch), DIL, Akamai och kontrolldatabasen.
seo-title: Tagghanteringskomponenter
solution: Audience Manager
title: Tagghanteringskomponenter
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Tagghanteringskomponenter{#tag-management-components}

Bland komponenterna för Audience Manager-tagghantering finns klientportalen, Adobe Tag Manager (borttaget till förmån för Adobe Dynamic Tag Manager och Adobe Experience Platform Launch), DIL, Akamai och kontrolldatabasen.

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

Behållaren [!UICONTROL DIL] hjälper dig att distribuera [!DNL Audience Manager] datainsamlingskod till din webbplats. [!UICONTROL TIM] är den borttagna taggiginfogningshanteraren. Den används inte längre av [!DNL Audience Manager]. I stället använder du [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) eller [!DNL Audience Manager] tillägget i [Adobe Experience Platform Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) för att konfigurera och generera behållarkod som du placerar på sidorna i lagret. Behållaren fungerar [!UICONTROL DTM] med [!UICONTROL Data Information Library (DIL)] för att samla in data från din webbplats och skicka den till [!DNL Audience Manager].

## Dataintegreringsbibliotek (DIL) {#dil}

DIL ( [Data Information Library](../../dil/dil-overview.md) ) är en självständig API-modul som samlar in data från din webbplats. [!UICONTROL DIL] hjälper till att eliminera behovet av att skriva särskild kod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata. [!UICONTROL DIL] utför dessa åtgärder automatiskt. Dessutom [!UICONTROL DIL] är komprimerad. Det är ett självständigt kodbibliotek som minskar mängden kod som krävs för att samla in information. Äntligen [!UICONTROL DIL] kan ni integrera [!DNL Audience Manager] med andra produkter i [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] använder [Akamai](https://www.akamai.com/html/about/index.html) för att hantera och leverera behållarkod från vår egen tagghanteringsplattform, som kallas [!UICONTROL TIM (Tag Insertion Manager)]. Koddistributionen med [!UICONTROL TIM] har fasats ut till förmån för [!DNL Adobe Dynamic Tag Management] och [!DNL Adobe Experience Platform Launch].

## Kontrolldatabas {#control-database}

Kontrolldatabasen:

* Bearbetar klientindata från portalen (till exempel för att skapa egenskaper och mål).
* Överför data till Akamai, som innehåller data som används för att skapa behållarmallen och målpubliceringens iFrame.
* Returnerar data för UI-rapporteringssystem.

