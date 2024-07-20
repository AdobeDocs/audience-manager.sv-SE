---
description: Filer med överföringskontroll (.info) innehåller metadatainformation om filöverföringar så att partners kan verifiera att filöverföringar hanteras på rätt sätt i Audience Manager.
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: Överföringskontrollfiler för loggfilsöverföringar
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Överföringskontrollfiler för loggfilsöverföringar {#transfer-control-files-for-log-file-transfers}

Filer med överföringskontroll ([!DNL .info]) tillhandahåller metadatainformation om filöverföringar så att partners kan verifiera att filöverföringar hanteras korrekt i Audience Manager.

[!DNL Audience Manager] skickar en fil för överföringskontroll till en partner vid varje filöverföring. På grund av flertrådskaraktären hos utgivaren [!DNL FTP] kan överföringskontrollfilen skickas innan de faktiska filerna har överförts.

Med metadata i filen [!DNL .info] kan partners:

* Fastställa när en fullständig överföringscykel är slutförd (det totala antalet filer i sekvensen har levererats).
* Fastställ om en viss fil i sekvensen är fullständig/korrekt (genom att undersöka filens storlek i byte och det totala antalet rader).
* Validera antalet rader i Raw-filer mot antalet rader efter att filerna har lästs in i databasen i den mottagande änden (filens storlek i rader).

## Namngivningskonventioner {#file-naming-conventions}

Överföringskontrollfilen har samma namn som roten för gruppen/sekvensen med filtillägget [!DNL .info].

Om till exempel den första filen i sekvensen hade namnet: [!DNL ftp_12345_67890_full_1500727351632-1.sync] skulle kontrollfilen ha namnet [!DNL ftp_12345_67890_iter_1500727351632.info].

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

>[!NOTE]
>
> Batchens totala nummer är exklusive själva filen [!DNL .info]. Det innebär att summorna inte innehåller filen [!DNL .info], dess bytestorlek eller antalet rader.
>
> Filernas bytestorlekar och antalet rader är inkluderande alla rader/rader för huvud och distans (tomma). Ta bort rubriker för att få antalet faktiska datarader/rader.
>
> Totalt antal rader i batch och total bytestorlek är inklusive huvud- och blankstegsrader.
