---
description: I Segment Builder kan du segmentera besökare utifrån åtgärder som inträffar eller upprepas under ett visst dagligt intervall.
seo-description: I Segment Builder kan du segmentera besökare utifrån åtgärder som inträffar eller upprepas under ett visst dagligt intervall.
seo-title: Nyhet och frekvens
solution: Audience Manager
title: Nyhet och frekvens
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Nyhet och frekvens {#recency-and-frequency}

I [!UICONTROL Segment Builder]kan du segmentera besökare med senaste och återkommande intervall baserat på åtgärder som inträffar eller upprepas under ett visst dagligt intervall.

Audience Manager definierar [!DNL recency] och [!DNL frequency] enligt följande:

* **[!UICONTROL Recency]:**Hur nyligen en användare har visat eller kvalificerat sig för en (eller flera) egenskap.
* **[!UICONTROL Frequency]:**Den hastighet med vilken en användare visar eller är kvalificerad för en (eller flera) egenskap.

[!UICONTROL Recency] och [!UICONTROL Frequency] inställningar hjälper er att segmentera besökarna utifrån deras faktiska (eller uppfattade) intressenivå på en webbplats, ett avsnitt eller en viss kreativ nivå. Användare som kvalificerar sig för ett segment med höga krav på senaste frekvens/frekvens kan till exempel vara mer intresserade av en webbplats eller produkt än användare som besöker mindre ofta eller mindre ofta.

## Plats för inställningar för senaste och frekvens {#location}

Inställningarna [!UICONTROL Segment Builder]och [!UICONTROL Recency] inställningarna finns i avsnittet [!UICONTROL Frequency] på [!UICONTROL Basic View] [!UICONTROL Traits] panelen. Klicka på klockikonen för att visa dessa kontroller.

![](assets/recency_frequency.png)

## Begränsningar och regler {#limitations-rules}

Granska och förstå dessa gränser och regler när du vill använda senaste och återkommande för egenskaper i dina segment.

### Nyhet

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Begränsning eller regel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Minimivärde</b> </p> </td> 
   <td colname="col2"> <p>Senaste aktivitet måste vara större än 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Trait Types</b> </p> </td> 
   <td colname="col2"> <p>Du kan endast använda senaste kontroller för regelbaserade egenskaper och mappegenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tredjepartskunskaper</b> </p> </td> 
   <td colname="col2"> <p>Du kan inte ange regler för senaste aktiviteter för enskilda tredjepartsegenskaper eller egenskapsgrupper som innehåller egenskaper från tredje part. Nyhet och frekvens gäller endast för dina egna egenskaper. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Frekvens

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Begränsning eller regel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Tredjepartskunskaper</b> </p> </td> 
   <td colname="col2"> <p>Du kan inte ange frekvensregler för enskilda egenskaper eller trait-grupper från tredje part som innehåller egenskaper från tredje part. Nyhet och frekvens gäller endast för dina egna egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Trait Types</b> </p> </td> 
   <td colname="col2"> <p>Du kan endast använda frekvenskontroller för regelbaserade egenskaper och mappegenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Krav för senaste</b> </p> </td> 
   <td colname="col2"> <p>Du kan konfigurera frekvenskrav <i>utan att</i> konfigurera krav på senaste aktivitet. Ange bara ett frekvensvärde och lämna fältet för senaste aktivitet tomt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regler för profilsammanslagning</b> </p> </td> 
   <td colname="col2"> <p>Se <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Tågfrekvens, Externa enhetsdiagram och regler</a>för profilsammanslagning. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel på senaste besök {#recency-examples}

Här är två exempel på hur aktuell information fungerar, beroende på vad du väljer i användargränssnittet:

### Använda operatorn mindre än eller lika med (&lt;=)

![Mindre än-lika med](assets/less-than-equal-to.png)

I det här exemplet väljer du operatorn &lt;=, vilket visas i skärmbilden. Detta ger användaren rätt till segmentet om han eller hon är berättigad till något av de tre egenskaperna minst tre gånger under de senaste fem dagarna. På tidslinjen nedan visas segmentkvalificeringen när segmentet skapas, den 1 oktober och tio dagar senare.

![De senaste fem dagarna](assets/last-5-days.png)

### Använda operatorn större än eller lika med (=>)

![Större än lika med](assets/greater-than-equal-to.png)

I det här exemplet väljer du operatorn =>, vilket visas i skärmbilden. Detta ger användaren rätt till segmentet om han eller hon kvalificerar sig för något av de tre egenskaperna minst tre gånger varje gång mellan sin första kvalificering på Audience Manager-plattformen och avslutningstiden fem dagar sedan. På tidslinjen nedan visas segmentkvalificeringen när segmentet skapas, den 1 oktober och tio dagar senare.

![Tidigare kvalifikationer](assets/earlier-qualification.png)


## Exempel på frekvensbegränsning {#frequency-capping}

Uttryck med frekvenskappning omfattar alla användare vars antal trait-implementeringar är under ett önskat värde. Här är några exempel på höger och fel:

* Fel - Uttrycket `frequency([1000T]) <= 5` innehåller alla användare som har uppnått egenskapen med ID &quot;1000&quot; högst fem gånger, men även användare som inte har fått det. Audience Manager validerar därför inte det här uttrycket av prestandaskäl, eftersom det skulle kvalificera för många användare för segmentet.

* Höger - Om du vill ta med alla användare som har uppnått egenskapen med ID:t &quot;1000&quot; högst fem gånger, lägger du till ytterligare ett villkor i uttrycket för att se till att användarna har kvalificerat sig för egenskapen minst en gång:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Höger - Om du vill att kravet på aktuell frekvens ska vara mindre än ett visst antal gånger eller dagar ska du koppla den egenskapen till en annan med en `AND` operator. Med hjälp av exemplet i den första punktpunkten blir det här uttrycket giltigt när det förenas med ett annat drag som visas här: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Höger - Vid användning av frekvensbegränsning för annonsering kan du skapa en segmentregel som ser ut så här: `(frequency([1000T] <= 2D) >= 5)`. Det här uttrycket omfattar alla användare som har uppnått egenskapen med ID &quot;1000&quot; under de senaste två dagarna minst fem gånger. Ange frekvensbegränsning genom att skicka det här segmentet till annonsservern med en `NOT` uppsättning på segmentet i annonsservern. Den här metoden ger bättre prestanda i [!DNL Audience Manager] samtidigt som den har samma syfte för frekvensbegränsning.

>[!MORELIKETHIS]
>
>* [Segment Builder Controls: Traits Section](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Kodsyntax som används i segmentuttrycksredigeraren](../../features/segments/segment-code-syntax.md)

