---
description: Beskriver den underliggande programvara som ligger till grund för de interaktiva rapporterna och datauppdateringsschemat.
seo-description: Beskriver den underliggande programvara som ligger till grund för de interaktiva rapporterna och datauppdateringsschemat.
seo-title: Rapportteknik
solution: Audience Manager
title: Rapportteknik
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
translation-type: tm+mt
source-git-commit: b5a962381780f1a1627e39b59e3ca86fd51763b5

---


# Rapportteknik{#report-technology}

Beskriver den underliggande programvara som ligger till grund för de interaktiva rapporterna och datauppdateringsschemat.

<!-- 

c_report_technology.xml

 -->

## Interaktiva rapporter använder tabellösningsteknik

[!DNL Audience Manager] använder [programmet Tableau](https://www.tableausoftware.com/) för att visa data i de interaktiva rapporterna. Med [!DNL Tableau]hjälp av [!UICONTROL Delivery and Overlap] rapporterna används visuella tecken och symboler som hjälper dig att:

* Hitta egenskaper med höga och låga prestanda.
* Dekordrag och segment med låg och hög unik besökaröverlappning.
* Använd överlappande data för att skapa riktade segment.
* Utöka räckvidden genom att identifiera relaterade egenskaper med låg överlappning.

## Datauppdateringsschema

Rapportdata uppdateras varje vecka varje söndag. Uppdateringen bearbetar data från lördag (dagen före) tillbaka till föregående söndag.

## Former, färger och storlekar som används i interaktiva rapporter {#shapes-colors-sizes}

De flesta interaktiva rapporter visar resultat med former av olika storlek och färger. Det här visningsformatet är utformat för att hjälpa dig att förstå data visuellt, utan att behöva gå igenom rader och kolumner med siffror.

<!-- 

r_legend.xml

 -->

### Rapportförklaring

Följande tabell definierar de former, storlekar och färger som används i de dynamiska rapporterna.

<table id="table_EC180A96E3784FC6B81FCFB546C4A3FA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dataelement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Former</b> </td> 
   <td colname="col2"> 
    <ul id="ul_076773ABD0BB4CE6834ACFA8B3D6AC2E"> 
     <li id="li_BBAB37A6EC1549B48C0E4D3BFAF7062C">Cirklar visar dina egna egenskaper. </li> 
     <li id="li_371331AE984A4A999CE0596EA13987E0">Kvadrater visar egenskaper från tredje part. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Färger</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F5D243297F0C4E5A8EDCBD28A548869E"> 
     <li id="li_332EB873A35440E6BB6093E36A0FAC3D">Röda skuggor indikerar <i>låg</i> överlappning. </li> 
     <li id="li_29DFDB1218DF4069B5DCFF841D48EF56">Gröna skuggor indikerar <i>hög</i> överlappning. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Storlek</b> </td> 
   <td colname="col2"> Storleken ökar eller minskar i direkt proportion för att nå (antalet eller % av klickningarna eller unika användare i ett trait eller segment). </td> 
  </tr> 
 </tbody> 
</table>

## Ikoner och verktyg för rapporter förklaras {#icons-tools-explained}

Beskriver hur du söker efter och använder de olika ikonverktygen som används i de dynamiska rapporterna.

<!-- 

r_icons.xml

 -->

### Dataikoner och verktyg

Följande ikonverktyg finns längst ned i varje dynamiskt rapportfönster. Följande bild innehåller mer information om dessa verktyg.

![](assets/tools_icons90.png)

### Exportera data

Med dessa verktyg kan du exportera data från rapporten i fyra olika format.

| Exportalternativ | Exporterar data |
|---|---|
| **[!UICONTROL Image]** | Som en bildfil (.png). Användbart när du vill hämta och dela rapportdata i det ursprungliga grafiska formatet. |
| **[!UICONTROL PDF]** | Som en PDF-fil. |
| **[!UICONTROL Data]** | I ett nytt webbläsarfönster som numeriska data i kolumner och rader. |
| **[!UICONTROL Crosstab]** | Som en CSV-fil. |

### Återställ ändringar

Välj det här verktyget om du vill ångra alla interaktiva klickningsändringar som du har gjort i rapporten.

### Automatiska uppdateringar

Rapporterna [!UICONTROL Delivery-Performance] och [!UICONTROL Trait-to-Trait Overlap] rapporterna är dynamiska rapporter som svarar på och ändras baserat på klickåtgärder.

Anta att du vill välja flera annonsörer i [!UICONTROL Overlap] rapporten. När det här alternativet är aktiverat börjar automatiska uppdateringar returnera data så fort du markerar en kryssruta. Detta dynamiska beteende kan avbryta ditt arbetsflöde eftersom du måste vänta tills rapporten har bearbetats innan du väljer en annan annonsörer. Använd det här verktyget för att inaktivera (och aktivera igen) funktionen efter behov.

### Uppdatera data

Klicka på uppdateringsikonen om du vill köra en rapport eller läsa in datauppsättningen igen. När automatiska uppdateringar är inaktiverade klickar du på Uppdatera för att köra eller uppdatera rapporten.

### Sökverktyg

Sökningen representeras av en allmän förstoringsglasikon (visas inte). Sökfältet är dolt tills du klickar på markeringsetiketterna till vänster på skärmen. Tabellen nedan beskriver sökverktygets plats för varje rapport.

| Rapport | Söka efter sökningar genom att hovra över |
|---|---|
| [!UICONTROL Delivery and Performance] rapport | Etiketten&quot;Advertiser Name&quot;. |
| [!UICONTROL Overlap] rapporter | Etiketten SID-namn. |
