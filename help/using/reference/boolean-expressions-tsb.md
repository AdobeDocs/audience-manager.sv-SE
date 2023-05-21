---
description: I den här artikeln beskrivs hur de booleska uttrycken AND, OR och NOT används i verktygen för Audience Manager.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: Booleska uttryck i traits och Segment Builder
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%

---

# Booleska uttryck i traits och Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

I den här artikeln beskrivs hur de booleska uttrycken AND, OR och NOT används i verktygen för Audience Manager.

<!-- 

c_tb_boolean.xml

 -->

**Booleska uttryck**

Boolesk logik är en förgrening av algebra som använder några grundläggande uttryck (eller operatorer) för att avgöra om en -programsats är true eller false. De vanligaste operatorerna är [!UICONTROL AND], [!UICONTROL OR]och [!UICONTROL NOT]. Kombinationer av dessa uttryck hjälper er att skapa regler för fokuserade egenskaper eller segmentkvalifikationer som är unika för era datakrav. Följande bild visar hur grundläggande booleska uttryck fungerar.

<br>

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>The [!UICONTROL NOT] operatorn använder ett implicit &quot;and&quot;-villkor och skrivs ibland som [!UICONTROL AND NOT].

**Så här använder du booleska uttryck i Trait och Segment Builder**

Du bygger upp regler för egenskaper och segmentkvalifikationer med booleska uttryck. I tabellen nedan beskrivs de allmänna bästa sätten att skapa kvalificeringskriterier med [!UICONTROL AND], [!UICONTROL OR]och [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Uttryck </th> 
   <th colname="col2" class="entry"> Använd den för att skapa </th> 
   <th colname="col3" class="entry"> För att vara berättigad </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OCH</span></b> </p> </td> 
   <td colname="col2"> <p>Små, fokuserade krav på mottagningskvalifikation. </p> </td> 
   <td colname="col3"> <p>Användare <i>måste</i> tillhör alla angivna egenskaper eller segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ELLER</span></b> </p> </td> 
   <td colname="col2"> <p>Omfattande, mindre fokuserade krav på målgruppskvalifikation. </p> </td> 
   <td colname="col3"> <p>Användare <i>kan</i> tillhör angivna egenskaper eller segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>Små, fokuserade krav på mottagningskvalifikation. </p> <p>Användbar när det finns flera villkor som gör det svårt eller ineffektivt att definiera krav på målgruppskvalifikation. Ibland är det enklare att validera mot krav som exkluderar i stället för inkluderar. </p> </td> 
   <td colname="col3"> <p>Användare <i>får inte</i> tillhör en uteslutits egenskap eller ett segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exempel på användningsfall**

The [!UICONTROL AND] är användbar när du enkelt har angett kraven för ditt medlemskap. Anta till exempel att du måste skapa en publik av&quot;dyra kameramarkare&quot;. Med en pixelmodell måste du skapa och placera pixlar för kameror och ett numeriskt prisvärde på sidan. Med sina egenskaper kan du däremot använda booleska operatorer för att hantera båda villkoren (kameror) [!UICONTROL AND] pris). Resultatet är effektiv datainsamling med färre HTTP-anrop, vilket i sin tur hjälper till att bevara användarupplevelsen på webbplatsen.

**[!UICONTROL OR]Exempel på användningsfall**

The [!UICONTROL OR] är användbar när du vill skapa signaler med breda krav på mottagningskvalifikationer. Om du har flera kvalificeringskrav för egenskaper eller segment finns det [!UICONTROL OR] -operatorn utvärderas till true när besökarna på webbplatsen uppvisar *alla* av dessa egenskaper. [!UICONTROL OR] kan vara mest användbart när du snabbt vill skapa en bred publik med kvalificerade webbplatsbesökare.

**[!UICONTROL AND NOT]Exempel på användningsfall**

The [!UICONTROL AND NOT] är användbart när det är enklare att definiera en målgrupp med *exkludering* i stället för *inkludering*. Anta till exempel att du har en försäljning och vill segmentera besökare i kunder som bara tittar på fullprisartiklar. I stället för att skapa en lista över signaler för alla kvalificerade fullpris- eller försäljningspriser kan det vara lättare att kvalificera besökare om de har *not* har sett en försäljningsprisartikel. Detta är administrativt effektivt eftersom du vanligtvis har färre försäljningspriser jämfört med de som erbjuds till fullt pris. Med ett booleskt värde [!UICONTROL NOT], besökare *får inte* uppvisar försäljningssignalen för att vara berättigad till fullprismedlemskap. I motsats till [!UICONTROL AND NOT] är motsatsen till [!UICONTROL AND] Användningsexempel, som visar hur målgruppsmedlemskapet bestäms genom inkludering (dvs. besökaren kvalificerades utifrån två uttryckligen angivna signaler).

>[!MORELIKETHIS]
>
>* [Arbeta med jämförelseoperatorer i TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Åtgärdsordning i TraitBuilder-uttryck](../features/traits/trait-operator-precedence.md)

