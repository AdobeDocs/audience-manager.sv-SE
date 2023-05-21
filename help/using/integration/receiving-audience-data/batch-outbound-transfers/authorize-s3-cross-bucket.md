---
description: Processen för utgående dataöverföring för kunder som använder Amazon Simple Storage Service (Amazon S3) kräver att vi frågar efter din åtkomstnyckel och hemliga nyckel för Amazon S3 för att kunna leverera de utgående datafilerna till din bucket.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Utnyttja behörigheter för Amazon S3 Cross Account Bucket för utgående filer
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 12%

---

# Utnyttja behörigheter för Amazon S3 Cross Account Bucket för utgående filer {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

The [!UICONTROL Outbound Data Transfer] för kunder som använder [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) kräver att vi frågar efter [!DNL Amazon S3] åtkomstnyckel och hemlig nyckel för att kunna leverera utgående datafiler till din bucket.

Om du inte vill dela dina [!DNL Amazon S3] åtkomstnyckel och hemlig nyckel till oss, kontakta [!DNL Audience Manager] konsult eller kundtjänst så kommer de att konfigurera [!DNL Cross-Account Bucket Permissions] för dig. Du behöver bara lägga till [!DNL Amazon S3] konto-ID till tillåtelselista för [!DNL S3] bucket där du vill ta emot utgående datafiler, enligt beskrivningen i [Amazon S3-dokumentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Dina [!DNL Audience Manager] konsult eller kundtjänst kommer att ge dig våra [!DNL Amazon S3] konto-ID.
