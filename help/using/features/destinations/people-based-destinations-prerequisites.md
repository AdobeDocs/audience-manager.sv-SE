---
description: 'Nedan finns en översikt över de kundkrav du måste uppfylla innan du registrerar dig för personbaserade destinationer.  '
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Förutsättningar och överväganden
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# Förutsättningar och överväganden {#prerequisites-considerations}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

Läs nedan för att få en översikt över kundkrav som du måste uppfylla innan du registrerar dig för [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Läs igenom den här artikeln noggrant innan du går vidare till implementeringsfasen.

## Registrera dig för [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] är en premiumfunktion som förbättrar er Audience Manager-upplevelse genom att ni kan aktivera era egna målgruppssegment i personbaserade miljöer genom att inrikta er på målgruppen med anpassade erbjudanden i sociala nätverk eller via e-postmarknadsföring.

Kontakta din Adobe-representant för att få tillgång till denna premiumfunktion.

## Partnerspecifika krav {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Innan du kan använda [!UICONTROL People-Based Destinations] för att skicka förstahandspubliken [!UICONTROL segments] till [!DNL Facebook]måste du uppfylla följande krav:

1. Dina [!DNL Facebook] användarkontot måste ha **Hantera kampanjer** behörighet aktiverad för annonskontot som du tänker använda.
2. Lägg till **Adobe Experience Cloud** företagskonto som annonspartner i [!DNL Facebook Ad Account]. Använd `business ID=206617933627973`. Se [Lägg till partners i din Business Manager](https://www.facebook.com/business/help/1717412048538897) för mer information.
   >[!IMPORTANT]
   > När du konfigurerar behörigheter för Adobe Experience Cloud måste du aktivera **Hantera kampanjer** behörighet. Det krävs för [!UICONTROL People-Based Destinations]-integreringen.
3. Läs och signera [!DNL Facebook Custom Audiences] Användarvillkor. Gör det genom att gå till `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, där `accountID` är din [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Innan du kan använda [!UICONTROL People-Based Destinations] för att skicka era egna målgruppssegment till [!DNL LinkedIn]bör du se till att [!DNL LinkedIn Campaign Manager] kontot har [!DNL Creative Manager] eller högre behörighetsnivå.

Så här redigerar du [!DNL LinkedIn Campaign Manager] användarbehörigheter, se [Lägg till, redigera och ta bort användarbehörigheter på annonskonton](https://www.linkedin.com/help/lms/answer/5753) i LinkedIn-dokumentationen.

Se [Förstå och konfigurera LinkedIn personbaserade mål](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) för videoinstruktioner.

### [!DNL Google Customer Match] {#gcm}

Innan du kan använda [!UICONTROL People-Based Destinations] för att skicka era egna målgruppssegment till en [!DNL Google Customer Match] ska du kontrollera att du läser och följer Google policy för användning av [!DNL Customer Match], konturerad i [Google supportdokumentation](https://support.google.com/google-ads/answer/6299717).

Kontrollera sedan att [!DNL Google] kontot har konfigurerats för [!DNL Standard] eller högre behörighetsnivå. Se [Google Ads-dokumentation](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) för mer information.

Kunder med kompatibla konton tillåts automatiskt listade av Google.

## Dataregistrering {#data-onboarding}

Intag av data för [!UICONTROL People-Based Destinations] stöder för närvarande upp till 10 hash-kodade e-postadresser som är länkade till ett kund-ID ([!DNL CRM ID]), per batchöverföring. Om du överför mer än 10 hash-kodade e-postadresser som är länkade till ett kund-ID importeras 10 av Audience Manager, utan någon särskild ordning.

Om du överför mer än 10 hash-kodade e-postadresser som är länkade till ett kund-ID vid flera batchöverföringar kommer Audience Manager att behålla de 10 senaste e-postadresserna som lagts till.

## Datasekretess {#data-privacy}

Fast [!UICONTROL People-Based Destinations] om du vill att målgrupper ska kunna målgruppsanpassas baserat på hash-kodade e-postadresser som du har överfört är det förbjudet att överföra direkt identifierbar besöksinformation till Audience Manager. Under introduktionsfasen av data måste du se till att de e-postadresser du tänker använda hashas med [!DNL SHA256] algoritm. Annars kan du inte använda dem i [!UICONTROL People-Based Destinations].

## Dataskärm jämfört med kryptering {#data-hashing-encryption}

Kryptering är en tvåvägsfunktion. All krypterad information kan också dekrypteras med rätt dekrypteringsnyckel. Kryptering av data i samband med Audience Manager utgör allvarliga risker, eftersom alla krypterade former av personligt identifierbar information också kan dekrypteras. I motsats till kryptering [!UICONTROL People-Based Destinations] är utformade för att fungera med hash-kodade data i stället.

Hash-funktionen är en envägsfunktion som förvränger indata och ger ett unikt resultat. Genom att använda rätt hash-algoritmer, som [!DNL SHA256]går det inte att vända på hashfunktionen och visa den information som inte är så rörig. E-postadresserna som du kommer att anlita Audience Manager måste hash-kodas med [!DNL SHA256] algoritm. På så sätt kan du se till att inga ohanterade e-postadresser når Audience Manager.

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

Adobe Experience Cloud ger dig möjlighet att hash-koda kund-ID:n via [!DNL Adobe Experience Platform Identity Service (ECID)]. Se [SHA256 Hash-stöd för setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) för detaljerad information om hur du använder ECID för att hash-koda kund-ID:n.

## Hämtar användarbehörighet {#obtaining-user-permission}

Sedan [!UICONTROL People-Based Destinations] hjälper er att aktivera egna målgruppsdata i personbaserade kanaler, är det ert ansvar att informera och få alla nödvändiga samtycke från era kunder om hur ni kommer att använda deras data för annonsering eller andra ändamål.

Innan du registrerar dig för [!UICONTROL People-Based Destinations]måste du se till att få kundernas samtycke innan du använder deras information i annonssyfte.

Om kunderna vill avanmäla sig från annonskampanjer finns mer information i [Hantering av avanmälan](../../overview/data-security-and-privacy/data-privacy-requests.md) för mer ingående information om hur du kan hindra Audience Manager från att samla in data ytterligare.

## Tvingande aktivering av förstahandsdata {#enforcing-first-party-activation}

När du använder [!UICONTROL People-Based Destinations]kan ni bara använda egna data för att aktivera målgruppssegment i personbaserade kanaler. Ni kan inte använda data från andra leverantörer för målgruppsaktivering i personbaserade kanaler.

När du använder [!UICONTROL People-Based Destinations], använda [Dataexportkontroller](../data-export-controls.md) för att märka [!UICONTROL data sources] och [!UICONTROL destinations] i enlighet med riktlinjer och krav från destinationsplattformar och dataleverantörer.

## Införliva autentiserade hash-ID:n via deklarerade ID-mål {#onboard-authenticated-declared-id}

Det finns två sätt att överföra offlinedata till Audience Manager för [!UICONTROL People-Based Destinations].

* [Skicka batchdata](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) till Audience Manager för att importera hashade e-postadresser. Med den här metoden kan du välja att använda de hash-kodade e-postadresserna från [!DNL CRM] databas i [!UICONTROL People-Based Destinations]. När du använder den här metoden kan du dessutom kvalificera de streckade e-postadresserna för [onboardtraits](../traits/trait-and-segment-qualification-reference.md).
* Använd [Deklarerade ID:n](../declared-ids.md) för att deklarera hash-kodade e-postadresser när autentiserade kund-ID skickas. När du använder den här metoden skickar Audience Manager bara till [!UICONTROL People-Based Destinations] e-postadresser som hashas av användare som har autentiserats online. E-postadresserna som aktiveras via personbaserade kanaler är bara de som anges i de deklarerade ID-händelseanropen. Andra e-postadresser som är kopplade till kund-ID:t skickas inte i realtid.
