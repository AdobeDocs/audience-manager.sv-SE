---
description: Om du vill skicka data från din egen Amazon S3-bucket till Audience Manager måste du först begära att en dedikerad Amazon S3-roll konfigureras.
solution: Audience Manager
title: Utnyttja Amazon S3-behörigheter för kontoöverskridande paket för inkommande filer
feature: Inbound Data Transfers
source-git-commit: 17cee6971ca1d5cda8f272558a46220227fc51f7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Utnyttja Amazon S3-behörigheter för kontoöverskridande paket för inkommande filer {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Om du vill skicka data från din egen Amazon S3-bucket till Audience Manager måste du först begära att en dedikerad Amazon S3-roll konfigureras.

Gör så här:

1. Kontakta kundtjänst och begär en alternativ metod för att skicka filer till Audience Manager.
2. Ge kundtjänst via [!DNL Amazon Resource Name (ARN)] för en roll i ditt Amazon S3-konto som du kommer att använda för att skicka filer. _Den här rollen måste skapas innan du kontaktar kundtjänst_. När konfigurationen är klar tillhandahåller kundtjänst [!DNL Amazon Resource Name (ARN)] för den nya rollen.
3. Redigera behörigheterna för din befintliga Amazon S3-roll och använd den roll som kundtjänst ger.

>[!NOTE]
>
>Se till att du använder kommandot `bucket-owner-full-control` [åtkomstkontrollista](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) för att Audience Manager ska kunna behandla data korrekt.
>
>Exempel på kommandot Amazon Web Services: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`

