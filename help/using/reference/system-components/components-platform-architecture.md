---
description: Kartan innehåller de större Audience Manager-systemen. Det visar visuellt hur data flödar in i, ut ur och mellan Audience Manager-komponenter.
seo-description: Kartan innehåller de större Audience Manager-systemen. Det visar visuellt hur data flödar in i, ut ur och mellan Audience Manager-komponenter.
seo-title: Dataflödesschema för plattformsarkitektur
solution: Audience Manager
title: Dataflödesschema för plattformsarkitektur
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# Plattformsarkitektur: Dataflödesschema{#platform-architecture-data-flow-map}

Kartan innehåller de större Audience Manager-systemen. Det visar visuellt hur data flödar in i, ut ur och mellan Audience Manager-komponenter.

## Så här läser du den här kartan {#compmap}

<!-- 

c_compmap.xml

 -->

På kartan innehåller den grå rutan [!DNL Audience Manager] system. Vissa komponenter är helt interna och andra sitter vid gränsen mellan [!DNL Audience Manager] och den yttre världen. Som [!DNL Audience Manager]-kund är interna komponenter ofta genomskinliga eller otillgängliga. Men ibland kan ni interagera med dessa system via användargränssnittet eller dataintegreringar. System i kanten av paketet samlar in och skickar data mellan [!DNL Audience Manager] och utsidan av världen.

Färger definierar den typ av data som flödar in och ut ur [!DNL Audience Manager]. Grönt är klientdata, blått är kunddata (personer som besöker er webbplats) och orange är data som används för rapportering.

Systembeskrivningar och sammanfattningar finns i avsnitten [åtgärd](../../reference/system-components/components-data-action.md), [samling](../../reference/system-components/components-data-collection.md), [bearbetning](../../reference/system-components/components-data-processing.md) och [tagghantering](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)
