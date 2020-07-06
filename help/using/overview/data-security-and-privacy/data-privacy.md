---
description: Beskriver Audience Manager-integrering och efterlevnad med allmänt vedertagna metoder för konsumentsekretess och avanmälan.
seo-description: Beskriver Audience Manager-integrering och efterlevnad med allmänt vedertagna metoder för konsumentsekretess och avanmälan.
seo-title: Översikt över datasekretess
solution: Audience Manager
title: Översikt över datasekretess
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 78%

---


# Översikt över datasekretess {#data-privacy}

## Översikt

The Data Privacy documentation describes [!DNL Audience Manager] integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.

[!DNL Audience Manager] inser hur viktig relationen är mellan konsumenterna och de varumärken som de interagerar med online. Båda parter drar nytta av det transparenta utbytet av pseudonyma dataelement:

* Konsumenterna får personaliserat innehåll, rabatterade produkterbjudanden och smidiga användarupplevelser.
* Varumärken får viktiga intäktsströmmar som stöder flera onlineaffärsmodeller.

In our continuing support of this model, [!DNL Audience Manager] remains committed to providing you with the tools to help support your ability to provide  transparency and control to your consumers, while delivering personalized ads subject to the [Online Behavioral Advertising (OBA) Self-Regulatory Principles](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

I den [allmänna dataskyddsförordningen (GDPR)](https://eugdpr.org/) infördes flera nya rättigheter för EU-medlemmar, bland annat **rätten till åtkomst** och **rätten att raderas**. This means that any [!DNL EU] citizen whose personal data has been collected by your business can request to access or delete their data at any time. Om ni inte uppfyller dessa krav kan det leda till böter på flera miljoner dollar för er organisation.

To comply with [!DNL GDPR], [!DNL Audience Manager] supports data access and delete [requests](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

I [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), som trädde i kraft den 1 januari 2020, ges personer bosatta i Kalifornien nya rättigheter när det gäller personuppgifter och det gör att vissa enheter som bedriver verksamhet i Kalifornien åläggs dataskyddsansvar.

[!DNL CCPA] ger personer bosatta i Kalifornien nya rättigheter, inklusive rätten att få tillgång till och radera personuppgifter och att få veta om personuppgifter säljs eller offentliggörs (och till vem). För att uppfylla detta [!DNL CCPA]har [!DNL Audience Manager] stöd för [!DNL CCPA] åtkomst och borttagning av [begäranden](data-privacy-requests.md).

Mer information finns på [Adobes sekretesscenter](https://www.adobe.com/se/privacy/opt-out.html#customeruse).

## Regelefterlevnad {#compliance}

[!DNL Audience Manager] hjälper er att uppfylla era skyldigheter enligt vissa sekretessregler via sekretessverktyg som [Adobe Experience Platform Privacy Service](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html) för förfrågningar om åtkomst och radering av data.

Den här tjänsten tillhandahåller ett [!DNL RESTful API] och användargränssnitt som hjälper er att hantera förfrågningar om konsumentdata. Med hjälp av [Privacy Service](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html) kan ni skicka förfrågningar om att få tillgång till och radera personuppgifter baserat på en kunds begäran vilket hjälper er att automatisera denna del av era efterlevnadsskyldigheter.

Begäran om åtkomst och borttagning av data hanteras via [Privacy Service](https://docs.adobe.com/content/help/sv-SE/experience-platform/privacy/home.html), men [förfrågningar om avanmälan](data-privacy-requests.md#opt-out-requests) stöds för närvarande via [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Mer information finns i [Förfrågningar om datasekretess](data-privacy-requests.md).

## Relaterade begrepp {#related-concepts}

* [Förfrågningar om datasekretess](data-privacy-requests.md)
* [Hantering av samtycke](data-privacy-consent.md)
* [Plugin-program för Audience Manager för IAB TCF](aam-iab-plugin.md)
* [Identifierare i Audience Manager](data-privacy-ids.md)
* [CCPA-ordlista](aam-ccpa-glossary.md)
* [GDPR-ordlista](aam-gdpr-glossary.md)
* [GDPR-överväganden för destinationer](aam-gdpr-partners.md)
* [GDPR-vägledning för Audience Manager-kunder](aam-gdpr-readiness.md)
* [Datastyrning](data-governance.md)
* [Vanliga frågor om sekretess och datalagring](../../faq/faq-privacy.md)