---
description: Mätvärden för Profile Link tillhandahåller data om personer och enheter som autentiserar din webbplats. Data och diagram i profillänken uppdateras dynamiskt när du skapar sammanfogningsregler eller när du klickar på en befintlig regel på kontrollpanelen Regler för profilsammanfogning. Dessa mått kan innehålla enhetsdiagram från Adobe Experience Cloud Device Co-op eller andra tredjepartskällor för enhetsdiagram.
seo-description: Mätvärden för Profile Link tillhandahåller data om personer och enheter som autentiserar din webbplats. Data och diagram i profillänken uppdateras dynamiskt när du skapar sammanfogningsregler eller när du klickar på en befintlig regel på kontrollpanelen Regler för profilsammanfogning. Dessa mått kan innehålla enhetsdiagram från Adobe Experience Cloud Device Co-op eller andra tredjepartskällor för enhetsdiagram.
seo-title: Rapportera mått för profilkopplingsregler
solution: Audience Manager
title: Rapportera mått för profilkopplingsregler
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Rapportera mått för profilkopplingsregler {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] mätvärden ger data om personer och enheter som autentiserar till er webbplats. Data och diagram i [!UICONTROL Profile Merge Rule Reports] uppdateras dynamiskt när du skapar en sammanfogningsregel eller när du klickar på en befintlig regel på [!UICONTROL Profile Merge Rules] kontrollpanelen. Dessa mått kan innehålla enhetsdiagram från [!DNL Adobe Experience Cloud Device Co-op] eller andra tredjepartsdiagramkällor.

## Sammanfoga regelmått {#merge-rule-metrics}

Rapporter returnerar data i liggande diagram sida vid sida när dina kopplingsregler använder data från [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) eller andra enhetsdiagram från tredje part som du har tillgång till i [!DNL Audience Manager]. På så sätt kan du jämföra autentiserade förstahandsdata med enhetsövergripande data från enhetsdiagram [!UICONTROL Experience Cloud Device Co-op] eller andra tredjepartsdiagram. Mer information om data som returneras av [!UICONTROL Device Co-op]finns [i Enhetsdiagram: Interna processer och utdata](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Dessa data uppdateras dagligen.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mått </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Autentiserad aktivitet</span></b> </p> </td> 
   <td colname="col2"> <p>Visar: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Aktiva personer</span>: Antalet personer som har autentiserats på din webbplats de senaste 60 dagarna. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Enhetsövergripande</span>: Det totala antalet <a href="merge-rules-start.md#create-data-source"> enhets-ID:n</a> som lagras i <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> datakällan</a> för den valda <a href="merge-rule-definitions.md"> autentiserade profilen</a> under den tid som datakällan har funnits. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % aktiva personer</span>: Visar <span class="wintitle"> aktiva personer</span> som %. </li> 
    </ul> <p> <span class="wintitle"> Med autentiserad aktivitet</span> kan du jämföra datakällor efter aktivitet, volym och procent. Det kan hjälpa er att hitta en datakälla som har många personer och en hög andel aktiva användare. Eller så kanske ni tycker att det är värdefullt att jämföra datakällor med en hög andel aktiva användare jämfört med den totala målgruppsstorleken. Ibland kan en datakälla med låga totala livstidsvärden och hög aktivitet vara mer värdefull än den med höga livstidsresultat och låga aktivitetsvärden. </p> <p> <p>Obs! Mätvärdena för <span class="wintitle"> autentiserad aktivitet</span> innehåller endast <span class="wintitle"> Profile Link</span> -data. Den här rapporten innehåller inte data för <span class="wintitle"> Device Graph</span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Genomsnittliga enheter per person</span></b> </p> </td> 
   <td colname="col2"> <p> Visar det genomsnittliga antalet enheter som används av besökare som har autentiserat din webbplats för den valda datakällan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Totalt antal enheter</span></b> </p> </td> 
   <td colname="col2"> <p>Visar det totala antalet enheter som personer har använt för att autentisera till din webbplats för den valda datakällan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Totalt antal personer</span></b> </p> </td> 
   <td colname="col2"> <p>Visar det totala antalet personer som har identifierats deterministiskt för den valda datakällan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mått för enhetsdiagram {#device-graph-metrics}

I [!UICONTROL Merge Rules] rapporterna visas också data om det totala antalet personer och enheter som har besökt webbplatsen för den valda datakällan och enhetsdiagrammet. Dessa mått returnerar data baserat på förinställda tidsintervall (summeringsperioden) som varierar beroende på vilket enhetsalternativ du väljer när du skapar en regel. I följande tabell visas de här rapportintervallen för alla alternativ för enhetsdiagram.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Alternativ för enhetsdiagram </th> 
   <th colname="col2" class="entry"> Rapportvisningsintervall </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profillänk</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Totalt antal personer: 60 dagar </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Totalt antal enheter: 120 dagar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Co-op Device Graph</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Totalt antal personer: 180 dagar </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Totalt antal enheter: 180 dagar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Totalt antal personer: 180 dagar </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Totalt antal enheter: 180 dagar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Totalt antal personer: 60 dagar </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Totalt antal enheter under 60 dagar </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempelrapporter {#sample-reports}

### Länkrapport för standardprofil

En standardrapport [!UICONTROL Profile Link] ser ut som i följande exempel. Sammanfogningsregler som använder flera datakällor (upp till 3, maximalt) visar diagram på olika flikar för varje datakälla. Den här sammanfogningsregeln innehåller inte [!UICONTROL Device Co-op] data.

![](assets/profile-link-metrics.png)

### Profillänksrapport med enhetsdiagramdata

En [!UICONTROL Profile Link Device Graph] rapport som innehåller enhetsdiagramdata från enheten [!UICONTROL Adobe Experience Cloud Device Co-op] eller ett enhetsdiagram från tredje part visar [!UICONTROL Profile Link] och visar enhetsdiagramdata med liggande liggande diagram sida vid sida. Genom att placera dessa diagram bredvid varandra kan du utvärdera fördelarna med att använda dem [!UICONTROL Experience Cloud Device Co-op] jämfört med [!UICONTROL Profile Link] dem separat. Sammanfogningsregler som använder flera datakällor (upp till 3, maximalt) visar diagram på olika flikar för varje datakälla. Som en påminnelse returnerar inte diagrammet och måtten data från enhetsdiagrammet eller andra enhetsdiagram från [!UICONTROL Authenticated Activity] tredje part som du har tillgång till i [!DNL Adobe] [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Trend-diagram för profillänkar {#profile-link-trend}

Förutom andra datavisualiseringar innehåller rapporterna [!UICONTROL Profile Link] ett linjediagram. Linjediagrammet är utformat för att visa trender över tid för dina profilregler. Trenddiagram (och andra rapporter) är tillgängliga när du klickar på en regel från [!UICONTROL Profile Merge Rules] landningssidan ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Dessa diagram innehåller enhetsdiagramdata om du är medlem i [!UICONTROL Device Co-op] eller andra enhetsdiagram från tredje part som du kan ha tillgång till i [!DNL Audience Manager]. Klicka på en trendlinje för att se underliggande data.

>[!MORELIKETHIS]
>
>* [Vanliga frågor om regler för profilsammanslagning](../../faq/faq-profile-merge.md)

