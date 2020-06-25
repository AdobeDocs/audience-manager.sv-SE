---
description: Beskriver komponenterna i ett Audience Manager-segment, de uttryck som används för att ange kriterier för målgruppskvalifikation och hur data överförs i ett händelseanrop.
seo-description: Beskriver komponenterna i ett Audience Manager-segment, de uttryck som används för att ange kriterier för målgruppskvalifikation och hur data överförs i ett händelseanrop.
seo-title: Signaler, egenskaper och segment
solution: Audience Manager
title: Signaler, egenskaper och segment
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---


# [!UICONTROL Signals], [!UICONTROL Traits]och [!UICONTROL Segments] {#signals-traits-and-segments}

Beskriver komponenterna i ett [!DNL Audience Manager] [!UICONTROL segment]projekt, de uttryck som används för att ange kriterier för målgruppskvalifikation och hur data överförs i ett händelseanrop.

## Disposition och syfte

[!DNL Audience Manager] uppgifterna består av [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]och tillhörande kvalificeringsregler. Dataelementen och reglerna kombineras för att skapa [!UICONTROL segments]. [!UICONTROL Segments] ordna besökare i relaterade grupper. I följande tabell definieras de tre huvudkomponenterna i en [!DNL Audience Manager][!UICONTROL segment].

| Element | Innehåller | Exempel |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] är de minsta dataenheterna i [!DNL Audience Manager] och uttrycks som [nyckelvärdepar](../reference/key-value-pairs-explained.md).<br><br><ul><li>Nyckeln är en konstant som definierar en datauppsättning (t.ex. kön, färg, pris).</li><li>Värdet är en variabel som är relaterad till konstanten (t.ex. man/kvinna, grön, 100).</li></ul>Jämförelseoperatorer kopplar nyckelvärdepar och anger relationen mellan dem. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Kombinationer av en eller flera [!UICONTROL signals].<br><br> [!DNL Boolean] uttryck och jämförelseoperatorer gör att du kan skapa [!UICONTROL trait] kvalificeringsregler. <br><br>Skapa exakta kvalificeringskrav med kombinationer av [!UICONTROL traits] och [!UICONTROL trait] grupper. | Från det tillgängliga [!UICONTROL signals]kan du skapa en `High End Camera Browser` regel som uttrycks som: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Användare som delar en uppsättning gemensamma attribut och är kvalificerade för relaterade [!UICONTROL traits]. [!DNL Boolean] -uttryck tillsammans med krav på aktuell frekvens/frekvens gör att du kan skapa [!UICONTROL segment] kvalificeringsregler.<br><br> Skapa exakta kvalificeringskrav med kombinationer av [!UICONTROL trait] och [!UICONTROL segment] regler. | Från den tillgängliga [!UICONTROL traits] och [!UICONTROL signals]den tillgängliga regeln kan du skapa en [!UICONTROL segment] regel som uttrycks som:`(product=camera AND type=digital SLR) OR (price>1000)` |

Använd diagrammet nedan om du vill behålla en mentalanteckning om relationen mellan [!UICONTROL signals], [!UICONTROL traits]och [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Bygg[!UICONTROL Traits]och[!UICONTROL Segment]regler med visuella verktyg och kodredigerare**

Kunderna hanterar [!UICONTROL traits] och [!UICONTROL segments] med visuella verktyg och kodredigerare i [!DNL Audience Manager] användargränssnittet. Med de visuella verktygen kan du skapa regler med hjälp av sökfunktioner, popup-alternativ, nedrullningsbara menyer samt dra och släpp-funktioner. Kodredigerarna ger avancerade användare möjlighet att programmässigt utveckla målgruppssegmenteringskriterier.

**Händelseanrop Skicka data till[!DNL Audience Manager]**

Ett eventsamtal skickar data från din webbplats till [!DNL Audience Manager]. Samtalet innehåller [!UICONTROL signal], [!UICONTROL trait]och [!UICONTROL segment] data i en [!DNL HTTP] begäran. Själva händelsen är allt efter `/event` delen av en [!DNL URL] sträng. Som visas i exemplet nedan kräver den här processen endast ett enda händelseanrop för att skicka flera variabler till [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segment: Syfte, komposition och regler](../features/segments/segments-purpose.md)

