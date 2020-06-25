---
description: Beskriver integrering av Audience Manager och efterlevnad av allmänt vedertagna bästa metoder för konsumentintegritet och avanmälningsförfaranden.
seo-description: Beskriver integrering av Audience Manager och efterlevnad av allmänt vedertagna bästa metoder för konsumentintegritet och avanmälningsförfaranden.
seo-title: Översikt över dataintegritet
solution: Audience Manager
title: Översikt över dataintegritet
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---


# Översikt över dataintegritet {#data-privacy}

## Översikt

Dokumentationen om dataintegritet beskriver hur man [!DNL Audience Manager] integrerar och följer allmänt vedertagna bästa metoder för konsumentintegritet och avanmälningsförfaranden.

[!DNL Audience Manager] Parlamentet erkänner vikten av förhållandet mellan konsumenterna och de onlinevarumärken de interagerar med. Båda parter drar nytta av det transparenta utbytet av pseudonyma dataelement:

* Konsumenterna får personaliserat innehåll, rabatterade produkterbjudanden och smidiga användarupplevelser.
* Varumärken får viktiga intäktsströmmar som stöder flera onlineaffärsmodeller.

I vårt fortsatta stöd för den här modellen är vi fast beslutna att ge er de verktyg som behövs för att ni ska kunna tillhandahålla transparens och kontroll till era kunder, samtidigt som ni levererar personaliserade annonser som är föremål för [!DNL Audience Manager] självreglerande principer [](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/)för onlineannonsering (OBA).

## [!DNL GDPR] {#gdpr}

I den [allmänna dataskyddsförordningen (GDPR)](https://eugdpr.org/) infördes flera nya integritetsrättigheter för EU-medlemmar, bland annat **rätten till tillgång** och **rätten att bli glömd**. Detta innebär att alla [!DNL EU] medborgare vars personuppgifter har samlats in av ditt företag när som helst kan begära åtkomst till eller radera sina uppgifter. Om du inte uppfyller dessa krav kan det leda till böter på flera miljoner dollar för din organisation.

För att uppfylla detta [!DNL GDPR]stöder [!DNL Audience Manager] dataåtkomst och [borttagningsbegäranden](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

I [California Consumer Privacy Act (CCPA)](https://www.caprivacy.org/about), som trädde i kraft den 1 januari 2020, ges personer bosatta i Kalifornien nya rättigheter när det gäller personuppgifter och åläggs dataskyddsansvar för vissa enheter som bedriver verksamhet i Kalifornien.

[!DNL CCPA] ger personer bosatta i Kalifornien nya integritetsrättigheter, inklusive rätten att få tillgång till och radera sina personuppgifter och att få veta om deras personuppgifter säljs eller offentliggörs (och till vem). För att uppfylla detta [!DNL CCPA]har [!DNL Audience Manager] stöd för [!DNL CCPA] åtkomst och borttagning av [begäranden](data-privacy-requests.md).

Mer information finns på [Adobes sekretesscenter](https://www.adobe.com/privacy/opt-out.html) .

## Regelefterlevnad {#compliance}

[!DNL Audience Manager] hjälper dig att uppfylla dina skyldigheter enligt vissa sekretessbestämmelser, via sekretessverktyg som [Adobe Experience Platform Privacy Servicen](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) för förfrågningar om dataåtkomst och radering.

Den här tjänsten tillhandahåller ett [!DNL RESTful API] och användargränssnitt som hjälper dig att hantera förfrågningar om konsumentdata. Med hjälp av [Privacy Servicen](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)kan ni skicka in förfrågningar om att få tillgång till och radera personuppgifter, baserat på en enskild kunds begäran, vilket hjälper er att automatisera denna del av era efterlevnadsskyldigheter.

Begäran om dataåtkomst och borttagning hanteras via [Privacy Servicen](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), men [avanmälningsbegäranden](data-privacy-requests.md#opt-out-requests) stöds för närvarande via [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). Mer information finns i [Datasekretessbegäranden](data-privacy-requests.md) .

## Relaterade begrepp {#related-concepts}

* [Begäranden om dataintegritet](data-privacy-requests.md)
* [Hantering av samtycke](data-privacy-consent.md)
* [Plugin-programmet Audience Manager för IAB TCF](aam-iab-plugin.md)
* [Audience Manager-identifierare](data-privacy-ids.md)
* [CCPA-ordlista](aam-ccpa-glossary.md)
* [GDPR - ordlista](aam-gdpr-glossary.md)
* [GDPR-överväganden för destinationer](aam-gdpr-partners.md)
* [GDPR:s beredskapsvägledning för Audience Manager-kunder](aam-gdpr-readiness.md)
* [Datastyrning](data-governance.md)
* [Vanliga frågor om sekretess och datalagring](../../faq/faq-privacy.md)