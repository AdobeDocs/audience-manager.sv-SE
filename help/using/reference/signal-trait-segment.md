---
description: Beskriver komponenterna i ett Audience Manager-segment, de uttryck som används för att ange kriterier för målgruppskvalifikation och hur data överförs i ett händelseanrop.
seo-description: Beskriver komponenterna i ett Audience Manager-segment, de uttryck som används för att ange kriterier för målgruppskvalifikation och hur data överförs i ett händelseanrop.
seo-title: Signaler, egenskaper och segment
solution: Audience Manager
title: Signaler, egenskaper och segment
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Signaler, egenskaper och segment{#signals-traits-and-segments}

Beskriver komponenterna i ett Audience Manager-segment, de uttryck som används för att ange kriterier för målgruppskvalifikation och hur data överförs i ett händelseanrop.

<!-- 

c_signal_trait_segment.xml

 -->

**Disposition och syfte**

[!DNL Audience Manager] data består av signaler, egenskaper, segment och tillhörande kvalificeringsregler. Dataelementen och reglerna kombineras för att skapa segment. Segment organiserar besökarna i relaterade grupper. I följande tabell definieras de tre huvudkomponenterna i ett [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Innehåller </th> 
   <th colname="col3" class="entry"> Exempel </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Signal</b> </td> 
   <td colname="col2"> <p>Signaler är de minsta dataenheterna i <span class="keyword"> Audience Manager</span> och uttrycks som <a href="../reference/key-value-pairs-explained.md"> nyckelvärdepar</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">Nyckeln är en konstant som definierar en datauppsättning (t.ex. kön, färg, pris). </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">Värdet är en variabel som är relaterad till konstanten (t.ex. man/kvinna, grön, 100). </li> 
    </ul> <p>Jämförelseoperatorer kopplar nyckelvärdepar och anger relationen mellan dem. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Trait</b> </td> 
   <td colname="col2"> <p>Kombinationer av en eller flera signaler. </p> <p>Med booleska uttryck och jämförelseoperatorer kan du skapa regler för kvalificering av egenskaper. </p> <p>Skapa precisa kvalificeringskrav med kombinationer av egenskaper och trait-grupper. </p> </td> 
   <td colname="col3"> <p>Från de tillgängliga signalerna kan du skapa regeln "Avancerad kameraläsare" som uttrycks som: </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Segment</b> </td> 
   <td colname="col2"> <p>Användare som delar en uppsättning gemensamma attribut och är kvalificerade för relaterade egenskaper. </p> <p>Med booleska uttryck, tillsammans med krav på aktuell tid/frekvens, kan du skapa regler för segmentkvalificering. </p> <p>Skapa exakta kvalificeringskrav med kombinationer av egenskaper och segmentregler. </p> </td> 
   <td colname="col3"> <p>Från tillgängliga egenskaper och signaler kan du skapa en segmentregel som uttrycks som: </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Använd diagrammet nedan för att få en uppfattning om relationen mellan signaler, egenskaper och segment.

![](assets/signals-traits-segments.png)

**Bygg egenskaper och segmentregler med Visual Tools och Code Editors**

Kunderna hanterar egenskaper och segment med visuella verktyg och kodredigerare i [!DNL Audience Manager] användargränssnittet. Med de visuella verktygen kan du skapa regler med hjälp av sökfunktioner, popup-alternativ, nedrullningsbara menyer samt dra och släpp-funktioner. Kodredigerarna ger avancerade användare möjlighet att programmässigt utveckla målgruppssegmenteringskriterier.

**Händelseanrop Skicka data till Audience Manager**

Ett eventsamtal skickar data från din webbplats till [!DNL Audience Manager]. Anropet innehåller signal-, trait- och segmentdata i en HTTP-begäran. Själva händelsen är allt efter `/event` delen av en URL-sträng. Som visas i exemplet nedan kräver den här processen endast ett enda händelseanrop för att skicka flera variabler till [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORELIKETHIS]
>
>* [Segment: Syfte, komposition och regler](../features/segments/segments-purpose.md)

