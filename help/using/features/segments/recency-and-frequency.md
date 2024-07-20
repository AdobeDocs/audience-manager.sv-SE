---
description: I Segment Builder kan du segmentera besökare utifrån åtgärder som inträffar eller upprepas under ett visst dagligt intervall.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: Nyhet och frekvens
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 1%

---

# Nyhet och frekvens {#recency-and-frequency}

I [!UICONTROL Segment Builder] kan du segmentera besökare utifrån åtgärder som inträffar eller upprepas under ett visst dagligt intervall.

Audience Manager definierar [!DNL recency] och [!DNL frequency] enligt följande:

* **[!UICONTROL Recency]:** Så nyligen en användare visat eller kvalificerat sig för en (eller flera) [!UICONTROL traits].
* **[!UICONTROL Frequency]:** Den frekvens med vilken en användare visade eller kvalificerade för en (eller flera) [!UICONTROL traits].

Med inställningarna för [!UICONTROL Recency] och [!UICONTROL Frequency] kan du segmentera besökare baserat på deras faktiska (eller uppfattade) intressenivå på en webbplats, ett avsnitt eller en viss kreativ nivå. Användare som kvalificerar sig för ett segment med höga krav på senaste frekvens/frekvens kanske är mer intresserade av en webbplats eller produkt än användare som besöker mindre ofta eller mindre ofta.

## Plats för [!UICONTROL Recency and Frequency]-inställningar {#location}

Inställningarna för [!UICONTROL Segment Builder], [!UICONTROL Recency] och [!UICONTROL Frequency] finns i avsnittet [!UICONTROL Basic View] på panelen [!UICONTROL Traits]. Klicka på klockikonen för att visa dessa kontroller.

![](assets/recency_frequency.png)

## Begränsningar och regler {#limitations-rules}

Granska och förstå dessa gränser och regler när du vill använda senaste och återkommande för egenskaper i dina segment.

### [!UICONTROL Recency] {#recency}

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
   <td colname="col1"> <p> <b>Anpassa typer</b> </p> </td> 
   <td colname="col2"> <p>Du kan endast använda senaste kontroller för regelbaserade egenskaper och mappegenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Tredjepartskunskaper</b> </p> </td> 
   <td colname="col2"> <p>Du kan inte ange regler för senaste aktiviteter för enskilda tredjepartsegenskaper eller trait-grupper som innehåller egenskaper från tredje part. Nyhet och frekvens gäller endast för dina egna egenskaper. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

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
   <td colname="col1"> <p> <b>Anpassa typer</b> </p> </td> 
   <td colname="col2"> <p>Du kan endast använda frekvenskontroller för regelbaserade egenskaper och mappegenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Senaste krav</b> </p> </td> 
   <td colname="col2"> <p>Du kan konfigurera frekvenskrav <i>utan att</i> konfigurerar krav för senaste aktivitet. Ange bara ett frekvensvärde och lämna fältet för senaste aktivitet tomt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regler för profilsammanslagning</b> </p> </td> 
   <td colname="col2"> <p>Se <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs och Profile Merge Rules </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel på senaste besök {#recency-examples}

Här är två exempel på hur aktuell information fungerar, beroende på vad du har valt i användargränssnittet:

### Använda operatorn mindre än eller lika med (&lt;=)

![Mindre än-lika med](assets/less-than-equal-to.png)

I det här exemplet väljer du operatorn &lt;=, vilket visas i skärmbilden. Detta kvalificerar användaren för [!UICONTROL segment] om de kvalificerar sig för någon av de tre [!UICONTROL traits] minst tre gånger under de senaste fem dagarna. Tidslinjen nedan visar [!UICONTROL segment]-kvalificeringen när [!UICONTROL segment] skapas, den 1 oktober och tio dagar senare.

![De senaste fem dagarna](assets/last-5-days.png)

### Använda operatorn större än eller lika med (=>)

![Större än-lika med](assets/greater-than-equal-to.png)

I det här exemplet väljer du operatorn =>, vilket visas i skärmbilden. Detta kvalificerar din användare för [!UICONTROL segment] om de kvalificerar sig för någon av de tre [!UICONTROL traits] minst tre gånger varje gång mellan sin första kvalificering på Audience Manager-plattformen och avslutningstiden för fem dagar sedan. Tidslinjen nedan visar [!UICONTROL segment]-kvalificeringen när [!UICONTROL segment] skapas, den 1 oktober och tio dagar senare.

![Tidigare kvalificering](assets/earlier-qualification.png)


## Exempel på frekvensbegränsning {#frequency-capping}

Uttryck med frekvensbegränsning inkluderar alla användare vars antal [!UICONTROL trait]-realiseringar är under det önskade värdet. Här är några exempel på höger och fel:

* Fel - Uttrycket `frequency([1000T]) <= 5` innehåller alla användare som har fyllt i [!UICONTROL trait] med ID 1000 högst fem gånger, men även användare som inte har fyllt i [!UICONTROL trait]. Därför validerar inte Audience Manager det här uttrycket av prestandaskäl, eftersom det skulle kvalificera för många användare för [!UICONTROL segment].

* Höger - Om du vill inkludera alla användare som har fyllt i [!UICONTROL trait] med ID:t 1000 högst fem gånger, lägger du till ytterligare ett villkor i uttrycket för att se till att användarna har kvalificerat sig för [!UICONTROL trait] minst en gång: `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Höger - Om du vill att kraven på aktuell/frekvens ska vara mindre än ett visst antal gånger eller dagar ansluter du [!UICONTROL trait] till en annan med en `AND` -operator. Med hjälp av exemplet i den första punktpunkten blir det här uttrycket giltigt när det kopplas till en annan [!UICONTROL trait], vilket visas här: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Höger - För annonseringsfall med frekvensbegränsning kan du skapa en [!UICONTROL segment]-regel som liknar den här: `(frequency([1000T] <= 2D) >= 5)`. Det här uttrycket innehåller alla användare som har skapat [!UICONTROL trait] med ID:t 1000 under de senaste två dagarna minst fem gånger. Ange frekvensbegränsning genom att skicka denna [!UICONTROL segment] till annonsservern med en `NOT` inställd på [!UICONTROL segment] i annonsservern. Den här metoden uppnår högre prestanda i [!DNL Audience Manager] samtidigt som den har samma syfte för frekvensbegränsning.

>[!MORELIKETHIS]
>
>* [Segmentbyggaren-kontroller: Traits Section ](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Kodsyntax som används i Segment Expression Editor](../../features/segments/segment-code-syntax.md)
