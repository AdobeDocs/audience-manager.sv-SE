---
description: Det här dokumentet förklarar hur samtyckeshantering fungerar i Audience Manager.
seo-description: Det här dokumentet förklarar hur samtyckeshantering fungerar i Audience Manager.
seo-title: Hantering av samtycke
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Hantering av samtycke
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 100%

---


# Hantering av samtycke

## Översikt {#overview}

Om samtycke krävs för vissa marknadsföringsaktiviteter måste Audience Manager-kunderna bestämma omfattningen och huruvida samtycke måste uppdateras för att fortsätta använda data i framtiden.

Audience Manager har verktyg som hjälper er att inhämta samtycke från era användare så att ni kan leverera personaliserade upplevelser till dem i alla kanaler.

>[!IMPORTANT]
>
> Innehållet i detta dokument är inte juridisk rådgivning och är inte avsett att ersätta juridisk rådgivning.
>
> Som personuppgiftsbiträde kan Adobe inte ge juridisk rådgivning när det gäller att inhämta samtycke. Ni kan överväga att samarbeta med en leverantör av lösningar för samtyckeshantering, som [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) eller [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), och fråga företagets juridiska avdelning om råd angående samtycke och rutiner när ni konfigurerar anmälningar.

## Experience Cloud Opt-in Service

Med [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/sv-SE/id-service/using/implementation/opt-in-service/optin-overview.html) kan ni konfigurera protokoll för besökare som hjälper er att avgöra om ni kan placera en cookie på personens enhet eller webbläsare när hen besöker er webbplats.

Detta är ett tillägg till [!DNL Experience Cloud ID (ECID) Service] som är utformat för att ni ska kunna kontrollera om och vilka Experience Cloud-lösningar som kan placera cookies på webbsidor för besökare innan användaren ger sitt samtycke.

Med [Experience Cloud Opt-In Service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) kan ni också ange protokoll som ska integreras med er plattform för hantering av samtycke (CMP) och befintliga system som en del av er större design.

## Hantera anmälan/inhämtning av samtycke

Audience Manager-kunder kan lagra samtycke för användare för olika ändamål som annonsering eller personalisering som traits i Audience Manager. Segment som du bygger med dessa traits kommer då bara att omfatta användare som gett samtycke för användningsområdet. Observera att datainsamlingen inte avbryts om du använder den här metoden, dataanvändningen påverkas bara när du skickar segment för aktivering. När användare återkallar sitt samtycke kan du ta bort dessa traits från användarprofilen med Audience Managers [inkommande satsvisa process](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) eller Audience Manager-avanmälningsprocessen som beskrivs nedan.

## Hantera avanmälan/återtagande av samtycke

Du kan hantera avanmälan för Adobe Experience Cloud via sidan [Your Privacy Choices](https://www.adobe.com/se/privacy/opt-out.html#customeruse). Med enklicksfunktioner kan slutanvändarna styra och avanmäla datainsamling via annonslösningarna i Adobe Experience Cloud (inklusive Audience Manager). Mer information finns i avsnittet för [företagskunder ](https://www.adobe.com/privacy/opt-out.html#customeruse) på sidan Privacy Choices. Information om webbläsare som inte stöder cookies från tredje part finns i [Deklarerad ID-anpassning](../../features/declared-ids.md#declared-id-targeting). För mobila enheter kan du hämta relevanta Audience Manager-identifierare och anropa Audience Managers avanmälnings-API:er som beskrivs i [exemplen på deklarerade ID-avanmälningar](../../features/declared-ids.md#opt-out-examples). Därefter kan all datainsamling avslutas för användare som har avanmälnings-API:er från Mobile SDK – se [Android-enheter](https://docs.adobe.com/content/help/sv-SE/mobile-services/android/gdpr-privacy-android/privacy.html) och [iOS-enheter](https://docs.adobe.com/content/help/sv-SE/mobile-services/ios/privacy-gdpr-ios/privacy.html). Mer information om avanmälan finns i [dokumentationen om förfrågningar om datasekretess](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Hantera samtycke för andrapartspartners

Andrapartspartners är i allmänhet också personuppgiftsansvariga och äger processen för att inhämta samtycke från registrerade för att dela data med andrapartsdatapartners. Som Audience Manager-kund ansvarar du för att avgöra om den andra parten har fått det samtycke som krävs för användningsområdet. Mer information om hur du inhämtar samtycke finns ovan.

## Hantera samtycke för Audience Marketplace tredjepartspartners

Audience Marketplace-tredjepartspartners är också personuppgiftsansvariga och äger sina processer för att inhämta samtycke och hantera förfrågningar om åtkomst/borttagning/korrigering. Adobe uppmanar Audience Marketplace-tredjepartspartners att uppdatera sina uppgifter i företagsprofilen i [Adobe Audience Finder](https://www.adobe-audience-finder.com/) med information om insamling av användardata. Informationen hämtas från Audience Marketplace tredjepartspartners och uppdateras regelbundet. Det är dock upp till varje Audience Manager-kund att fastställa om Audience Marketplace-tredjepartspartnern har fått det samtycke som krävs för användningsområdet. Adobe gör inga utfästelser om omfattningen eller giltigheten av det samtycke som erhållits eller rapporterats av en tredjepartspartner på Audience Marketplace för ett visst användningsområde.
