---
description: Lär dig mer om komponenterna i ett segment och de uttryck som används för att ange kriterier för målgruppskvalificering. Du kan även hitta information om hur data överförs.
landing-page-description: Lär dig mer om komponenterna i ett segment och de uttryck som används för att ange kriterier för målgruppskvalificering. Du kan även hitta information om hur data överförs.
short-description: Lär dig mer om komponenterna i ett segment och de uttryck som används för att ange kriterier för målgruppskvalificering. Du kan även hitta information om hur data överförs.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Signaler, traits och segment
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 20%

---

# [!UICONTROL Signals], [!UICONTROL Traits] och [!UICONTROL Segments] {#signals-traits-and-segments}

Beskriver komponenterna i en [!DNL Audience Manager] [!UICONTROL segment], uttrycken som används för att ange kvalificeringskriterier för målgrupper och hur data överförs i ett händelseanrop.

## Disposition och syfte

[!DNL Audience Manager]-data består av [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments] och relaterade kvalificeringsregler. Dataelementen och reglerna kombineras för att skapa [!UICONTROL segments]. [!UICONTROL Segments] organiserar webbplatsbesökare i relaterade grupper. Följande tabell definierar de tre huvudkomponenterna i en [!DNL Audience Manager] [!UICONTROL segment].

| Element | Innehåller | Exempel |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] är de minsta dataenheterna i [!DNL Audience Manager] och uttrycks som [nyckelvärdepar](../reference/key-value-pairs-explained.md).<br><br><ul><li>Nyckeln är en konstant som definierar en datauppsättning (till exempel kön, färg, pris).</li><li>Värdet är en variabel som är relaterad till konstanten (t.ex. man/kvinna, grön, 100).</li></ul>Jämförelseoperatorer kopplar nyckelvärdepar och anger relationen mellan dem. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Kombinationer av en eller flera [!UICONTROL signals].<br><br> [!DNL Boolean]-uttryck och jämförelseoperatorer gör att du kan skapa [!UICONTROL trait]-kvalificeringsregler. <br><br>Skapa exakta kvalificeringskrav med kombinationer av [!UICONTROL traits]- och [!UICONTROL trait]-grupper. | Från tillgängliga [!UICONTROL signals] kan du skapa en `High End Camera Browser`-regel uttryckt som: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Användare som delar en uppsättning gemensamma attribut och är kvalificerade för relaterade [!UICONTROL traits]. [!DNL Boolean]-uttryck, tillsammans med krav på aktuell tid/frekvens, gör att du kan skapa [!UICONTROL segment]-kvalificeringsregler.<br><br> Skapa exakta kvalificeringskrav med kombinationer av [!UICONTROL trait]- och [!UICONTROL segment]-regler. | Från tillgängliga [!UICONTROL traits] och [!UICONTROL signals] kan du skapa en [!UICONTROL segment]-regel uttryckt som:`(product=camera AND type=digital SLR) OR (price>1000)` |

Använd diagrammet nedan om du vill behålla en mental anteckning om relationen mellan [!UICONTROL signals], [!UICONTROL traits] och [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Bygg [!UICONTROL Traits] och [!UICONTROL Segment] regler med visuella verktyg och kodredigerare**

Klienterna hanterar [!UICONTROL traits] och [!UICONTROL segments] med visuella verktyg och kodredigerare i användargränssnittet i [!DNL Audience Manager]. Med de visuella verktygen kan du skapa regler med hjälp av sökfunktioner, popup-alternativ, nedrullningsbara menyer samt dra och släpp-funktioner. Kodredigerarna ger avancerade användare möjlighet att programmässigt utveckla målgruppssegmenteringskriterier.

**Händelseanrop Skicka data till[!DNL Audience Manager]**

Ett händelseanrop skickar data från din webbplats till [!DNL Audience Manager]. Anropet innehåller [!UICONTROL signal]-, [!UICONTROL trait]- och [!UICONTROL segment]-data i en [!DNL HTTP]-begäran. Själva händelsen är allt efter `/event`-delen av en [!DNL URL]-sträng. Som visas i exemplet nedan kräver den här processen endast ett enda händelseanrop för att skicka flera variabler till [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segment: Syfte, sammansättning och regler](../features/segments/segments-purpose.md)
