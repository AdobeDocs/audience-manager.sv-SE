---
description: 'Nedan finns en översikt över de kundkrav du måste uppfylla innan du registrerar dig för personbaserade destinationer.  '
seo-description: 'Nedan finns en översikt över de kundkrav du måste uppfylla innan du registrerar dig för personbaserade destinationer.  '
seo-title: Krav och överväganden för personbaserade destinationer
solution: Audience Manager
title: Förutsättningar och överväganden
translation-type: tm+mt
source-git-commit: 8b72a42f9458fba97d02d2f16228e7d985ca3463
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---


# Förutsättningar och överväganden {#prerequisites-considerations}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

Nedan finns en översikt över de kundkrav du måste uppfylla innan du kan registrera dig [!DNL People-Based Destinations].

>[!IMPORTANT]
> Läs igenom den här artikeln noggrant innan du går vidare till implementeringsfasen.

## Registrera dig för [!UICONTROL People-Based Destinations] {#signing-up}

[!DNL People-Based Destinations] är en premiumfunktion som förbättrar er Audience Manager-upplevelse genom att ni kan aktivera era egna målgruppssegment i personbaserade miljöer genom att inrikta er på målgruppen med anpassade erbjudanden i sociala nätverk eller via e-postmarknadsföring.

Kontakta din Adobe-representant för att få tillgång till denna premiumfunktion.

## Partnerspecifika krav {#partner-prerequisites}

### [!DNL Facebook]

Innan du kan använda [!DNL People-Based Destinations] för att skicka dina egna målgruppssegment till [!DNL Facebook]kontrollerar du att du uppfyller följande krav:

1. Ditt [!DNL Facebook] användarkonto måste ha behörigheten **Hantera kampanjer** aktiverad för annonskontot som du tänker använda.
2. Lägg till **Adobe Experience Cloud** -företagskontot som annonspartner i ert [!DNL Facebook Ad Account]företag. Använd `business ID=206617933627973`. Mer information finns i [Lägg till partners i din Business Manager](https://www.facebook.com/business/help/1717412048538897) .
   >[!IMPORTANT]
   > När du konfigurerar behörigheter för Adobe Experience Cloud måste du aktivera behörigheten **Hantera kampanjer** . Detta krävs för [!DNL People-Based Destinations] integreringen.
3. Läs och signera [!DNL Facebook Custom Audiences] användarvillkoren. För att göra detta, gå till `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, var `accountID` är din [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn]

Innan du kan använda [!DNL People-Based Destinations] för att skicka dina egna målgruppssegment till [!DNL LinkedIn], måste du se till att ditt [!DNL LinkedIn Campaign Manager] konto har den [!DNL Creative Manager] eller högre behörighetsnivån.

Mer information om hur du redigerar [!DNL LinkedIn Campaign Manager] användarbehörigheter finns i [Lägga till, redigera och ta bort användarbehörigheter på annonskonton](https://www.linkedin.com/help/lms/answer/5753)

## Datainhämtning {#data-onboarding}

Inmatning av data för [!DNL People-Based Destinations] närvarande stöder upp till 10 hash-kodade e-postadresser länkade till ett kund-ID ([!DNL CRM ID]) per batchöverföring. Om du överför mer än 10 hash-kodade e-postadresser som är länkade till ett kund-ID importeras 10 av Audience Manager, utan någon särskild ordning.

Om du överför mer än 10 hash-kodade e-postadresser som är länkade till ett kund-ID vid flera batchöverföringar kommer Audience Manager att behålla de 10 senaste e-postadresserna som lagts till.

## Dataintegritet {#data-privacy}

Även om du [!DNL People-Based Destinations] kan rikta in dig på målgrupper baserat på hash-kodade e-postadresser som du har överfört, är du inte längre berättigad att överföra direkt identifierbar besöksinformation till Audience Manager. I datainloggningsfasen måste du se till att de e-postadresser som du tänker använda hashas med [!DNL SHA256] -algoritmen. Annars kan du inte använda dem i [!DNL People-Based Destinations].

## Dataskärm jämfört med kryptering {#data-hashing-encryption}

Kryptering är en tvåvägsfunktion. All krypterad information kan också dekrypteras med rätt dekrypteringsnyckel. Kryptering av data i samband med Audience Manager utgör allvarliga risker, eftersom alla krypterade former av personligt identifierbar information också kan dekrypteras. I motsats till kryptering [!DNL People-Based Destinations] är de utformade för att fungera med hash-kodade data i stället.

Hash-funktionen är en envägsfunktion som förvränger indata och ger ett unikt resultat. Genom att använda rätt hash-algoritmer, som [!DNL SHA256]att det inte finns något sätt att vända på hashfunktionen och visa den okramade informationen. E-postadresserna som du kommer att anlita Audience Manager måste hash-kodas med [!DNL SHA256] -algoritmen. På så sätt kan du se till att inga ohanterade e-postadresser når Audience Manager.

## Hash-krav {#hashing-requirements}

När du hash-kodar e-postadresserna måste du se till att följande krav uppfylls:

* Trimma alla inledande och avslutande blanksteg från e-poststrängen. exempel: `johndoe@example.com`, inte `<space>johndoe@example.com<space>`;
* När du hash-kodar e-poststrängarna ska du se till att hash-koda den gemena strängen.
   * Exempel: `example@email.com`, inte `EXAMPLE@EMAIL.COM`;
* Kontrollera att den hash-kodade strängen är i gemener
   * Exempel: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, inte `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Salt inte strängen.

Se videon nedan för att förstå hashkraven för [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Med Adobe Experience Cloud får ni möjlighet att hash-koda kund-ID:n via Adobe Experience Platform Identity Service. Se [SHA256 Hashing Support för setCustomerID](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) för mer information om hur man använder ECID för att hash-koda kund-ID:n.

## Hämtar användarbehörighet {#obtaining-user-permission}

Eftersom [!DNL People-Based Destinations] ni kan aktivera egna målgruppsdata i personbaserade kanaler är det ert ansvar att informera och få alla nödvändiga samtycke från era kunder om hur ni kommer att använda deras data för annonsering eller andra ändamål.

Innan du registrerar dig måste du se till [!DNL People-Based Destinations]att få kundernas samtycke innan du använder deras information i annonssyfte.

Om dina kunder vill avanmäla sig från annonskampanjer finns mer information om hur du kan stoppa Audience Manager från att samla in data i [avanmälningshanteringen](../../overview/data-security-and-privacy/data-privacy-requests.md) .

## Tvingande aktivering av förstahandsdata {#enforcing-first-party-activation}

När du använder [!DNL People-Based Destinations]kan du bara använda egna data för att aktivera målgruppssegment i personbaserade kanaler. Ni kan inte använda data från andra leverantörer för målgruppsaktivering i personbaserade kanaler.

När du använder [!UICONTROL People-Based Destinations]kan du använda [Dataexportkontroller](../data-export-controls.md) för att etikettera datakällor och mål enligt riktlinjer och krav från målplattformar och dataleverantörer.

## Införliva autentiserade hash-ID:n via deklarerade ID-mål {#onboard-authenticated-declared-id}

Det finns två sätt att överföra offlinedata till Audience Manager för [!DNL People-Based Destinations].

* [Skicka batchdata](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) till Audience Manager för att importera hashade e-postadresser. Med den här metoden kan du välja att använda hash-kodade e-postadresser från din [!DNL CRM] databas i [!DNL People-Based Destinations]. När du använder den här metoden kan du dessutom kvalificera hash-kodade e-postadresser för [anpassade egenskaper](../traits/trait-and-segment-qualification-reference.md).
* Använd [deklarerade ID:n](../declared-ids.md) för att deklarera hashade e-postadresser när autentiserade kund-ID skickas. När du använder den här metoden skickar Audience Manager endast till [!DNL People-Based Destinations] de streckade e-postadresserna från användare som har autentiserat online. E-postadresserna som aktiveras via personbaserade kanaler är bara de som anges i de deklarerade ID-händelseanropen. Andra e-postadresser som är kopplade till kund-ID:t skickas inte i realtid.
