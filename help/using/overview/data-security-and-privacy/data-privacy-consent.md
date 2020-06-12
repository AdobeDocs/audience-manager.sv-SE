---
description: Det här dokumentet förklarar hur samtyckeshantering fungerar i Audience Manager.
seo-description: Det här dokumentet förklarar hur samtyckeshantering fungerar i Audience Manager.
seo-title: Hantering av samtycke
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Hantering av samtycke
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 34af220db2cf23ccde225eb1e05af7ce0e1513b7
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---


# Hantering av samtycke

## Översikt {#overview}

I de fall där samtycke krävs för vissa marknadsföringsaktiviteter måste Audience Manager-kunderna bestämma omfattningen och huruvida vissa samtycke måste uppdateras för att kunna fortsätta använda data som fortsätter framåt.

Audience Manager har verktyg som hjälper er att få ut det innehåll ni behöver från era användare, så att ni kan leverera personaliserade upplevelser till dem i alla kanaler.

>[!IMPORTANT]
>
> Innehållet i detta dokument är inte juridisk rådgivning och är inte avsett att ersätta juridisk rådgivning.
>
> Som personuppgiftsbiträde kan Adobe inte ge juridisk rådgivning när det gäller att få samtycke. Du kanske också vill överväga att samarbeta med en leverantör av lösningar för samtyckeshantering, som [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) eller [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), och rådfråga företagets juridiska avdelning om råd angående samtycke och rutiner när du konfigurerar din avanmälningsimplementering.

## Experience Cloud-anmälningstjänst

Med [Experience Clouds anmälningstjänst](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) kan ni konfigurera protokoll för besökaren för att hjälpa er att avgöra om ni kan ställa in en cookie på personens enhet eller webbläsare när ni besöker er webbplats.

Detta är ett tillägg till [!DNL Experience Cloud ID (ECID) Service], som är utformat för att du ska kunna kontrollera om och vilka Experience Cloud-lösningar som kan placera cookies på webbsidor för besökare innan användaren ger sitt samtycke.

Med [Experience Clouds anmälningstjänst](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) kan ni också ange protokoll som ska integreras med er plattform för hantering av samtycke (CMP) och befintliga system som en del av er större design.

## Hantera anmälan/inhämtning av samtycke

Audience Manager-kunder kan lagra användares samtycke för olika användningsområden, som annonsering eller personalisering som egenskaper i Audience Manager. Segment som du bygger med dessa egenskaper kommer då endast att omfatta användare som ger respektive samtycke för varje användning. Observera att datainsamlingen inte avbryts om du använder den här metoden, men att dataanvändningen endast påverkas när du skickar segment för aktivering. När användare återkallar sitt samtycke kan du ta bort dessa egenskaper från användarprofilen med hjälp av Audience Managers [ingående gruppprocess](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) eller Audience Manager-avanmälningsprocess enligt nedan.

## Hantera avanmälan/återtagande av samtycke

Du kan hantera avanmälan för Adobe Experience Cloud via sidan [Dina sekretessval](https://www.adobe.com/privacy/opt-out.html#customeruse) . Med enklicksfunktioner kan slutanvändarna styra och avanmäla datainsamling via annonslösningarna i Adobe Experience Cloud (inklusive Audience Manager). Mer information finns i avsnittet om [företagskunder](https://www.adobe.com/privacy/opt-out.html#customeruse) på sidan Sekretessalternativ. Information om webbläsare som inte stöder cookies från tredje part finns i [Deklarerad ID-målning](../../features/declared-ids.md#declared-id-targeting). För mobila enheter kan du hämta relevanta Audience Manager-identifierare och anropa Audience Managers avanmälnings-API:er enligt exemplen [med](../../features/declared-ids.md#opt-out-examples)deklarerade ID-avhopp. Därefter kan du upphöra med all datainsamling för de användare som har avanmälnings-API:er från Mobile SDK - se [Android-enheter](https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html) och [iOS-enheter](https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html). Mer information om avanmälan finns i dokumentationen för [datasekretessförfrågningar](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Hantera samtycke för andra partspartners

Andra parts partner är i allmänhet också datakontrollanter och äger processen för att få det samtycke som den registrerade behöver för att dela data med andra parts datapartners. Som Audience Manager-kund ansvarar du för att avgöra om den andra parten har fått det samtycke som krävs för ditt användningsfall. Mer information om hur du får tillstånd finns ovan.

## Hantera samtycke för målgruppsmarknadsplatsens tredjepartspartners

Audience Marketplace-partners från tredje part är också datakontroller och äger sin process för att inhämta samtycke och hantera begäranden om åtkomst/borttagning/korrigering. Adobe begär aktivt att tredjepartspartners på Audience Marketplace uppdaterar sin företagsprofilinformation i [Adobe Audience Finder](https://www.adobe-audience-finder.com/) med ytterligare information om insamling av användardata. Informationen hämtas från Audience Marketplace Third Party Partners och uppdateras regelbundet. Det är dock upp till varje Audience Manager-kund att fastställa att Audience Marketplace-partnern har fått det samtycke som krävs för kundens användningsfall. Adobe gör inga utfästelser om omfattningen eller giltigheten av det samtycke som erhållits eller rapporterats av en tredjepartspartner på Audience Marketplace för ett visst användningsfall.
