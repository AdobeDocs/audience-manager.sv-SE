---
description: Betamiljön används för att testa din Audience Manager-implementering. Ändringar som görs i betaversionen påverkar inte produktionsdata. Kontakta din Audience Manager Partner Solutions-representant om du är intresserad av att använda betamiljön.
keywords: sandlåda
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta Environment
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---

# Beta Environment {#beta-environment}

Betamiljön används för att testa din Audience Manager-implementering. Ändringar som görs i betaversionen påverkar inte produktionsdata. Kontakta din Audience Manager Partner Solutions-representant om du är intresserad av att använda betamiljön.

## Översikt

Funktionen i Bveta-miljön är en exakt kopia av produktionsmiljön, utan några experimentella eller osläppliga funktioner. Dina inloggningsuppgifter från produktionsmiljön är giltiga i betaversionen.

**Uppdatera schema**

Betamiljön uppdateras i slutet av varje månad under tider med låg belastning.

>[!IMPORTANT]
>
>Observera att dina kunddata ([signaler, egenskaper och segment](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=sv-SE)) inte synkroniseras mellan produktions- och betamiljöerna.

## Inkommande trafik

Betaversionen stöder endast inkommande trafik för filnamns- och innehållssyntaxvalidering. Eftersom ingen ID-mappning görs i betamiljön ser kunderna inga segmentpopulationer.

Därför kommer sidan [!UICONTROL Onboarding Status] alltid att rapportera [!UICONTROL No matching AAM ID] när filen har importerats till betamiljön.

Vi rekommenderar alla kunder att utföra inkommande tester i sin produktionsmiljö.

## Utgående trafik

Utgående trafik är inte aktiverat för betamiljön.

## Slutpunkter

| Tjänst | URL/värdnamn | Hur man får åtkomst |
|--- |--- | --- |
| S3 | Kontakta din Audience Manager Partner Solutions-representant eller kundtjänst | Kontakta din Audience Manager Partner Solutions-representant eller kundtjänst för att skapa en Amazon S3-bucket för din betainstans. Läs om [fördelarna med att använda Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Se [Åtkomst till DCS i Beta-miljön](../reference/beta-environment.md#access-dcs-beta-environment). |
| UI | `https://bank-beta.demdex.com` | Autentiseringsuppgifterna för produktionsmiljön gäller för betamiljön. |
| API | `https://api-beta.demdex.com/...` | Autentiseringsuppgifterna för produktionsmiljön gäller för betamiljön. Vi rekommenderar att du skapar en allmän API-användare, [se information](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Åtkomst till DCS i Beta-miljön {#access-dcs-beta-environment}

1. Gör ett DCS-anrop med kommandot [curl](https://curl.haxx.se/docs/manpage.html). Curl är ett verktyg som du kan använda för att överföra data från eller till en server med hjälp av ett av många protokoll som stöds.

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
