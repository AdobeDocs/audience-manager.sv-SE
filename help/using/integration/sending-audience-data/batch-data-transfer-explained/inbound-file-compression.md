---
description: Du kan också komprimera datafiler när du skickar dem till Audience Manager.
seo-description: Du kan också komprimera datafiler när du skickar dem till Audience Manager.
seo-title: Filkomprimering för inkommande dataöverföringsfiler
solution: Audience Manager
title: Filkomprimering för inkommande dataöverföringsfiler
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 9%

---


# Filkomprimering för inkommande dataöverföringsfiler{#file-compression-for-inbound-data-transfer-files}

Du kan komprimera datafiler när du skickar dem till Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager har stöd för gzip-komprimering (`.gz`) för inkommande, asynkrona dataöverföringar.

Audience Manager har även stöd för okomprimerade filer.

>[!IMPORTANT]
>
>Vi stöder inte kryptering för inkommande filer som komprimeras med gzip (`.gz`).
>
>Om du vill kryptera och komprimera inkommande filer använder du [PGP-kryptering](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] -kryptering inkluderar filkomprimering.

## Amazon S3-komprimering

För leverans till måste du använda [!DNL Amazon S3]`.gz` eller okomprimerade filer. Komprimerade filer måste vara 1 GB eller mindre. Om filerna är större bör du diskutera fil- och överföringsprocessen med Kundtjänst. Även om [!DNL Audience Manager] kan hantera mycket stora filer kan det finnas sätt att minska filstorleken eller göra dataöverföringen mer effektiv.

>[!IMPORTANT]
>
>Klienten måste använda binärt läge för att överföra komprimerade eller krypterade filer [!DNL FTP] . Komprimerade eller krypterade filer som skickas i [!DNL ASCII] läge kommer att skada dataöverföringsfilen.

## Bästa praxis

* Filerna bör [!DNL .gzip] komprimeras (och ha ett [!DNL .gz] filtillägg).
* Den maximala komprimerade filstorleken för en `.gz` komprimerad fil är 1 GB.
* Den optimala delningsstorleken, för snabb/tidigaste bearbetning av dina filer, är ungefär 1 GB okomprimerat eller 200-300 MB komprimerat.
* [!DNL Amazon S3] tillämpar en egen storleksgräns på 5 GB för överförda filer.
