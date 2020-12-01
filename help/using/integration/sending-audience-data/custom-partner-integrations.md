---
description: På den här sidan visas anpassade integreringar mellan Audience Manager och datapartner.
seo-description: På den här sidan visas anpassade integreringar mellan Audience Manager och datapartner.
seo-title: Anpassade partnerintegreringar
solution: Audience Manager
title: Anpassade partnerintegreringar
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 3%

---


# Anpassade partnerintegreringar {#custom-partner-integrations}

På den här sidan visas anpassade integreringar mellan Audience Manager och datapartner.

## Oracle Data Cloud {#oracle-data-cloud}

### Beskrivning

Audience Manager inhämtar cookie- och mobil-ID-data från Oracle Data Cloud för Audience Marketplace via inkommande datafiler. Specifikationerna för anpassad integrering som beskrivs nedan avser endast inkommande datafiler som innehåller mobila ID:n (IDFA och Android Device ID).

### Integrationsinformation

Inkommande datafiler som tas emot från Oracle Data Cloud skiljer sig från standardsyntaxen för inkommande filnamn som beskrivs i [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) och från standardsyntaxen för inkommande filinnehåll som beskrivs i [Innehåll i inkommande datafil: Syntax, ogiltiga tecken, variabler och exempel](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

De element som markeras nedan är obligatoriska, förutom standardimplementeringsfälten för inkommande datafiler. Beskrivningar av alla andra standardfält och filnamnselement finns i Filnamnssyntax och Syntax för filinnehåll på de två sidor som är länkade ovan.

### Namnge filer

ODC-filnamn är strukturerade som:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Filnamnselementet `odc` identifierar filen som importerad från Oracle Data Cloud och instruerar filvalideraren för inkommande Audience Manager att bearbeta den som sådan.

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