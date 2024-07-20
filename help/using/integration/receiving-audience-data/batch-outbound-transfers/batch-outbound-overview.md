---
description: Audience Manager skickar batchdata till tredjepartsleverantörer av innehåll enligt dessa specifikationer.
seo-description: Adobe Audience Manager (AAM) sends batch data to third-party content providers according to these specifications.
seo-title: Batch Outbound Data Transfers in Adobe Audience Manager (AAM)
title: Batchutgående dataöverföringar
feature: Outbound Data Transfers
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Batchutgående dataöverföringar

Audience Manager skickar batchdata till tredjepartsleverantörer av innehåll enligt dessa specifikationer.

* [Namn på utgående datafil: Syntax och exempel](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

  Beskriver obligatoriska fält, syntax och konventioner som används för att namnge en utgående datafil.

* [Konfigurera integrering av batchdataöverföring](batch-server-configuration.md)

  Beskriver de metoder som du kan använda för att konfigurera batchdataöverföringsintegrering.

* [Överföringskontrollfiler för loggfilsöverföringar](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

  Filer med överföringskontroll (.info) innehåller metadatainformation om filöverföringar så att partners kan verifiera att filöverföringar hanteras på rätt sätt i Audience Manager.

* [Utgående mallmakron](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

  Visar makron som du kan använda för att skapa utgående mallar. Bland dessa finns filnamnsmakron, huvudmakron och innehållsmakron.

* [Exempel på utgående makro](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

  Exempel på hur några av de vanliga makrona används för att skapa utgående filmallar.

* [Utnyttja Amazon S3-behörigheter för kontoöverskridande paket för utgående filer](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

  Processen för utgående dataöverföring för kunder som använder Amazon Simple Storage Service (Amazon S3) kräver att vi frågar efter din åtkomstnyckel och hemliga nyckel för Amazon S3 för att kunna leverera de utgående datafilerna till din bucket.
