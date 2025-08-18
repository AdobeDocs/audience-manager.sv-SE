---
description: Audience Manager använder distribuerade, avancerade datorlösningar för att möta de krav som externa källor ställer på våra system.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Förstå Edge datacenter
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Förstå Edge datacenter{#understanding-the-edge-data-center}

Audience Manager använder distribuerade, avancerade datorlösningar för att möta de krav som externa källor ställer på våra system.

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge datoranvändning ger bättre prestanda som svar på diffus, Internet-omfattande efterfrågan eftersom själva &quot;edge&quot; är en global gräns. Det innebär att [!DNL Audience Manager] dynamiskt placerar bearbetningen närmast efterfrågekällorna och returnerar data med den kortaste möjliga sökvägen. Edge datoranvändning bidrar till att upprätthålla webbplatsens prestanda, vilket i sin tur bevarar användarupplevelsen på webbplatsen. edge-datacentret är en nyckelgateway för att flytta data in och ut från [!DNL Audience Manager].

Datacentret för kanten [!DNL Audience Manager] innehåller:

* **Kärnservrar:** De här är de viktigaste [!DNL Audience Manager] systemen. De uppdaterar och tillhandahåller data till edge-servrarna.

* **Edge-servrar:** Det här är oftast program- och/eller webbservrar. De sitter vid gränsen mellan [!DNL Audience Manager] och Internet. Edge-servrar, som [!DNL DCS]- eller Akamai-system, hanterar vanligtvis data och förfrågningar som flödar in i och ut från [!DNL Audience Manager].

* **Belastningsutjämnare:** Hantera ojämna datoranvändnings-/bearbetningskrav som är inbyggda i Internet-program. Dessa balanserare förhindrar att serverkluster överbelastas medan andra förblir inaktiva.

I följande diagram visas Audience Manager edge data center-miljö.

![](assets/edge_data_center.png)

## Geografisk fördelning och belastningsfördelning {#geo-dist-balance}

Se avsnittet [!DNL DCS] i [Datainsamlingskomponenter](../../reference/system-components/components-data-collection.md).
