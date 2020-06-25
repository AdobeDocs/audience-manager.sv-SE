---
description: Betamiljön används för att testa implementeringen av Audience Manager. Ändringar som görs i betaversionen påverkar inte produktionsdata. Kontakta din Audience Manager Partner Solutions-representant om du är intresserad av att använda betamiljön.
keywords: sandbox
seo-description: Betamiljön används för att testa implementeringen av Audience Manager. Ändringar som görs i betaversionen påverkar inte produktionsdata. Kontakta din Audience Manager Partner Solutions-representant om du är intresserad av att använda betamiljön.
seo-title: Beta-miljö
solution: Audience Manager
title: Beta-miljö
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 3%

---


# Beta-miljö {#beta-environment}

Betamiljön används för att testa implementeringen av Audience Manager. Ändringar som görs i betaversionen påverkar inte produktionsdata. Kontakta din Audience Manager Partner Solutions-representant om du är intresserad av att använda betamiljön.

## Översikt

Betamiljön är en exakt kopia av produktionsmiljön, utan några experimentella eller osläppliga funktioner. Dina inloggningsuppgifter från produktionsmiljön är giltiga i betaversionen.

**Uppdatera schema**

Betamiljön uppdateras i slutet av varje månad under tider med låg belastning.

**Utgående trafik**

Utgående trafik är inte aktiverat för betamiljön.

<!-- 

Added re: AAM-30826.

 -->

## Slutpunkter



| Tjänst | URL/värdnamn | Hur man får åtkomst |
|--- |--- | --- |
| S3 | Kontakta din Audience Manager Partner Solutions-representant eller kundtjänst | Kontakta din Audience Manager Partner Solutions-representant eller kundtjänst om du vill konfigurera en Amazon S3-bucket för din betainstans. Läs om [fördelarna med att använda Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Se [Åtkomst till DCS i betamiljön](../reference/beta-environment.md#access-dcs-beta-environment). |
| UI | `https://bank-beta.demdex.com` | Autentiseringsuppgifterna för produktionsmiljön gäller för betamiljön. |
| API | `https://api-beta.demdex.com/...` | Autentiseringsuppgifterna för produktionsmiljön gäller för betamiljön. Vi rekommenderar att du skapar en allmän API-användare, [se informationen](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Åtkomst till DCS i betamiljön {#access-dcs-beta-environment}

1. Gör ett DCS-anrop med [kommandot](https://curl.haxx.se/docs/manpage.html)curl. Curl är ett verktyg som du kan använda för att överföra data från eller till en server med hjälp av ett av många protokoll som stöds.

   Exempel:

   `curl -v https://dcs-beta.demdex.net/event`

1. Kontrollera att din begäran har hanterats av beta-DCS genom att söka efter&quot;sandbox&quot; i DCS-svarshuvudet.

   Exempel:

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->