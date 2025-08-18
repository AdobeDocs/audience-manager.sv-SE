---
description: Audience Manager tagghanteringskomponenter är bland annat klientportalen, Adobe Tag Manager (ersatt till förmån för Adobe Experience Platform Launch), DIL, Akamai och kontrolldatabasen.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management Components
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Tag Management Components{#tag-management-components}

Audience Manager tagghanteringskomponenter är bland annat klientportalen, Adobe Tag Manager (ersatt till förmån för Adobe Experience Platform Tags), DIL, Akamai och kontrolldatabasen.

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

Behållaren [!UICONTROL DIL] hjälper till att distribuera [!DNL Audience Manager]-datainsamlingskod till din webbplats. [!UICONTROL TIM] är den inaktuella hanteraren för tagginfogning. Den används inte längre av [!DNL Audience Manager]. I stället använder du tillägget [!DNL Audience Manager] i [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) för att konfigurera och generera behållarkod som du placerar på sidor i lagret.

## Data Integration Library (DIL) {#dil}

[Datainformationsbiblioteket](../../dil/dil-overview.md) (DIL) är en självständig API-modul som samlar in data från din webbplats. [!UICONTROL DIL] hjälper till att eliminera behovet av att skriva specialkod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata. [!UICONTROL DIL] utför dessa åtgärder automatiskt. Dessutom är [!UICONTROL DIL] kompakt. Det är ett självständigt kodbibliotek som minskar mängden kod som krävs för att samla in information. Slutligen kan [!UICONTROL DIL] hjälpa dig att integrera [!DNL Audience Manager] med andra produkter i [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] använder [Akamai](https://www.akamai.com/us/en/about/) för att lagra och leverera behållarkod från vår egen tagghanteringsplattform, som kallas [!UICONTROL TIM (Tag Insertion Manager)]. Koddistributionen med [!UICONTROL TIM] har fasats ut till förmån för [!DNL Adobe Experience Platform Tags].

## Kontrolldatabas {#control-database}

Kontrolldatabasen:

* Bearbetar klientindata från portalen (till exempel för att skapa egenskaper och mål).
* Överför data till Akamai, som innehåller data som används för att skapa behållarmallen och målpubliceringens iFrame.
* Returnerar data för UI-rapporteringssystem.
