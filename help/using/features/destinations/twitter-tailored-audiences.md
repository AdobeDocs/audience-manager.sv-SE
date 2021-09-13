---
description: I den här artikeln beskrivs hur du konfigurerar anpassade Twitter-målgrupper för både nya och befintliga integreringar.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Konfigurera anpassade Twitter-målgrupper som självbetjäningsmål
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 8023bfe1e4ea415867e1233f143627ff179cce42
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Konfigurera [!DNL Twitter Custom Audiences] som ett självbetjäningsenhetsbaserat mål {#configure-twitter}

I den här artikeln beskrivs hur du konfigurerar en integrering med [Twitter Custom Audiences](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Förutsättningar {#prerequisites}

Innan du konfigurerar ditt [!DNL Twitter Custom Audiences]-mål bör du kontrollera att du uppfyller följande krav för Twitter.

1. Ditt [!DNL Twitter Ads]-konto måste kunna annonseras. Nya [!DNL Twitter Ads]-konton är inte berättigade till reklam under de första två veckorna efter att de har skapats.
2. [!DNL Twitter]-användarkontot som du har auktoriserat åtkomst för i Audience Manager måste ha [behörigheten för partnermålgruppshanteraren](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiverad.
3. När du skapar det första [!DNL Twitter Custom Audiences]-målet i din Audience Manager-instans kontaktar du Adobe Consulting eller kundtjänst för att aktivera synkroniseringen av [!DNL Twitter] ID (datakälla-ID = 1123) för ditt konto. Detta krävs för korrekt synkronisering mellan Audience Manager och [!DNL Twitter].

## Lägg till ett nytt [!DNL Twitter Custom Audiences]-mål {#add-new-twitter-destination}

I det här avsnittet beskrivs de steg du måste följa när du konfigurerar ett nytt enhetsbaserat mål för [!DNL Twitter Custom Audiences]. I det här scenariot antas att du inte har något befintligt [!DNL Twitter Custom Audiences]-mål konfigurerat via din Adobe-konsult eller kundtjänst.

### Steg 1. Autentisera med [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Innan du kan lägga till det enhetsbaserade målet måste du länka Audience Manager och ditt [!DNL Twitter Custom Audiences]-konto. Så här gör du:

1. Logga in på ditt Audience Manager-konto och gå till **[!DNL Administration > Integrated Accounts]**. Om du har en tidigare konfigurerad integrering med en målplattform bör du se den på den här sidan. I annat fall är sidan tom.
1. Klicka på **[!DNL Add Account]**.
1. Välj [!DNL Twitter Custom Audiences] och klicka på **[!DNL Confirm]** för att omdirigeras till autentiseringssidan.

   ![integrerade plattformar](assets/dbd-integrated-platforms.png)

1. När du har autentiserat dig omdirigeras du till Audience Manager där du ska se dina associerade annonskonton. Välj det annonserarkonto som du vill använda och klicka på **[!DNL Confirm]**.

### Steg 2. Skapa ett nytt enhetsbaserat mål {#step2-create-new-destination}

När du har länkat Audience Manager och din [!DNL Twitter Custom Audiences] kan du skapa det nya målet. Så här gör du:

>[!NOTE]
>
>Du kan inte ändra namnet på ett befintligt enhetsbaserat mål. Ange ett namn som hjälper dig att identifiera målet korrekt.

1. Logga in på ditt Audience Manager-konto, gå till **[!DNL Audience Data > Destinations]** och klicka på **[!DNL Create Destination]**.
1. I avsnittet **[!DNL Basic Information]** anger du en **[!DNL Name]** och **[!DNL Description]** för det nya målet och använder inställningarna nedan: ![konfiguration](assets/dbd-new-basic.png)
1. Klicka på **[!DNL Next]**.
1. Välj [Dataexportetiketter](/help/using/features/data-export-controls.md#controls-labels) som du vill ange för det här målet.
1. Klicka på **[!DNL Save]**.
1. I avsnittet **[!DNL Segment Mappings]** väljer du de målgruppssegment som du vill skicka till det här målet.
1. Spara målet.

## Överväganden vid segmentmappning {#segment-mapping-considerations}

När du mappar målgruppssegment till [!UICONTROL Twitter] måste du se till att följande krav för segmentnamngivning uppfylls:

* Ge segmentmappningsnamn som kan läsas av människor. Vi rekommenderar att du använder samma namn som du använde för Audience Manager-segmenten.
* Använd inte specialtecken (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) i namn på segment och segmentmappningar. Om Audience Manager-segmentnamnet innehåller dessa tecken tar du bort dem innan du mappar segmentet till ett [!UICONTROL Twitter]-mål.

### Exempel

* Korrigera segmentets eller mappningens namn: &quot;US and European Shoppers&quot;
* Felaktigt segment eller mappningsnamn: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Du kan inte ändra namnen på redan mappade segment. Audience Manager använder segmentnamnen för att identifiera segmenten i integreringen korrekt.

## Överväganden om matchningsfrekvenser {#match-rates-considerations}

* Integrationen mellan Audience Manager och [!UICONTROL Twitter Custom Audiences] har stöd för historiska målgruppsefterfyllningar. Alla segmentkvalifikationer skickas till [!UICONTROL Twitter] när du skapar målet.
