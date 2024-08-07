---
description: På den här sidan visas anpassade integreringar mellan Audience Manager och datapartner.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Anpassade partnerintegreringar
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# Anpassade partnerintegreringar {#custom-partner-integrations}

På den här sidan visas anpassade integreringar mellan Audience Manager och datapartner.

## Oracle Data Cloud {#oracle-data-cloud}

### Beskrivning

Audience Manager inhämtar cookie- och mobil-ID-data från Oracle Data Cloud för Audience Marketplace via inkommande datafiler. Specifikationerna för anpassad integrering som beskrivs nedan avser endast inkommande datafiler som innehåller mobila ID:n (IDFA och Android Device ID).

### Integrationsinformation

Inkommande datafiler som tas emot från Oraclet Data Cloud skiljer sig från standardsyntaxen för inkommande filnamn, som beskrivs i [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md), och från standardsyntaxen för inkommande filinnehåll, som beskrivs i [Innehåll i den inkommande datafilen: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

De element som markeras nedan är obligatoriska, förutom standardimplementeringsfälten för inkommande datafiler. Beskrivningar av alla andra standardfält och filnamnselement finns i Filnamnssyntax och Syntax för filinnehåll på de två sidor som är länkade ovan.

### Namnge filer

ODC-filnamn är strukturerade som:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Filnamnselementet `odc` identifierar filen som importerad från Oraclet Data Cloud och instruerar den inkommande filvalideraren i Audience Manager att bearbeta den som sådan.

### Filinnehåll

Fält i ODC-filen för inkommande data måste visas i den ordning som visas nedan:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type` kan vara:

* IDFA
* Android-enhets-ID

>[!IMPORTANT]
>
>Skicka inte IDFA- och Android-enhets-ID:n i samma inkommande datafil.

## Exempel på ODC-inkommande fil

Hämta [exempelfilen](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Den här filen kvalificerar flera IDFA:er för trait ID 38838. Du kan öppna den här filen i en vanlig textredigerare eller kodredigerare.
