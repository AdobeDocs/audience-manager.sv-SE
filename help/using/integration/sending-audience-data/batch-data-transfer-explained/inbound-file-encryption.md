---
description: Du kan även kryptera datafiler med PGP-kryptering när du skickar dem till Audience Manager.
seo-description: Du kan även kryptera datafiler med PGP-kryptering när du skickar dem till Audience Manager.
seo-title: PGP-filkryptering för inkommande datatyper
solution: Audience Manager
title: PGP-filkryptering för inkommande datatyper
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 10%

---

# PGP-filkryptering för inkommande datatyper{#file-pgp-encryption-for-inbound-data-types}

Du kan kryptera datafiler med [!DNL PGP]-kryptering när du skickar dem till Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] -kryptering inkluderar filkomprimering. När du skickar [!DNL PGP] krypterade inkommande filer måste du inte [komprimera](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) dem med gzip (`.gz`).
>
>[!DNL PGP] Krypterade inkommande filer som också är  [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) komprimerade är ogiltiga i Audience Manager.

Följ stegen nedan för att kryptera inkommande datafiler.

1. Hämta den offentliga [Audience Manager-nyckeln](./assets/adobe_pgp.pub).
2. Importera den offentliga nyckeln till din betrodda butik.

   Om du till exempel använder [!DNL GPG] kan kommandot vara som följer:

   `gpg --import adobe_pgp.pub`

3. Verifiera att nyckeln har importerats korrekt genom att köra följande kommando:

   `gpg --list-keys`

   Du bör se ett meddelande som liknar följande:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Kryptera inkommande data med följande kommando:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Alla krypterade data måste använda `.pgp` eller `.gpg` som filtillägg (t.ex. `ftp_dpm_100_123456789.sync.pgp` eller `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager stöder bara datakrypteringsalgoritmen [!DNL Advanced Encryption Standard (AES)]. Audience Manager stöder alla nyckelstorlekar.
