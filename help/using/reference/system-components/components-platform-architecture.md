---
description: Kartan innehåller de större Audience Manager-systemen. Det visar visuellt hur data flödar in i, ut ur och mellan Audience Manager-komponenter.
seo-description: Kartan innehåller de större Audience Manager-systemen. Det visar visuellt hur data flödar in i, ut ur och mellan Audience Manager-komponenter.
seo-title: Platform Architecture Data Flow Map
solution: Audience Manager
title: Platform Architecture Data Flow Map
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 2%

---


# Plattformsarkitektur: Dataflödesschema{#platform-architecture-data-flow-map}

Kartan innehåller de större Audience Manager-systemen. Det visar visuellt hur data flödar in i, ut ur och mellan Audience Manager-komponenter.

## How to read this map {#compmap}

<!-- 

c_compmap.xml

 -->

På kartan innehåller den grå rutan [!DNL Audience Manager] system. Vissa komponenter är helt interna och andra sitter på gränsen mellan [!DNL Audience Manager] och omvärlden. Som [!DNL Audience Manager] kund är interna komponenter ofta transparenta eller otillgängliga. Men ibland kan ni interagera med dessa system via användargränssnittet eller dataintegreringar. Systemen på kanten av paketet samlar in och skickar data mellan [!DNL Audience Manager] och utanför världen.

Färger definierar den typ av data som flödar in och ut [!DNL Audience Manager]. Grönt är klientdata, blått är kunddata (personer som besöker er webbplats) och orange är data som används för rapportering.

Systembeskrivningar och sammanfattningar finns i avsnitten om [dataåtgärd](../../reference/system-components/components-data-action.md), [insamling](../../reference/system-components/components-data-collection.md), [bearbetning](../../reference/system-components/components-data-processing.md)och [tagghantering](../../reference/system-components/components-tag-management.md) .

![](assets/flowmap.png)

