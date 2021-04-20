---
description: S3-statuskatalogen innehåller en .info-fil med information om slutförda och misslyckade överföringar. Filen innehåller JSON-formaterade data med statusresultat i en array.
seo-description: S3-statuskatalogen innehåller en .info-fil med information om slutförda och misslyckade överföringar. Filen innehåller JSON-formaterade data med statusresultat i en array.
seo-title: Statusuppdateringar för metadatafiler
solution: Audience Manager
title: Statusuppdateringar för metadatafiler
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: Log Files
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---


# Statusuppdateringar för metadatafiler{#status-updates-for-metadata-files}

S3-statuskatalogen innehåller en `.info`-fil med information om slutförda och misslyckade överföringar. Filen innehåller JSON-formaterade data med statusresultat i en array.

Innehållet i `.info`-filen ser ut ungefär som i det här exemplet.

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## Nyckelvärdepar för metadata definierade {#key-value-pairs}

I följande tabeller listas och definieras nycklarna i avsnitten `Files` och `Summary` i en metadatastatusfil.

**Tangenter i filarrayen**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nyckel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Description</code> </p> </td> 
   <td colname="col2"> <p>Innehåller en kort beskrivning av varför bearbetningen misslyckades. Det här fältet är tomt när bearbetningen har slutförts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Filstorlek i byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>MD 5-kontrollsumman för metadatafilen som har överförts till din <code> meta</code>-katalog. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Namnet på den metadatafil som överförts till din <code> meta</code>-katalog. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>Det läsbara namnet på den typ av data som filen innehåller. Det baseras på det underordnade ID:t i ditt filnamn. </p> <p>Se <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Namngivningskonventioner för metadatafiler</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>Det läsbara namnet på den typ av data som filen innehåller. Det baseras på det överordnade ID:t i ditt filnamn. </p> <p>Se <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Namngivningskonventioner för metadatafiler</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>Returnerar två textvärden som beskriver bearbetningsstatusen för metadatafilen: </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Tangenter i objektet Sammanfattning**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nyckel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Filbearbetningsdatum i <code><i>yyyy-mm-dd</i></code>-format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>Returnerar två textvärden som beskriver bearbetningsstatusen för alla filer för en hel dag: </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>Antalet filer som inte kunde bearbetas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>Antal filer som bearbetats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Returnerar en läsbar tidsstämpel för bearbetning av starttider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>En UNIX-tidsstämpel för bearbetning av starttider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Totalt antal byte för alla metadatafiler för dagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Totalt antal filer som bearbetats för dagen. </p> </td> 
  </tr> 
 </tbody> 
</table>
