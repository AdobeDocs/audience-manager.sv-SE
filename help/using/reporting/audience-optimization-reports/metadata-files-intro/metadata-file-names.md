---
description: Namnge metadatafilen för Audience Optimization enligt dessa specifikationer.
seo-description: Namnge metadatafilen för Audience Optimization enligt dessa specifikationer.
seo-title: Namnkonventioner för metadatafiler
solution: Audience Manager
title: Namnkonventioner för metadatafiler
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 7%

---

# Namnkonventioner för metadatafiler{#naming-conventions-for-metadata-files}

Namnge metadatafilen för Audience Optimization enligt dessa specifikationer.

## Syntax- och ID-kategorier {#syntax}

Följande syntax definierar strukturen för ett välformaterat metadatafilnamn. Obs! *kursiv* anger en variabelplatshållare. De andra elementen är konstanter och ändras inte.

**Syntax:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Använd* inte filtillägg i dina metadatafiler (.txt eller andra).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* Mittkomponenten **0** är tekniskt sett överordnat ID, som är ett äldre fält. Värdet ska alltid anges som **0**.
* Det underordnade ID:t kan ha ett värde mellan 1 och 10, beroende på dimensionen. Se nedan:

## Underordnade ID-dimensioner {#child-dimension}

I metadatafilnamnet är det underordnade ID:t en identifierare som klassificerar datatypen i en fil och placerar den i en hierarki. Du kan tagga det underordnade ID:t i filnamnet med följande kategori-ID:

1. Campaign
1. Kreativ
1. Placement
1. Exchange
1. Plats
1. Annonsör (om integreringskoder används i en [datakälla](../../../features/manage-datasources.md#details))
1. Infogningsordning (IO)
1. Vertikalt (dvs. en specifik bransch- eller affärskategori som &quot;datorer&quot;, &quot;bilar&quot;, &quot;fastigheter&quot; osv.)
1. Taktisk
1. Affärsenhet eller varumärke

## Exempel på {#example}

För en Creative-metadatafil kan filnamnet vara 20190115_0_2.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
