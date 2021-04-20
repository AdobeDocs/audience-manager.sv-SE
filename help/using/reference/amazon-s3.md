---
description: Information om Amazon Simple Storage Service (Amazon S3).
seo-description: Information om Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3 Om
solution: Audience Manager
title: Amazon S3 Om
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3: Om{#amazon-s-about}

Information om Amazon Simple Storage Service (Amazon S3).

Vi rekommenderar att du använder Amazon S3 i stället för FTP som en metod för att hämta filer från och leverera filer till partners. Amazon S3 har ett enkelt webbtjänstgränssnitt som kan användas för att lagra och hämta valfri mängd data när som helst, var som helst på webben.

Fördelarna med att använda Amazon S3 är bland annat:

* **Skalbarhet:** Amazon S3 ger nästan obegränsad skalbarhet.
* **Tillförlitlighet och tillgänglighet:** Amazon S3 ger lagringstjänster med hög hållbarhet och hög tillgänglighet.
* **Hastighet:** Amazon S3 tillåter snabba dataöverföringar.
* **Lätt att använda:** Amazon S3 är mycket enkelt att använda och implementera. Implementeringen kan vara igång om ungefär en timme. Det tar mycket längre tid att implementera en FTP-katalog.
* **Överföring av flera delar:** Stora filer kan överföras snabbt och effektivt när flera delar överförs.
* **Säkerhet:** Amazon S3 ger stark säkerhet.

   * Alla kataloger är bara tillgängliga för rätt kund eller kund.
   * Stöd för HTTPS-protokoll för överföringar och nedladdningar. Du bör alltid använda HTTPS när du överför filer i [!DNL Audience Manager].
   * Amazon S3 erbjuder kryptering vid vila för kryptering av [utgående datafiler](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Vi använder krypteringsmetoden [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html), som gör att krypteringsnycklar automatiskt genereras och hanteras av Amazon S3.

* **Stöd för felsökning och säkerhetskopiering:** Amazon S3 gör  [!DNL Audience Manager] att du kan spara exakta kopior av filer för att underlätta felsökning och återöverföringar.

Mer information om Amazon S3 finns i följande resurser:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) på Amazon webbplats för webbtjänster.

[Kom igång med Amazon Simple Storage ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Service på webbplatsen AWS Documentation.
