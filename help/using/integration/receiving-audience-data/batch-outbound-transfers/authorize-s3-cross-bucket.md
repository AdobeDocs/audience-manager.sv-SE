---
description: Processen för utgående dataöverföring för kunder som använder Amazon Simple Storage Service (Amazon S3) kräver att vi frågar efter din åtkomstnyckel och hemliga nyckel för Amazon S3 för att kunna leverera de utgående datafilerna till din bucket.
seo-description: Processen för utgående dataöverföring för kunder som använder Amazon Simple Storage Service (Amazon S3) kräver att vi frågar efter din åtkomstnyckel och hemliga nyckel för Amazon S3 för att kunna leverera de utgående datafilerna till din bucket.
seo-title: Utnyttja behörigheter för Amazon S3 Cross Account Bucket för utgående filer
solution: Audience Manager
title: Utnyttja behörigheter för Amazon S3 Cross Account Bucket för utgående filer
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# Utnyttja behörigheter för Amazon S3 Cross Account Bucket för utgående filer {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Processen [!UICONTROL Outbound Data Transfer] för kunder som använder [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) kräver att vi frågar efter din [!DNL Amazon S3] åtkomstnyckel och hemliga nyckel för att kunna leverera de utgående datafilerna till din bucket.

Om du inte vill dela din [!DNL Amazon S3] åtkomstnyckel och hemliga nyckel med oss kontaktar du din [!DNL Audience Manager] konsult eller kundtjänst så konfigureras de [!DNL Cross-Account Bucket Permissions] åt dig. Du behöver bara lägga till ditt [!DNL Amazon S3] konto-ID i en tillåtelselista för den [!DNL S3] bucket där du vill få de utgående datafilerna, vilket beskrivs i [Amazon S3-dokumentationen](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Din [!DNL Audience Manager] konsult eller kundtjänst kommer att förse dig med ditt [!DNL Amazon S3] konto-ID.