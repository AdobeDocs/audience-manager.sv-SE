---
description: Processen för utgående dataöverföring för kunder som använder Amazon Simple Storage Service (Amazon S3) kräver att vi frågar efter din åtkomstnyckel och hemliga nyckel för Amazon S3 för att kunna leverera de utgående datafilerna till din bucket.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Utnyttja Amazon S3-behörigheter för kontoöverskridande paket för utgående filer
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 7302fafa537ad15144a64cc96f7150c5b0233c12
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Utnyttja Amazon S3-behörigheter för kontoöverskridande paket för utgående filer {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Processen [!UICONTROL Outbound Data Transfer] för kunder som använder [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) kräver att vi frågar efter din [!DNL Amazon S3]-åtkomstnyckel och hemliga nyckel för att kunna leverera de utgående datafilerna till din bucket.

Om du inte vill dela din [!DNL Amazon S3]-åtkomstnyckel och hemliga nyckel med oss kontaktar du din [!DNL Audience Manager]-konsult eller kundtjänst så konfigurerar de [!DNL Cross-Account Bucket Permissions] åt dig.

Du behöver bara lägga till ditt konto-ID för [!DNL Amazon S3] i en tillåtelselista för den [!DNL S3]-bucket där du vill ta emot de utgående datafilerna, enligt beskrivningen i [Amazon S3-dokumentationen](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Din [!DNL Audience Manager]-konsult eller kundtjänst kommer att förse dig med ditt [!DNL Amazon S3] konto-ID.
