---
description: Du kan även kryptera datafiler med PGP-kryptering när du skickar dem till Audience Manager.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: PGP-filkryptering för inkommande datatyper
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 8%

---

# PGP-filkryptering för inkommande datatyper{#file-pgp-encryption-for-inbound-data-types}

Du kan kryptera datafiler med [!DNL PGP] kryptering när de skickas till Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] -kryptering inkluderar filkomprimering. Vid sändning [!DNL PGP] krypterade inkommande filer ser till att du inte [komprimera](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) de använder gzip (`.gz`).
>
>[!DNL PGP] krypterade inkommande filer som också [komprimerad](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) är ogiltiga i Audience Manager.

Följ stegen nedan för att kryptera inkommande datafiler.

1. Ladda ned [Audience Manager public key](./assets/adobe_pgp.pub).
2. Importera den offentliga nyckeln till din betrodda butik.

   Om du till exempel använder [!DNL GPG]kan kommandot likna följande:

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
   >Audience Manager har bara stöd för [!DNL Advanced Encryption Standard (AES)] datakrypteringsalgoritm. Audience Manager stöder alla nyckelstorlekar.
