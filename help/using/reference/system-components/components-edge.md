---
description: Audience Manager använder distribuerade, avancerade datorlösningar för att uppfylla de krav som externa källor ställer på våra system.
seo-description: Audience Manager använder distribuerade, avancerade datorlösningar för att uppfylla de krav som externa källor ställer på våra system.
seo-title: Förstå Edge Data Center
solution: Audience Manager
title: Förstå Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Förstå Edge Data Center{#understanding-the-edge-data-center}

Audience Manager använder distribuerade, avancerade datorlösningar för att uppfylla de krav som externa källor ställer på våra system.

## Grunderna i Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge Computing ger bättre prestanda som svar på diffus, internetomfattande efterfrågan eftersom själva&quot;edge&quot; är en global gräns. Detta innebär [!DNL Audience Manager] att bearbetningen placeras dynamiskt närmast efterfrågekällorna och att data returneras med kortast möjliga sökväg. Med Edge Computing bibehålls webbplatsens prestanda, vilket i sin tur bevarar användarupplevelsen på webbplatsen. edge data center är en nyckelgateway för att flytta in och ut data [!DNL Audience Manager].

I [!DNL Audience Manager] kantdatacentret ingår:

* **Kärnservrar:** Det här är de viktigaste [!DNL Audience Manager] systemen. De uppdaterar och tillhandahåller data till edge-servrarna.

* **Edge-servrar:** Vanligtvis är detta program- och/eller webbservrar. De sitter vid gränsen mellan [!DNL Audience Manager] och Internet. Edge-servrar, som [!UICONTROL DCS] eller Akamai-system, hanterar vanligtvis data och förfrågningar som flödar in i och ut [!DNL Audience Manager].

* **Belastningsutjämnare:** Hantera ojämna krav på datoranvändning och bearbetning i Internet-tillämpningar. Dessa balanserare förhindrar att serverkluster överbelastas medan andra förblir inaktiva.

Följande diagram visar datacentermiljön i Audience Manager edge.

![](assets/edge_data_center.png)

## Geografisk fördelning och belastningsfördelning {#geo-dist-balance}

Se [!UICONTROL DCS] avsnittet i [Datainsamlingskomponenter](../../reference/system-components/components-data-collection.md).
