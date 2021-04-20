---
description: Beskriver den underliggande programvara som ligger till grund för de interaktiva rapporterna och datauppdateringsschemat.
seo-description: Beskriver den underliggande programvara som ligger till grund för de interaktiva rapporterna och datauppdateringsschemat.
seo-title: Rapportteknik
solution: Audience Manager
title: Rapportteknik
uuid: 5f3d815b-e1e6-42f2-b848-ac035a5aa77d
feature: Overlap Reports
exl-id: 59d875d6-a630-4795-93a7-1d432860f0a1
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# Rapportteknik{#report-technology}

Beskriver den underliggande programvara som ligger till grund för de interaktiva rapporterna och datauppdateringsschemat.

<!-- 

c_report_technology.xml

 -->

## Interaktiva rapporter använder tabellösningsteknik

[!DNL Audience Manager] använder  [](https://www.tableausoftware.com/) Tableu för att visa data i de interaktiva rapporterna. Med [!DNL Tableau] använder [!UICONTROL Delivery and Overlap]-rapporterna visuella tecken och symboler som hjälper dig att:

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

## Dokumentation till tabelldokument {#tableau-documentation}

Mer information om flikkontroller som du kan se i våra interaktiva rapporter finns i den officiella dokumentationen för [Tableau Server i Linux 2018.2](https://help.tableau.com/v2018.2/server-linux/en-us/get_started_server.htm)
