---
description: Du kan begära en CSV-fil för en överlappningsrapport när den rapporten når sin postgräns på 1 miljon. En rapport kan ha nått denna gräns när ett meddelande om att ett oväntat fel har inträffat visas. Kontakta kundtjänst om du vill begära en komprimerad CSV-fil som du kan importera och arbeta med i ditt eget databassystem. Filerna är tillgängliga för överlappningsrapporter för segment-till-segment, segment-till-trait och trait-to-trait.
seo-description: Du kan begära en CSV-fil för en överlappningsrapport när den rapporten når sin postgräns på 1 miljon. En rapport kan ha nått denna gräns när ett meddelande om att ett oväntat fel har inträffat visas. Kontakta kundtjänst om du vill begära en komprimerad CSV-fil som du kan importera och arbeta med i ditt eget databassystem. Filerna är tillgängliga för överlappningsrapporter för segment-till-segment, segment-till-trait och trait-to-trait.
seo-title: CSV-filer för överlappningsrapporter
solution: Audience Manager
title: CSV-filer för överlappningsrapporter
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 0%

---


# CSV-filer för överlappningsrapporter{#csv-files-for-overlap-reports}

Du kan begära en CSV-fil för en överlappningsrapport när den rapporten når sin postgräns på 1 miljon. En rapport kan ha nått denna gräns när ett meddelande om att ett oväntat fel har inträffat visas. Kontakta kundtjänst om du vill begära en komprimerad CSV-fil som du kan importera och arbeta med i ditt eget databassystem. Filerna är tillgängliga för överlappningsrapporter för segment-till-segment, segment-till-trait och trait-to-trait.

## Metadata för filnamn {#file-name-metadata}

Följande tabell innehåller en beskrivning av de filnamnkonventioner och filtillägg som används i en CSV-fil som överlappar. I exemplen *visar kursiv* en variabelplatshållare.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metadataelement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Filtillägg </p> </td> 
   <td colname="col2"> <p>Överlappande rapportfiler är gzip-komprimerade och har ett <code> .gz</code> filtillägg. Du måste lägga till filnamnstillägget i filen efter dekomprimeringen. <code> .csv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filnamn </p> </td> 
   <td colname="col2"> <p>Filnamnssyntax: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segment-till-segment-filer: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Segment-till-trait-filer: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Trait-to-trait-filer: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datumintervall </p> </td> 
   <td colname="col2"> <p>Datumintervallet för en rapport är ett 5-siffrigt ID som innehåller: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> för en 7-dagars rapport. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> för en 30-dagars rapport. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flera filer </p> </td> 
   <td colname="col2"> <p>Vi ökar den sista siffran i filnamnet om en rapport innehåller flera filer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exempel </p> </td> 
   <td colname="col2"> <p>Exempel på filnamn för en enda rapport: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">En 7-dagars fil: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">En 30-dagars fil: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Exempel på filnamn för en rapport med flera filer: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Filinnehåll {#file-contents}

I filen omges strängdata med citattecken. Se modelldata nedan. Detta har trunkerats av utrymmesskäl och för att passa skärmen.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Poster för segment-till-segment-rapporter {#segment-segment-records}

En datafil för [segmentöverlappningsrapporten](segment-segment-overlap-report.md) innehåller följande poster.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>ID:t för det segment som du jämför med baslinjesegmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>Namnet på det segment som du jämför med baslinjesegmenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>ID för baslinjesegmentet. Baslinjesegmentet är det segment som du vill jämföra med andra segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>Namnet på baslinjesegmentet som du jämför med andra segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Du kan få rapporter för 7- och 30-dagars summeringsintervall. Den <code> rangeid</code> motsvarar de tidsintervall som visas nedan. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 dagar </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 dagar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Bearbetningsdatumet för en rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>Antalet unika användare i segmentet som du jämför med baslinjesegmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>Antalet unika användare i baslinjesegmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Ett totalt antal överlappningar av unika användare mellan baslinjesegmentet och de andra segment som valts för jämförelse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% överlappning av unika användare mellan baslinjesegmentet och de andra segment som valts för jämförelse. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Rapportposter för segment-till-trait {#segment-trait-records}

En datafil för [segmentöverlappningsrapporten](segment-trait-overlap-report.md) innehåller följande poster.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>Trait ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Trait name. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>DataProvider-ID. ID:n omfattar: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Dataproviderns namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Du kan få rapporter för 7- och 30-dagars summeringsintervall. Den <code> rangeid</code> motsvarar de tidsintervall som visas nedan. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 dagar </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 dagar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Bearbetningsdatumet för en rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>Antalet unika användare i det valda segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Antalet unika användare i en egenskap. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Antalet unika användare som delas mellan de valda segmenten och egenskaperna. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% av unika användare som överlappar varandra mellan trait och segment. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% av de unika användare som överlappar segmentet och egenskaperna. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Rapportposter för fack till fack {#trait-trait-records}

En datafil för [Trait-to-Trait Overlap Report](trait-trait-overlap-report.md) innehåller följande poster.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID:t för det trait som du jämför med baslinjestrafiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Namnet på det trait som du jämför med baslinjetrafiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID:t för din baslinje. Baslinjetrafiken är den egenskap som du vill jämföra med andra egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Namnet på baslinjetrafiken som du jämför med andra egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>DataProvider-ID. ID:n omfattar: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Dataproviderns namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Du kan få rapporter för 7- och 30-dagars summeringsintervall. Den <code> rangeid</code> motsvarar de tidsintervall som visas nedan. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 dagar </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 dagar </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Bearbetningsdatumet för en rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Antalet unika användare som delas mellan de valda egenskaperna. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Antalet unika användare i en grundegenskap. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Antalet unika användare som delas mellan de valda egenskaperna. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% av unika användare som överlappar de valda egenskaperna. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% av de unika användare som överlappar de valda egenskaperna. I UI-rapporten visas den här siffran i popup-fönstret när du hovrar över ett spår i heatmap-resultatet. </p> </td> 
  </tr> 
 </tbody> 
</table>
