---
description: I den här artikeln beskrivs hur du konfigurerar Twitter-anpassade målgrupper för både nya och befintliga integreringar.
seo-description: I den här artikeln beskrivs hur du konfigurerar Twitter-anpassade målgrupper för både nya och befintliga integreringar.
seo-title: Konfigurera Twitter-anpassade målgrupper som enhetsbaserade destinationer med självbetjäning
solution: Audience Manager
title: Konfigurera Twitter-anpassade målgrupper som enhetsbaserade destinationer med självbetjäning
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 8ff76decc1cbd7f7babd619dd1ce9fe047541337
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 4%

---


# Konfigurera [!DNL Twitter Tailored Audiences] som självbetjäningsbaserat enhetsbaserat mål {#configure-twitter}

I den här artikeln beskrivs hur du konfigurerar en integrering med [Twitter-anpassade målgrupper](https://business.twitter.com/en/targeting/tailored-audiences.html).

## Förutsättningar {#prerequisites}

Innan du konfigurerar ditt [!DNL Twitter Tailored Audiences] mål bör du kontrollera följande Twitter-krav som du måste uppfylla.

1. Ditt [!DNL Twitter Ads] konto måste kunna annonseras. Nya [!DNL Twitter Ads] konton är inte berättigade till reklam under de första två veckorna efter att de har skapats.
2. Ditt [!DNL Twitter] användarkonto som du har auktoriserat åtkomst för i Audience Manager måste ha [behörigheten för partnermålgruppshanteraren](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiverad.
3. När du skapar det första [!DNL Twitter Tailored Audiences] målet i din Audience Manager-instans kontaktar du Adobe Consulting eller kundtjänst för att aktivera synkroniseringen av [!DNL Twitter] ID (datakälla-ID = 1123) för ditt konto. Detta krävs för korrekt synkronisering mellan Audience Manager och [!DNL Twitter].

## Lägg till ett nytt [!DNL Twitter Tailored Audiences] mål {#add-new-twitter-destination}

I det här avsnittet beskrivs de steg du måste följa när du konfigurerar ett nytt enhetsbaserat mål för [!DNL Twitter Tailored Audiences]. I det här scenariot förutsätts att du inte har någon befintlig [!DNL Twitter Tailored Audiences] destination konfigurerad via din Adobe-konsult eller kundtjänst.

### Steg 1. Autentisera med [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Innan du kan lägga till det enhetsbaserade målet måste du länka Audience Manager och ditt [!DNL Twitter Tailored Audiences] konto. Så här gör du:

1. Logga in på ditt Audience Manager-konto och gå till **[!DNL Administration > Integrated Accounts]**. Om du har en tidigare konfigurerad integrering med en målplattform bör du se den på den här sidan. I annat fall är sidan tom.
1. Klicka på **[!DNL Add Account]**.
1. Markera [!DNL Twitter Tailored Audiences] och klicka för **[!DNL Confirm]** att omdirigeras till autentiseringssidan.                     ![integrerade plattformar](assets/dbd-integrated-platforms.png)
1. När du har autentiserat dig omdirigeras du till Audience Manager där du ska se dina associerade annonskonton. Välj det annonserarkonto som du vill använda och klicka på **[!DNL Confirm]**.

### Steg 2. Skapa ett nytt enhetsbaserat mål {#step2-create-new-destination}

När du har länkat Audience Manager och ditt [!DNL Twitter Tailored Audiences]mål kan du skapa det nya målet. Så här gör du:

>[!NOTE]
>
>Du kan inte ändra namnet på ett befintligt enhetsbaserat mål. Ange ett namn som hjälper dig att identifiera målet korrekt.

1. Logga in på ditt Audience Manager-konto, gå till **[!DNL Audience Data > Destinations]** och klicka på **[!DNL Create Destination]**.
1. I **[!DNL Basic Information]** avsnittet anger du ett **[!DNL Name]** och **[!DNL Description]** ett nytt mål och använder inställningarna nedan: ![konfiguration](assets/dbd-new-basic.png)
1. Klicka på **[!DNL Next]**.
1. Välj de [dataexportetiketter](/help/using/features/data-export-controls.md#controls-labels) som du vill ange för det här målet.
1. Klicka på **[!DNL Save]**.
1. I **[!DNL Segment Mappings]** avsnittet markerar du de målgruppssegment som du vill skicka till det här målet.
1. Spara målet.

## Överväganden vid segmentmappning {#segment-mapping-considerations}

När du mappar målgruppssegment till [!UICONTROL Twitter]måste du se till att följande krav för namngivning av segment uppfylls:

* Ge segmentmappningsnamn som kan läsas av människor. Vi rekommenderar att du använder samma namn som du använde för Audience Manager-segmenten.
* Använd inte specialtecken (`,``%` `:``;``@` `/``=` `?` `$`) i namn på segment- och segmentmappningar. Om Audience Manager-segmentnamnet innehåller dessa tecken tar du bort dem innan du mappar segmentet till ett [!UICONTROL Twitter] mål.

### Exempel

* Korrigera segmentets eller mappningens namn: &quot;US and European Shoppers&quot;
* Felaktigt segment eller mappningsnamn: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Du kan inte ändra namnen på redan mappade segment. Audience Manager använder segmentnamnen för att identifiera segmenten i integreringen korrekt.

## Överväganden om matchningsfrekvenser {#match-rates-considerations}

* Integrationen mellan Audience Manager och [!UICONTROL Twitter Tailored Audiences] stöder historiska efterfyllningar av målgrupper. Alla segmentkvalifikationer skickas till [!UICONTROL Twitter] när du skapar målet.
