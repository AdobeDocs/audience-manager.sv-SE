---
description: Kartan innehåller de större Audience Manager-systemen. Det visar visuellt hur data flödar in i, ut ur och mellan Audience Manager-komponenter.
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Dataflödesschema för plattformsarkitektur
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 2%

---

# Plattformsarkitektur: Dataflödesschema{#platform-architecture-data-flow-map}

Kartan innehåller de större Audience Manager-systemen. Det visar visuellt hur data flödar in i, ut ur och mellan Audience Manager-komponenter.

## Så här läser du den här kartan {#compmap}

<!-- 

c_compmap.xml

 -->

Den grå rutan innehåller [!DNL Audience Manager] system. Vissa komponenter är helt interna och andra sitter på gränsen mellan [!DNL Audience Manager] och världen utanför. Som en [!DNL Audience Manager] kunderna, interna komponenter är ofta transparenta eller otillgängliga. Men ibland kan ni interagera med dessa system via användargränssnittet eller dataintegreringar. System i kanten av paketet samlar in och skickar data mellan [!DNL Audience Manager] och världen utanför.

Färger definierar den typ av data som flödar in och ut ur [!DNL Audience Manager]. Grönt är klientdata, blått är kunddata (personer som besöker er webbplats) och orange är data som används för rapportering.

Systembeskrivningar och sammanfattningar finns i informationen [åtgärd](../../reference/system-components/components-data-action.md), [samling](../../reference/system-components/components-data-collection.md), [bearbetning](../../reference/system-components/components-data-processing.md)och [tagghantering](../../reference/system-components/components-tag-management.md) -avsnitt.

![](assets/flowmap.png)
