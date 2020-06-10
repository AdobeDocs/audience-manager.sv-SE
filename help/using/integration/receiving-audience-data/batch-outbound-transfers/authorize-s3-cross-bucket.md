---
description: Processen för utgående dataöverföring för kunder som använder Amazon Simple Storage Service (Amazon S3) kräver att vi frågar efter din åtkomstnyckel och hemliga nyckel för Amazon S3 för att kunna leverera de utgående datafilerna till din bucket.
seo-description: Processen för utgående dataöverföring för kunder som använder Amazon Simple Storage Service (Amazon S3) kräver att vi frågar efter din åtkomstnyckel och hemliga nyckel för Amazon S3 för att kunna leverera de utgående datafilerna till din bucket.
seo-title: Utnyttja behörigheter för Amazon S3 Cross Account Bucket för dina utgående filer
solution: Audience Manager
title: Utnyttja behörigheter för Amazon S3 Cross Account Bucket för dina utgående filer
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---


# Utnyttja behörigheter för Amazon S3 Cross Account Bucket för dina utgående filer {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Processen [!UICONTROL Outbound Data Transfer] för kunder som använder [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) kräver att vi frågar efter din [!DNL Amazon S3] åtkomstnyckel och hemliga nyckel för att kunna leverera de utgående datafilerna till din bucket.

Om du inte vill dela din [!DNL Amazon S3] åtkomstnyckel och hemliga nyckel med oss kontaktar du din [!DNL Audience Manager] konsult eller kundtjänst så konfigureras de [!DNL Cross-Account Bucket Permissions] åt dig. Du behöver bara lägga till ditt [!DNL Amazon S3] konto-ID i en Tillåt-lista för den [!DNL S3] bucket där du vill ta emot utgående datafiler, enligt beskrivningen i [Amazon S3-dokumentationen](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Din [!DNL Audience Manager] konsult eller kundtjänst kommer att förse dig med ditt [!DNL Amazon S3] konto-ID.