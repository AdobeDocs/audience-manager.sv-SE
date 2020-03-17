---
description: Beskriver Audience Manager-integrering och efterlevnad av allmänt vedertagna bästa metoder för konsumentsekretess och avanmälningsförfaranden.
seo-description: Beskriver Audience Manager-integrering och efterlevnad av allmänt vedertagna bästa metoder för konsumentsekretess och avanmälningsförfaranden.
seo-title: Översikt över dataintegritet
solution: Audience Manager
title: Översikt över dataintegritet
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: f8184dfccdb7b5cbc3ace67831d988dd8061ea38

---


# Översikt över dataintegritet {#data-privacy}

## Översikt

Dokumentationen om datasekretess beskriver Audience Manager-integrering och efterlevnad av allmänt vedertagna bästa metoder för konsumentsekretess och avanmälningsförfaranden.

Audience Manager inser vikten av relationen mellan konsumenterna och de onlinevarumärken de interagerar med. Båda parter drar nytta av det transparenta utbytet av pseudonyma dataelement:

* Konsumenterna får personaliserat innehåll, rabatterade produkterbjudanden och smidiga användarupplevelser.
* Varumärken får viktiga intäktsströmmar som stöder flera onlineaffärsmodeller.

I vårt fortsatta stöd för den här modellen fortsätter Audience Manager att ge er de verktyg ni behöver för att kunna erbjuda era kunder transparens och kontroll, samtidigt som ni levererar personaliserade annonser som omfattas av [självreglerande principer](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)för onlineannonsering (OBA).

 

I den [allmänna dataskyddsförordningen (GDPR)](https://eugdpr.org/) infördes flera nya integritetsrättigheter för EU-medlemmar, bland annat **rätten till tillgång** och **rätten att bli glömd**. Detta innebär att alla EU-medborgare vars personuppgifter har samlats in av ert företag när som helst kan begära att få tillgång till eller radera sina uppgifter. Om du inte uppfyller dessa krav kan det leda till böter på flera miljoner dollar för din organisation.

För att uppfylla GDPR stöder Audience Manager [förfrågningar](data-privacy-requests.md)om dataåtkomst och radering.

I [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), som trädde i kraft den 1 januari 2020, ges personer bosatta i Kalifornien nya rättigheter när det gäller personuppgifter och åläggs dataskyddsansvar för vissa enheter som bedriver verksamhet i Kalifornien.

CCPA ger personer bosatta i Kalifornien nya integritetsrättigheter, inklusive rätten att få tillgång till och radera sina personuppgifter och att få veta om deras personuppgifter säljs eller offentliggörs (och till vem). För att uppfylla kraven i CCPA har Audience Manager stöd för CCPA-åtkomst och [borttagningsbegäranden](data-privacy-requests.md).

Mer information finns på [Adobes sekretesscenter](https://www.adobe.com/privacy/opt-out.html) .

## Regelefterlevnad {#compliance}

Audience Manager hjälper er att uppfylla era skyldigheter enligt vissa sekretessregler, via sekretessverktyg som [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) för dataåtkomst och borttagningsbegäranden.

Den här tjänsten tillhandahåller ett [!DNL RESTful API] och användargränssnitt som hjälper dig att hantera förfrågningar om konsumentdata. Med hjälp av [Integritetstjänsten](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)kan ni skicka in förfrågningar om att få tillgång till och radera personuppgifter, baserat på en enskild kunds begäran, vilket hjälper er att automatisera denna del av era efterlevnadsskyldigheter.

Begäran om åtkomst och borttagning av data hanteras via [sekretesstjänsten](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), men [avanmälningsbegäranden](data-privacy-requests.md#opt-out-requests) stöds för närvarande via [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Mer information finns i [Datasekretessbegäranden](data-privacy-requests.md) .

## Relaterade begrepp {#related-concepts}

* [Begäranden om dataintegritet](data-privacy-requests.md)
* [Hantering av samtycke](data-privacy-consent.md)
* [Plugin-program för Audience Manager för IAB TCF](aam-iab-plugin.md)
* [Identifierare för Audience Manager](data-privacy-ids.md)
* [CCPA-ordlista](aam-ccpa-glossary.md)
* [GDPR - ordlista](aam-gdpr-glossary.md)
* [GDPR-överväganden för destinationer](aam-gdpr-partners.md)
* [GDPR-beredskapsvägledning för kunder med Audience Manager](aam-gdpr-readiness.md)
* [Datastyrning](data-governance.md)
* [Vanliga frågor om sekretess och datalagring](../../faq/faq-privacy.md)