---
description: Du kan också komprimera datafiler när du skickar dem till Audience Manager.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Filkomprimering för inkommande dataöverföringsfiler
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 6%

---

# Filkomprimering för inkommande dataöverföringsfiler{#file-compression-for-inbound-data-transfer-files}

Du kan komprimera datafiler när du skickar dem till Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager har stöd för gzip (`.gz`) för inkommande, asynkrona dataöverföringar.

Audience Manager har även stöd för okomprimerade filer.

>[!IMPORTANT]
>
>Vi stöder inte kryptering för inkommande filer som komprimeras med gzip (`.gz`).
>
>Om du vill kryptera och komprimera inkommande filer använder du [PGP-kryptering](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] -kryptering inkluderar filkomprimering.

## Amazon S3-komprimering

För leverans till [!DNL Amazon S3]måste du använda `.gz` eller okomprimerade filer. Komprimerade filer måste vara 1 GB eller mindre. Om filerna är större bör du diskutera fil- och överföringsprocessen med Kundtjänst. Fast [!DNL Audience Manager] kan hantera mycket stora filer, det kan finnas sätt att minska filstorleken eller göra dataöverföringen mer effektiv.

>[!IMPORTANT]
>
>Dina [!DNL FTP] klienten måste använda binärt läge för att överföra komprimerade eller krypterade filer. Komprimerade eller krypterade filer som skickats in [!DNL ASCII] dataöverföringsfilen skadas.

## Bästa praxis

* Filer ska vara [!DNL .gzip] komprimerad (och har en [!DNL .gz] filtillägg).
* Maximal komprimerad filstorlek för `.gz` komprimerad fil är 1 GB.
* Den optimala delningsstorleken, för snabb/tidigaste bearbetning av dina filer, är ungefär 1 GB okomprimerat eller 200-300 MB komprimerat.
* [!DNL Amazon S3] tillämpar en egen storleksgräns på 5 GB för överförda filer.
