---
description: Filer med överföringskontroll (.info) innehåller metadatainformation om filöverföringar så att partners kan verifiera att filöverföringar hanteras korrekt i Audience Manager.
seo-description: Filer med överföringskontroll (.info) innehåller metadatainformation om filöverföringar så att partners kan verifiera att filöverföringar hanteras korrekt i Audience Manager.
seo-title: Överföringskontrollfiler för loggfilsöverföringar
solution: Audience Manager
title: Överföringskontrollfiler för loggfilsöverföringar
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 0%

---


# Överföringskontrollfiler för loggfilsöverföringar {#transfer-control-files-for-log-file-transfers}

Filer med överföringskontroll ([!DNL .info]) innehåller metadatainformation om filöverföringar så att partners kan verifiera att filöverföringar hanteras korrekt i Audience Manager.

[!DNL Audience Manager] skickar en fil för överföringskontroll till en partner vid varje filöverföring. På grund av att utgivaren har flera trådar kan [!DNL FTP] överföringskontrollfilen skickas innan de faktiska filerna har överförts.

Med metadata i [!DNL .info] filen kan partners:

* Fastställa när en fullständig överföringscykel är slutförd (det totala antalet filer i sekvensen har levererats).
* Fastställ om en viss fil i sekvensen är fullständig/korrekt (genom att undersöka filens storlek i byte och det totala antalet rader).
* Validera antalet rader i Raw-filer mot antalet rader efter att filerna har lästs in i databasen i den mottagande änden (filens storlek i rader).

## Namngivningskonventioner {#file-naming-conventions}

Överföringskontrollfilen har samma namn som roten för gruppen/sekvensen med ett [!DNL .info] filtillägg.

Om till exempel den första filen i sekvensen hade namn: [!DNL ftp_12345_67890_full_1500727351632-1.sync], kommer kontrollfilen att få ett namn [!DNL ftp_12345_67890_iter_1500727351632.info].

## Filformat {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[ANMÄRKNING]
>
> Batchens totala nummer är exklusive själva [!DNL .info] filen. Det innebär att summorna inte omfattar [!DNL .info] filen, dess bytestorlek eller antalet rader.
>
> Filernas bytestorlekar och antalet rader är inkluderande alla rader/rader för huvud och distans (tomma). Ta bort rubriker för att få antalet faktiska datarader/rader.
>
> Totalt antal rader i batch och total bytestorlek är inklusive huvud- och blankstegsrader.