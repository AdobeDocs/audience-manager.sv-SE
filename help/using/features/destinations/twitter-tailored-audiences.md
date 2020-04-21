---
description: I den här artikeln beskrivs hur du konfigurerar Twitter-anpassade målgrupper för både nya och befintliga integreringar.
seo-description: I den här artikeln beskrivs hur du konfigurerar Twitter-anpassade målgrupper för både nya och befintliga integreringar.
seo-title: Konfigurera Twitter-anpassade målgrupper som självbetjäningsbaserade enhetsbaserade mål
solution: Audience Manager
title: Konfigurera Twitter-anpassade målgrupper som självbetjäningsbaserade enhetsbaserade mål
translation-type: tm+mt
source-git-commit: fb1bec17023b7b70c53659d68e2fbc431d9022fa

---


# Konfigurera [!DNL Twitter Tailored Audiences] som självbetjäningsbaserat enhetsbaserat mål {#configure-twitter}

I den här artikeln beskrivs hur du konfigurerar en integrering med [Twitter-anpassade målgrupper](https://business.twitter.com/en/targeting/tailored-audiences.html).

## Förutsättningar {#prerequisites}

Innan du konfigurerar ditt [!DNL Twitter Tailored Audiences] mål bör du kontrollera följande Twitter-krav som du måste uppfylla.

1. Ditt [!DNL Twitter Ads] konto måste kunna annonseras. Nya [!DNL Twitter Ads] konton är inte berättigade till reklam under de första två veckorna efter att de har skapats.
2. Ditt [!DNL Twitter] användarkonto som du har auktoriserat åtkomst för i Audience Manager måste ha behörigheten [Partner-målgruppshanterare](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiverad.
3. När du skapar den första [!DNL Twitter Tailored Audiences] målplatsen i din Audience Manager-instans kontaktar du Adobe Consulting eller kundtjänst för att aktivera synkroniseringen av [!DNL Twitter] ID (datakälla-ID = 1123) för ditt konto. Detta krävs för korrekt synkronisering mellan Audience Manager och [!DNL Twitter].

## Lägg till ett nytt [!DNL Twitter Tailored Audiences] mål {#add-new-twitter-destination}

I det här avsnittet beskrivs de steg du måste följa när du konfigurerar ett nytt enhetsbaserat mål för [!DNL Twitter Tailored Audiences]. I det här scenariot förutsätts att du inte har någon befintlig [!DNL Twitter Tailored Audiences] destination konfigurerad via din Adobe-konsult eller kundtjänst.

### Steg 1. Autentisera med [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Innan du kan lägga till det enhetsbaserade målet måste du länka till Audience Manager och ditt [!DNL Twitter Tailored Audiences] konto. Så här gör du:

1. Logga in på ditt Audience Manager-konto och gå till **[!DNL Administration > Integrated Accounts]**. Om du har en tidigare konfigurerad integrering med en målplattform bör du se den på den här sidan. I annat fall är sidan tom.
1. Klicka på **[!DNL Add Account]**.
1. Markera [!DNL Twitter Tailored Audiences] och klicka för **[!DNL Confirm]** att omdirigeras till autentiseringssidan.                     ![integrerade plattformar](assets/dbd-integrated-platforms.png)
1. När du har autentiserat dig omdirigeras du till Audience Manager där du bör se dina associerade annonskonton. Välj det annonserarkonto som du vill använda och klicka på **[!DNL Confirm]**.

### Steg 2. Skapa ett nytt enhetsbaserat mål {#step2-create-new-destination}

När du har länkat Audience Manager och din [!DNL Twitter Tailored Audiences]målmapp kan du skapa den nya målplatsen. Så här gör du:

>[!NOTE]
>
>Du kan inte ändra namnet på ett befintligt enhetsbaserat mål. Ange ett namn som hjälper dig att identifiera målet korrekt.

1. Logga in på ditt Audience Manager-konto, gå till **[!DNL Audience Data > Destinations]** och klicka på **[!DNL Create Destination]**.
1. I **[!DNL Basic Information]** avsnittet anger du ett **[!DNL Name]** och **[!DNL Description]** ett nytt mål och använder inställningarna nedan: ![inställningar](assets/dbd-new-basic.png)
1. Klicka på **[!DNL Next]**.
1. Välj de [dataexportetiketter](/help/using/features/data-export-controls.md#controls-labels) som du vill ange för det här målet.
1. Klicka på **[!DNL Save]**.
1. I **[!DNL Segment Mappings]** avsnittet markerar du de målgruppssegment som du vill skicka till det här målet.
1. Spara målet.

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Överväganden vid segmentmappning {#segment-mapping-considerations}

När du mappar målgruppssegment till [!UICONTROL Twitter]måste du se till att följande krav för namngivning av segment uppfylls:

* Ge segmentmappningsnamn som kan läsas av människor. Vi rekommenderar att du använder samma namn som du använde för Audience Manager-segmenten.
* Använd inte specialtecken (`,``%` `:``;``@` `/``=` `?` `$`) i namn på segment- och segmentmappningar. Om namnet på Audience Manager-segmentet innehåller dessa tecken tar du bort dem innan du mappar segmentet till ett [!UICONTROL Twitter] mål.

### Exempel

* Korrigera segmentets eller mappningens namn: &quot;US and European Shoppers&quot;
* Felaktigt segment eller mappningsnamn: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Du kan inte ändra namnen på redan mappade segment. Audience Manager använder segmentnamnen för att identifiera segmenten i integreringen korrekt.

## Överväganden om matchningsfrekvenser {#match-rates-considerations}

* När du använder [!UICONTROL Twitter Tailored Audiences]visas inga värden i målsidans mått [!UICONTROL Segment Addressable Audience] och [!UICONTROL Segment Match Rate] mått. Detta är normalt eftersom målgruppsmatchning och matchningsfrekvenser för detta mål hanteras och hanteras av [!UICONTROL Twitter], inte av Adobe.
* Integrationen mellan Audience Manager och [!UICONTROL Twitter Tailored Audiences] stöd för historiska efterfyllningar av målgrupper. Alla segmentkvalifikationer skickas till [!UICONTROL Twitter] när du skapar målet.
