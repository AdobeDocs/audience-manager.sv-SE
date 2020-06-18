---
description: En översikt över funktionen Addressable Audience och användningsexempel.
keywords: DIL
seo-description: En översikt över funktionen Addressable Audience och användningsexempel.
seo-title: Adresserbara målgrupper
solution: Audience Manager
title: Adresserbara målgrupper
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 0%

---


# Mottagande målgrupp {#addressable-audiences}

En översikt över [!UICONTROL Addressable Audience] funktionen och användningsexempel.

## Vad är en adresserbar publik? {#addressable-audience-description}

Funktionen [!UICONTROL Addressable Audiences] visar överlappningen mellan de målgrupper du ser i alla dina egenskaper där data [!DNL Audience Manager] samlas in och det valda målet. Ta en titt på bilden nedan för att få en förståelse för detta koncept. Överlappningen mellan varje cirkel representerar olika typer av adresserbara målgrupper.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Audience Manager Addressable Audience for a Destination</b> </p> </td> 
   <td colname="col2"> <p>Antal enheter som har interagerat med alla Audience Manager-kunder på plattformsnivå under rapportens kontrollperiod och som kan matchas med det valda målet. </p> <p>Det här måttet är användbart eftersom det visar dig: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Storleken på den totala adresserbara målgrupp som <span class="keyword"> Audience Manager</span> kan nå på ett visst mål. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Hur stor <span class="keyword"> profilpoolen för Audience Manager</span> är för en målinriktningsplattform och deras målgrupper. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kundens totala målgrupp</b> </p> </td> 
   <td colname="col2"> <p>Ett antal enheter som antingen har fått en regelbaserad egenskap på dina egenskaper eller en inbyggd egenskap från dina offlinefiler under backupfönstret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Matchningsfrekvens för adresserbar publik</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Antal överlappningar av enheter som antingen har fått ett regelbaserat beteende eller en inbyggd egenskap under kontrollfönstret och enheter som har en ID-synkronisering med den valda målplatsen oavsett synkroniseringstidpunkten. </p> 
    </draft-comment> <p>Detta mått representerar enheter som: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Har fått antingen en regelbaserad eller en introducerad egenskap under backupfönstret <b>OCH</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Ha en ID-synkronisering med det valda målet oavsett synkroniseringstidpunkten. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kundmatchningsfrekvens</b> </p> </td> 
   <td colname="col2"> <p>Kundadresserbar publik‡ Kundens totala publik uttryckt i %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Total segmentpopulation</b> </p> </td> 
   <td colname="col2"> <p>Antal enheter som var medlemmar i ditt segment under rapportens kontrollperiod. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentadresserbar publik</b> </p> </td> 
   <td colname="col2"> <p>Antalet användare som har tillhört segmentet under rapportens summeringsperiod och som har en aktiv ID-synkronisering på webbplatsen. Segmenten kan innehålla egna data från första part samt data från andra part och tredje part via egenskaper som förvärvats i <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Tips: När det används med 1-dagars summeringsperiod kan det här måttet hjälpa dig att förstå segmentens aktuella status. Detta beror på att <span class="wintitle"> segmentadresserbara målgruppsmått</span> representerar de användare som stannade i ett segment under föregående dag. Kombinera detta med det faktum att <span class="keyword"> Audience Manager</span> uppdaterar <span class="wintitle"> adresserbara målgrupper</span> dagligen, och kombinerar denna mätperiod och uppslagsperiod, som ger den senaste ögonblicksbilden av era segment. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Matchningsfrekvens för segment</b> </p> </td> 
   <td colname="col2"> <p>Segmentadresserbar publik / Total segmentpopulation uttryckt i %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Målgruppsgränssnitt {#addressable-audience-interface}

Funktionen omvandlar det här abstrakta konceptet till mätbara data [!UICONTROL Addressable Audience] . I [!DNL Audience Manager]den här funktionen visas målgrupper som överlappar datavisualiseringar som ger snabböverskådlig information tillsammans med numeriska data i tabellform.

[!UICONTROL Addressable Audiences] finns i **[!UICONTROL Audience Data > Destinations]**. Välj **[!UICONTROL Integrated Platforms > Device-Based]** om du vill se adresserbara målgruppsmått.

![](assets/addressable-audiences-landing.png)

De tre mätvärdena som visas på [!UICONTROL Addressable Audiences] landningssidan är:

| Mått | Beskrivning |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Detta mått representerar [!UICONTROL Customer Addressable Audience] (beskrivs i tabellen ovan) *för de senaste 30 dagarna.* |
| **[!UICONTROL Match Rate]** | Detta mått representerar [!UICONTROL Addressable Audience Match Rate] (beskrivs i tabellen ovan) *de senaste 30 dagarna*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Antal enheter som har interagerat med alla [!DNL Audience Manager] kunder på plattformsnivå under rapportens kontrollperiod och som kan matchas med den här destinationen. Mer information finns i [Platform-nivåstatistik](/help/using/features/addressable-audiences.md#platform-level-metrics) . |

Klicka på namnet på en server-till-server-destination för att visa dina adresserbara målgruppsdata. Observera att den här funktionen endast returnerar data för server-till-server-mål och att åtkomst kräver administratörsbehörighet.

![](assets/addressableAudiences.png)

Genom att granska dessa data kan du

* **Prognos och planering:** [!UICONTROL Segment Addressable Audience] data ger er större detaljrikedom i de segment ni planerar att skicka till en målgrupp för målgruppsanpassning och aktivering.

* **Prestandagranskningar:** Funktionen är också ett felsökningsverktyg [!UICONTROL Addressable Audiences] . Ni kan granska kampanjens resultat, förstå kampanjens räckvidd och dubbelkontrollera med målgrupps-/aktiveringspartners om ni inte ser de resultat ni förväntar er.

### Prospektera med data från tredje part och effekter för matchningsfrekvenser

Innan man köper data från tredje part för att värva målgrupper kan man validera överlappningen med andra dataleverantörer. Detta kan hjälpa er att fatta ett välgrundat beslut innan ni köper nya data. ID-synkroniseringen för inköpt information från tredje part är inte bara beroende av att dina data överlappar varandra, utan även av tredjepartsleverantörernas fotavtryck med alla andra [!DNL Audience Manager] kunder. Din [!DNL Adobe] konsult kan hjälpa er att identifiera ytterligare relevanta datakällor för att optimera prospekteringskampanjer.

### Mobilanvändare och matchningsfrekvenser

Det finns luckor när du försöker ansluta [!DNL Safari] eller använda mobilappar där det inte finns några cookies från tredje part. Det gör det svårt att synkronisera användare med vissa partners eftersom endast dessa [!DNL Adobe] ID:n för synkroniserade cookies från tredje part finns i medieleveransloggarna. Detta är en orsak till att du kanske ser [låga matchningsfrekvenser](../features/addressable-audiences.md#low-match-rates) för dina destinationer.

## Datumintervall i adresserbara målgrupper och destinationer {#date-ranges}

Läs avsnitten nedan om tillgängliga datumintervall och hur data lagras utifrån varje intervall i rapporter för en [!UICONTROL Addressable Audience] eller [!UICONTROL Destination].

## Tillgängliga datumintervall och tidszoner {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Rapporter för dina [!UICONTROL Addressable Audiences] - och [destinationer](../features/destinations/destinations.md) använder samma datumintervall. Alternativen för datumintervall är:

* [!UICONTROL Last 1 Day] (Det här intervallet går från midnatt till midnatt under föregående 24-timmarsperiod. Det är inte ett reellt mått eller ett mått för aktuell tid.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alla datum och datumintervall anges i [!DNL UTC] tidszonen. Se [Tidszoner i Audience Manager](../reference/aam-time-zones.md).

## Data i datumintervallintervall {#date-range-intervals}

Mätvärdena [!UICONTROL Addressable Audience] och [!UICONTROL Destination] värdena returnerar antalet unika användare för det valda tidsintervallet. En besökare räknas till exempel bara en gång, även om de kommer till platsen flera gånger. Det första besöket är det unika besöket och registreras. De följande besöken är återkommande besök och räknas inte eftersom de inte är unika.

Datumintervall innehåller data för det valda tidsintervallet eller äldre. Och data försvinner från varje rapportintervall när tiden går. Låt oss anta att du ser 2 besökare efter att du valt [!UICONTROL Last 30 Days] alternativet. I rapporterna kan följande besökare:

* *Inkluderas* i resultaten som returneras av de längre tidsintervallen (60 dagar, 90 dagar och Livstid).
* *Inkluderas inte* i de kortare intervall som föregår [!UICONTROL Last 30 Day] alternativet (Aktuell, 7 dagar och 14 dagar).

Och på dag 31 visas dessa besökare bara på 60 dagar, 90 dagar och [!UICONTROL Lifetime] resultat. De har åldrats utanför 30-dagarsintervallet. Besökarna går inte ut ur [!UICONTROL Lifetime] intervallet.

## Målgruppsstatistik {#addressable-audience-metrics}

I det här avsnittet beskrivs de typer av mätvärden som tillhandahålls av [!UICONTROL Addressable Audiences].

### Kundnivåstatistik {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Dessa värden returnerar data för egenskaper som realiseras när besökare kommer till er webbplats eller när ni skickar inkommande datafiler till [!DNL Audience Manager]. Dessa mått ger en heltäckande bild av målgruppens storlek för ditt konto.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Kundadresserbar publik</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Antal överlappningar av enheter som antingen har fått ett regelbaserat beteende eller en inbyggd egenskap under kontrollfönstret och enheter som har en ID-synkronisering med den valda målplatsen oavsett synkroniseringstidpunkten. </p> 
    </draft-comment> <p>Detta mått representerar enheter som: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Har fått antingen en regelbaserad eller en introducerad egenskap under backupfönstret <b>OCH</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Ha en ID-synkronisering med det valda målet oavsett synkroniseringstidpunkten. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kundens totala målgrupp</b> </p> </td> 
   <td colname="col2"> <p>Ett antal enheter som antingen har fått en regelbaserad egenskap på dina egenskaper eller en inbyggd egenskap från dina offlinefiler under backupfönstret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kundmatchningsfrekvens</b> </p> </td> 
   <td colname="col2"> <p>Kundadresserbar publik‡ Kundens totala publik uttryckt i %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Matchningsmått på segmentnivå {#segment-level-metrics}

Dessa värden returnerar data för segmentmedlemskap. De ger en mer detaljerad och korrekt bild av målgruppsstorleken för varje segment.

>[!NOTE]
>
>Det sätt på vilket genvägen tillämpas på segmentnivån skiljer sig från det på kundnivå. Besökarna kan komma till webbplatsen för 10 dagar sedan och dra nytta av en egenskap, och kan kvalificera sig för ett segment sedan dess och sedan lämna segmentet för 2 dagar sedan. När 7-dagars summering tillämpas räknas dessa besökare på segmentnivå men inte på kundnivå.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentadresserbar publik</b> </p> </td> 
   <td colname="col2"> <p>Antalet användare som har tillhört segmentet under rapportens summeringsperiod och som har en aktiv ID-synkronisering på webbplatsen. Segmenten kan innehålla egna data från första part samt data från andra part och tredje part via egenskaper som förvärvats i <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>. </p> <p> <p>Tips: När det används med 1-dagars summeringsperiod kan det här måttet hjälpa dig att förstå segmentens aktuella status. Detta beror på att <span class="wintitle"> segmentadresserbara målgruppsmått</span> representerar de användare som stannade i ett segment under föregående dag. Kombinera detta med det faktum att <span class="keyword"> Audience Manager</span> uppdaterar <span class="wintitle"> adresserbara målgrupper</span> dagligen, och kombinerar denna mätperiod och uppslagsperiod, som ger den senaste ögonblicksbilden av era segment. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Total segmentpopulation</b> </p> </td> 
   <td colname="col2"> <p>Antal enheter som var medlemmar i ditt segment under rapportens kontrollperiod. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Matchningsfrekvens för segment</b> </p> </td> 
   <td colname="col2"> <p>Segmentadresserbar publik / Total segmentpopulation uttryckt i %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Platform Level Metrics {#platform-level-metrics}

Det här måttet returnerar data om aktiviteter som samlats in för alla [!DNL Audience Manager] kunder. De kan ge en bredare bild av kundens målgrupp jämfört med de samlade [!DNL Audience Manager] kunderna.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Manager Addressable Audience</b> </p> </td> 
   <td colname="col2"> <p>Antal enheter som har interagerat med alla Audience Manager-kunder på plattformsnivå under rapportens kontrollperiod och som kan matchas med det valda målet. </p> <p>Det här måttet är användbart eftersom det visar dig: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> Storleken på den totala adresserbara målgrupp som <span class="keyword"> Audience Manager</span> kan nå på ett visst mål. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Hur stor <span class="keyword"> profilpoolen för Audience Manager</span> är för en målinriktningsplattform och deras målgrupper. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Jämföra målgrupper som kan ta emot kunder och segment{#comparing-metrics}

Du bör inte jämföra värdena [!UICONTROL Customer Addressable Audience] och [!UICONTROL Segment Addressable Audience] måtten för att avgöra om det ena är större än det andra. Dessa är separata, olika och oberoende mätvärden. Såsom beskrivs i definitionerna ovan, härleds vart och ett av dessa från olika datauppsättningar. Därför bör du undvika att dra några slutsatser om ett mätvärde är större än det andra. Allt du kan säga när du jämför dessa är att:

* [!UICONTROL Customer Addressable Audiences] bygger på *anpassade implementeringar av egna data*. Detta ger en bred, heltäckande bild av er integrering med en datapartner.

* [!UICONTROL Segment Addressable Audiences] baseras på segmentkvalifikationer *för era egna data, plus data* från andra leverantörer. Detta mätresultat ger en mer detaljerad och korrekt bild av era adresserbara målgrupper på en målinriktningsplattform.

## Orsaker till låg matchningsfrekvens för adresserbara målgrupper {#low-match-rates}

Vanliga element som ligger bakom låga [!UICONTROL Addressable Audience] matchningsfrekvenser eller avvikelser i rapporterade tal.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Orsak </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Mobiltrafik</b> </p> </td> 
   <td colname="col2"> <p>De flesta server-till-server-integreringar är beroende av synkroniseringsprocesser som underlättas av cookies från tredje part. I mobilmiljöer används dock inte cookies från tredje part. Därför kan det verka som om era adresserbara målgrupper är låga jämfört med segmentstorleken. </p> <p>Från och med januari 2018 kan du aktivera mobila målgrupper på samma Google- och Adobe Advertising Cloud-destinationer som konfigurerats för cookie-baserade målgrupper. Detta innebär att du kan skicka segment med kombinerat medlemskap för cookie och mobilt ID till dina Google- och Advertising Cloud-destinationer, men tänk på att adressater bara visar överlappningen mellan cookie-ID:n och destinationer. Audience Manager skickar 100 % av de mobila målgrupperna till destinationer, men de mobila målgrupperna mäts inte av det adresserbara målgruppsmåttet. </p> <p> <p><b>Obs</b>:  Ta till exempel ett segment med en befolkning på 1 000 000. Om du mappar det här segmentet till ett Google- eller Adobe Advertising Cloud-mål kan du se en adresserbar publik på 700 000 enheter och en matchningsfrekvens på 70 %. Medlemskapet på 700 000 består av cookie-ID:n som har en ID-synkronisering med målet. Din adresserbara publik kan faktiskt vara mycket högre, eftersom adresserbara mobil-ID:n inte visas i det här måttet. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari-trafik</b> </p> </td> 
   <td colname="col2"> <p>Safari blockerar cookies från tredje part. Detta förhindrar att Audience Manager synkroniserar ID:n med målet. I och med introduktionen av <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>kan ni förvänta er att era adresserbara målgrupper inte inkluderar Safari-användare. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Spårade mediaexponeringar</b> </p> </td> 
   <td colname="col2"> <p>På grund av de bästa metoderna för annonsservrar görs inga ID-synkroniseringar i annonstaggar. Kunder som gör en stor mängd annonsering utanför webbplatsen synkroniserar inte användare med tredjepartsintegreringar i dessa miljöer. Dessutom kan ett stort antal insamlade mediefunktionsdata minska antalet adresserbara målgrupper. </p> </td>
  </tr> 
 </tbody> 
</table>

## Felsökning med adresserbara målgrupper {#troubleshooting}

Förutom att använda matchningsfrekvenser kan du även använda [!UICONTROL Addressable Audiences] som felsökningsverktyg.

<!-- addressable-audiences-troubleshooting.xml -->

Anta att du skickar ett segment till ett mål och att det visar låga rapporteringssiffror. Om du kontrollerar [!UICONTROL Addressable Audience] resultatet visas det om det är ett tekniskt problem eller om det bara är ett fall med låg matchningsfrekvens. En låg matchningsfrekvens visar att målplatsen inte är så bra för de valda segmenten. En skillnad i det totala antalet adresserbara målgruppsnummer mellan [!DNL Audience Manager] och målet innebär emellertid ett integrerings-, synkroniserings- eller annat tekniskt problem. Kontakta i så fall din kontoansvarige.