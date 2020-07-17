---
description: I den här artikeln beskrivs hur de booleska uttrycken AND, OR och NOT används i verktygen för Audience Manager.
seo-description: I den här artikeln beskrivs hur de booleska uttrycken AND, OR och NOT används i verktygen för Audience Manager.
seo-title: Booleska uttryck i traits och Segment Builder
solution: Audience Manager
title: Booleska uttryck i traits och Segment Builder
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 3%

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
>Operatorn [!UICONTROL NOT] använder ett underförstått &quot;och&quot;-villkor och skrivs ibland som [!UICONTROL AND NOT].

**Så här använder du booleska uttryck i Trait och Segment Builder**

Du bygger upp regler för egenskaper och segmentkvalifikationer med booleska uttryck. Tabellen nedan beskriver allmänna bästa metoder för att skapa kvalificeringskriterier med [!UICONTROL AND], [!UICONTROL OR]och [!UICONTROL NOT].

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
   <td colname="col3"> <p>Användarna <i>måste</i> tillhöra alla angivna egenskaper eller segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> ELLER</span></b> </p> </td> 
   <td colname="col2"> <p>Omfattande, mindre fokuserade krav på målgruppskvalifikation. </p> </td> 
   <td colname="col3"> <p>Användare <i>kan</i> tillhöra alla angivna egenskaper eller segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>Små, fokuserade krav på mottagningskvalifikation. </p> <p>Användbar när det finns flera villkor som gör det svårt eller ineffektivt att definiera krav på målgruppskvalifikation. Ibland är det enklare att validera mot krav som exkluderar i stället för inkluderar. </p> </td> 
   <td colname="col3"> <p>Användare <i>får inte</i> tillhöra en uteslutits egenskap eller ett uteslutit segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]Exempel på användningsfall **

Operatorn [!UICONTROL AND] är användbar när du enkelt har angett kraven för trait-medlemskap. Anta till exempel att du måste skapa en publik av&quot;dyra kameramarkare&quot;. Med en pixelmodell måste du skapa och placera pixlar för kameror och ett numeriskt prisvärde på sidan. Med sina egenskaper kan du däremot använda booleska operatorer för att hantera båda villkoren ( [!UICONTROL AND] kamerapris). Resultatet är effektiv datainsamling med färre HTTP-anrop, vilket i sin tur hjälper till att bevara användarupplevelsen på webbplatsen.

**[!UICONTROL OR]Exempel på användningsfall **

Operatorn [!UICONTROL OR] är användbar när du vill skapa signaler med breda krav på mottagningskvalifikationer. Om du har flera krav på egenskaper eller segment utvärderas [!UICONTROL OR] operatorn till true när webbplatsbesökarna uppvisar *någon* av dessa egenskaper. [!UICONTROL OR] kan vara mest användbart när du snabbt vill skapa en bred publik med kvalificerade webbplatsbesökare.

**[!UICONTROL AND NOT]Exempel på användningsfall **

Operatorn [!UICONTROL AND NOT] är användbar när det är enklare att definiera en målgrupp genom *uteslutning* i stället för *inkludering*. Anta till exempel att du har en försäljning och vill segmentera besökare i kunder som bara tittar på fullprisartiklar. I stället för att skapa en lista med signaler för alla kvalificerade fullpris- eller försäljningspriser kan det vara lättare att kvalificera besökare om de *inte* har sett någon försäljningsprisartikel. Detta är administrativt effektivt eftersom du vanligtvis har färre försäljningspriser jämfört med de som erbjuds till fullt pris. Med en boolesk [!UICONTROL NOT]får besökarna inte ** visa försäljningssignalen för att kvalificera sig för fullprismedlemskap. Däremot [!UICONTROL AND NOT] är det motsatsen till [!UICONTROL AND] användningsfallet, som visade hur målgruppsmedlemskapet bestäms av inkludering (dvs. besökaren kvalificerades utifrån två uttryckligen angivna signaler).

>[!MORELIKETHIS]
>
>* [Arbeta med jämförelseoperatorer i TraitBuilder](../features/traits/trait-comparison-operators.md)
>* [Åtgärdsordning i TraitBuilder-uttryck](../features/traits/trait-operator-precedence.md)

