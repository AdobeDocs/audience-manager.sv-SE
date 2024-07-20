---
description: I den här artikeln beskrivs hur du konfigurerar Amazon Advertising för både nya och befintliga integreringar.
solution: Audience Manager
title: Konfigurera Amazon Advertising som självbetjäningsbaserat mål
exl-id: 049af52a-b425-493d-9e77-9ced7ba6d168
source-git-commit: bac3167927af0957e7081e1ea653464101affcb8
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# Konfigurera [!DNL Amazon Advertising] som ett självbetjäningsenhetsbaserat mål {#configure-amazon}

I den här artikeln beskrivs hur du konfigurerar en integrering med [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us).

## Förutsättningar {#prerequisites}

Innan du konfigurerar ditt [!DNL Amazon Advertising]-mål måste du kontrollera att du uppfyller följande krav.

* Ditt [!DNL Amazon]-konto måste kunna annonseras.
* När du skapar det första [!DNL Amazon Advertising]-målet i din Audience Manager-instans kontaktar du Adobe Consulting eller kundtjänst för att aktivera synkroniseringen av [!DNL Amazon] ID (Data Source ID = 139200) för ditt konto. Detta krävs för korrekt synkronisering mellan Audience Manager och [!DNL Amazon].
* När de nya målgrupperna för dataleverantörer har skapats bör du [uppdatera deras metadata](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) och lägga till **[!DNL audience fees]**. För den här åtgärden kan du använda [Amazon Ads API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) eller [Amazon Advertising-gränssnittet](https://advertising.amazon.com/).

## Lägg till ett nytt [!DNL Amazon Advertising]-mål {#add-new-amazon-destination}

I det här avsnittet beskrivs de steg du måste följa när du konfigurerar ett nytt enhetsbaserat mål för [!DNL Amazon Advertising]. I det här scenariot antas att du inte har något befintligt [!DNL Amazon Advertising]-mål konfigurerat via din Adobe-konsult eller kundtjänst.

### Steg 1. Autentisera med [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

Innan du kan lägga till det enhetsbaserade målet måste du länka Audience Manager och ditt [!DNL Amazon Advertising]-konto. Så här gör du:

1. Logga in på ditt Audience Manager-konto och gå till **[!UICONTROL Administration > Integrated Accounts]**. Om du har en tidigare konfigurerad integrering med en målplattform bör du se den på den här sidan. I annat fall är sidan tom.
1. Välj **[!UICONTROL Add Account]**.
1. Välj [!UICONTROL Amazon Data Provider].

   ![integrerade plattformar](assets/dbd-amazon-without-options.png)

1. Välj ett av **[!UICONTROL Amazon Data Provider]**-alternativen beroende på den region där ditt [!DNL Amazon Ads]-konto har skapats (Nordamerika, Europa eller Ostasien) och klicka på **[!DNL Confirm]** för att omdirigeras till autentiseringssidan.

   ![integrerade plattformar](assets/dbd-amazon-with-options.png)

1. När du har autentiserat dig omdirigeras du till Audience Manager där du ska se dina associerade annonskonton. Välj det annonserarkonto som du vill använda och klicka på **[!UICONTROL Confirm]**. Genom att göra detta har du gett Audience Manager behörighet att skicka uppdateringar till era målgrupper.

### Steg 2. Skapa ett nytt enhetsbaserat mål {#step2-create-new-destination}

När du har länkat Audience Manager och ditt [!DNL Amazon Advertising]-konto kan du skapa det nya målet. Så här gör du:

>[!NOTE]
>
>Du kan inte ändra namnet på ett befintligt enhetsbaserat mål. Ange ett namn som hjälper dig att identifiera målet korrekt.

1. Logga in på ditt Audience Manager-konto, gå till **[!UICONTROL Audience Data > Destinations]** och välj **[!UICONTROL Create Destination]**.
1. I avsnittet **[!UICONTROL Basic Information]** anger du **[!UICONTROL Name]** och **[!UICONTROL Description]** för det nya målet och använder inställningarna nedan:

   ![konfiguration](assets/dbd-new-account-amazon.png)

1. Välj **[!UICONTROL Next]**.
1. Välj de [dataexportetiketter](/help/using/features/data-export-controls.md#controls-labels) som du vill ange för det här målet.
1. Välj **[!UICONTROL Save]**.
1. I avsnittet **[!UICONTROL Segment Mappings]** väljer du de målgruppssegment som du vill skicka till det här målet.
1. Spara målet.

## Överväganden om matchningsfrekvenser {#match-rates-considerations}

Integrationen mellan Audience Manager och [!DNL Amazon Advertising] har stöd för historiska målgruppsåsidosättningar. Alla segmentkvalifikationer skickas till [!DNL Amazon] när du skapar målet.

## Felsökning {#troubleshooting}

När du konfigurerar eller skickar data till målet [!DNL Amazon Advertising] kan du råka ut för de fel som beskrivs nedan. I det här avsnittet förklaras vad som kan orsaka felen och hur du åtgärdar dem.

| Felmeddelande | Förekomst/orsak | Upplösning |
|---|---|---|
| `Internal server error` | Det här felmeddelandet visas i användargränssnittet i Audience Manager när du försöker lägga till ett nytt [!DNL Amazon]-konto med en inaktuell version av Amazon API. | Kontakta Adobe kundtjänst. |
| `Amazon Error: Account XXXXXXXXX was not found` | Det här felmeddelandet visas i användargränssnittet i Audience Manager när de autentiseringsuppgifter som konfigurerats för målet inte har behörighet att komma åt motsvarande Amazon Ads-konto. | <ul><li>Kontrollera att kontoautentiseringsuppgifterna som du använder uppfyller [kraven](#prerequisites).</li><li>Navigera till användargränssnittet för Amazon Ads med samma inloggningsuppgifter och kontrollera om rätt målgrupper visas under motsvarande konto. </li></ul> |
