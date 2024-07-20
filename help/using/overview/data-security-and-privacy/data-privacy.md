---
description: Beskriver Audience Manager-integrering och efterlevnad med allmänt vedertagna metoder för konsumentsekretess och avanmälan.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: Översikt över datasekretess
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 52%

---

# Översikt över datasekretess {#data-privacy}

## Översikt

Dokumentationen om dataintegritet beskriver [!DNL Audience Manager]-integrering och kompatibilitet med allmänt accepterade bästa metoder för konsumentsekretess och avanmälningsförfaranden.

[!DNL Audience Manager] inser vikten av relationen mellan konsumenterna och de onlinevarumärken de interagerar med. Båda parter drar nytta av det transparenta utbytet av pseudonyma dataelement:

* Konsumenterna får personaliserat innehåll, rabatterade produkterbjudanden och smidiga användarupplevelser.
* Varumärken får viktiga intäktsströmmar som stöder flera onlineaffärsmodeller.

I vårt fortsatta stöd för den här modellen fortsätter [!DNL Audience Manager] att tillhandahålla verktyg som hjälper dig att tillhandahålla transparens och kontroll till dina kunder, samtidigt som personaliserade annonser levereras i enlighet med [Advertising självreglerande principer för onlinebeteende](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/) (OBA).

## [!DNL GDPR] {#gdpr}

I den [allmänna dataskyddsförordningen (GDPR)](https://gdpr.eu/data-privacy/) infördes flera nya rättigheter för EU-medlemmar, bland annat **rätten till åtkomst** och **rätten att raderas**. Det innebär att alla [!DNL EU]-medborgare vars personuppgifter har samlats in av ditt företag kan begära åtkomst till eller radera sina data när som helst. Om ni inte uppfyller dessa krav kan det leda till böter på flera miljoner dollar för er organisation.

För att uppfylla kraven för [!DNL GDPR] stöder [!DNL Audience Manager] dataåtkomst och [borttagningsbegäranden](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

I [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), som trädde i kraft den 1 januari 2020, ges personer bosatta i Kalifornien nya rättigheter när det gäller personuppgifter och det gör att vissa enheter som bedriver verksamhet i Kalifornien åläggs dataskyddsansvar.

[!DNL CCPA] ger personer bosatta i Kalifornien nya integritetsrättigheter, inklusive rätten att få tillgång till och ta bort sina personuppgifter och att få veta om deras personuppgifter säljs eller avslöjas (och till vem). [!DNL Audience Manager] stöder [!DNL CCPA] åtkomst och borttagning av [förfrågningar](data-privacy-requests.md) för att uppfylla kraven för [!DNL CCPA].

Mer information finns på [Adobes sekretesscenter](https://www.adobe.com/se/privacy/opt-out.html#customeruse).

## Regelefterlevnad {#compliance}

[!DNL Audience Manager] hjälper dig att uppfylla dina skyldigheter enligt vissa sekretessregler, via sekretessverktyg som [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) för dataåtkomst och borttagningsbegäranden.

Den här tjänsten tillhandahåller ett [!DNL RESTful API] och användargränssnitt som hjälper er att hantera förfrågningar om konsumentdata. Med hjälp av [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) kan ni skicka förfrågningar om att få tillgång till och radera personuppgifter baserat på en kunds begäran vilket hjälper er att automatisera denna del av era efterlevnadsskyldigheter.

Dataåtkomst- och borttagningsbegäranden hanteras via Privacy Servicen, men [avanmälningsbegäranden](data-privacy-requests.md#opt-out-requests) stöds för närvarande via [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Mer information finns i [Förfrågningar om datasekretess](data-privacy-requests.md).

## Relaterade begrepp {#related-concepts}

* [Förfrågningar om datasekretess](data-privacy-requests.md)
* [Hantering av samtycke](data-privacy-consent.md)
* [Plugin-program för Audience Manager för IAB TCF](aam-iab-plugin.md)
* [Audience Manager-identifierare](data-privacy-ids.md)
* [CCPA-ordlista](aam-ccpa-glossary.md)
* [GDPR-ordlista](aam-gdpr-glossary.md)
* [GDPR-överväganden för destinationer](aam-gdpr-partners.md)
* [GDPR-vägledning för Audience Manager-kunder](aam-gdpr-readiness.md)
* [Datastyrning](data-governance.md)
* [Vanliga frågor om sekretess och datalagring](../../faq/faq-privacy.md)
