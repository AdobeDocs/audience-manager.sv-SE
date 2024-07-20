---
description: De vanligaste oanvända egenskaperna representeras som ett punktdiagram över egenskaper som ännu inte är medlemmar i ett segment, baserat på spårtyp, datakälla och prestanda.
seo-description: Top Unused Traits are represented as a scatter diagram of traits that are not yet members of a segment, based on trait type, data source, and performance.
seo-title: Top Unused Traits
solution: Audience Manager
title: De vanligaste oanvända traderna
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: Audience Optimization Reports
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 0%

---

# De vanligaste oanvända traderna{#top-unused-traits}

De vanligaste oanvända egenskaperna representeras som ett punktdiagram över egenskaper som ännu inte är medlemmar i ett segment, baserat på spårtyp, datakälla och prestanda.

## Användningsexempel {#use-cases}

Med rapporten [!UICONTROL Top Unused Traits] kan du analysera och jämföra prestanda för första och tredje parts egenskaper som för närvarande inte är mappade till ett segment. Den här vyn visar de bästa egenskaperna som kan användas i ett målgruppssegment för antingen kampanjoptimering eller nya möjligheter.

## Använda rapporten Oanvända vanligaste egenskaper {#using-the-report}

Använd **[!UICONTROL Data Provider Type]**-kontrollerna för att växla mellan egenskaper för första part och tredje part. Välj **[!UICONTROL All]** om du vill returnera egenskaper för första och tredje part i rapporten.

Med skjutreglaget **[!UICONTROL Impressions]** kan du välja ett lägsta och högsta värde för returnerade visningar. Eventuella egenskaper som ligger bakom mindre eller mer än de angivna gränserna visas inte i rapporten.

Använd kontrollerna **[!UICONTROL Day Range]** och **[!UICONTROL Date Through]** om du vill justera uppslagsintervallet. Observera att endast 30 dagars summeringsperiod är tillgänglig för den här rapporten.

Använd listrutan **[!UICONTROL Order]** för att välja de webbegenskaper i portföljen som du vill returnera information för.

I listrutan **[!UICONTROL Data Provider]** markerar du datakällorna som innehåller de egenskaper som du vill se i rapporten.

Använd listrutan **[!UICONTROL Traits]** för att välja vilka egenskaper du vill se i rapporten.

>[!IMPORTANT]
>
>När du aktiverar [!UICONTROL Audience Optimization for Publishers] måste du inkludera beskrivande metadata för [!UICONTROL Order IDs], enligt beskrivningen i steg 3 i [Importera datafiler från Google Ad Manager (tidigare DFP) till Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Genom att göra detta försäkrar du dig om att rapporten innehåller information om webbegenskapen som [!UICONTROL Order] i stället för [!UICONTROL Order ID].

## Tolka resultaten {#interpreting-results}

**Exempelrapport**

Din [!UICONTROL Top Unused Traits]-rapport kan se ut ungefär som den nedan. Klicka på en bubbla i rapporten för att visa underliggande data.

Se beskrivningarna för ytterligare information i tabellen nedan.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Objekt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">-dataleverantörstyp </span> </p> </td> 
   <td colname="col2"> <p>Anger om den valda datakällan innehåller egenskaper för första part eller tredje part. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait ID </span> </p> </td> 
   <td colname="col2"> <p>Det unika ID:t för den här egenskapen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait Name</span> </p> </td> 
   <td colname="col2"> <p>Det alfanumeriska namn som du eller DataProvider har tilldelat den här egenskapen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ordning</span> </p> </td> 
   <td colname="col2"> <p>Den webbegenskap som du ser den här rapporten för. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Antalet gånger som medlemmar i den här egenskapen har exponerats för ditt lager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Trait Uniques</span> </p> </td> 
   <td colname="col2"> <p>Antalet trait-medlemmar under de senaste 30 dagarna. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

Positionen för era egenskaper i en rapport kan berätta mycket om vilka egenskaper ni kan använda för att optimera befintliga målgruppssegment.

De egenskaper som ligger högre upp på Impressions-axeln är de som du vill använda i dina kampanjer. För egenskaper med ett lågt antal visningar är det osannolikt att du når den här målgruppen på din webbegenskap baserat på dina [!DNL Google Ad Manager]-data.

Titta till vänster om [!UICONTROL Unique Trait Realizations]-axeln för att få mycket exakta egenskaper och till höger för egenskaper som kan skapa skalor.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Placement Indicates </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Övre vänster</b> </p> </td> 
   <td colname="col2"> <p>Ett stort antal visningar och ett lågt antal realiseringar. </p> <p>Detta är en mycket exakt målgrupp som ännu inte är medlem i ett segment. Fundera på målinriktning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nederst till vänster</b> </p> </td> 
   <td colname="col2"> <p>Lågt antal visningar, lågt antal anpassade implementeringar. </p> <p> Ta hänsyn till de här egenskaperna eftersom medlemmarna inte bidrar till intrycket av webbinnehållet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Övre höger</b> </p> </td> 
   <td colname="col2"> <p>Ett stort antal intryck, ett stort antal realisationer. </p> <p>En stor räckvidd mot en publik som ännu inte markerats i ett segment. Den här målgruppen är den främsta kandidaten till målgruppsanpassning på grund av det stora antalet visningar och den omfattande användningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nederst till höger</b> </p> </td> 
   <td colname="col2"> <p>Lågt antal visningar, ett stort antal anpassade implementeringar. </p> <p> Du kan utesluta dessa egenskaper eftersom medlemmarna inte bidrar till intrycket av dina webbegenskaper. </p> </td> 
  </tr> 
 </tbody> 
</table>
