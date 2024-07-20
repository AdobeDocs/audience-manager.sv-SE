---
description: I den här artikeln beskrivs hur du konfigurerar nya enhetsbaserade mål från användargränssnittet i Audience Manager.
seo-description: This article explains how to configure new device-based destinations from the Audience Manager user interface.
seo-title: Add New Device-Based Destinations
solution: Audience Manager
title: Lägg till nya enhetsbaserade mål
feature: Destination Basics
exl-id: c5d7de2e-085d-48b9-a596-381503c79f55
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# Lägg till nya enhetsbaserade mål {#add-new-device-based-destinations}

I den här artikeln beskrivs hur du konfigurerar nya enhetsbaserade mål från användargränssnittet i Audience Manager.

>[!IMPORTANT]
>
>För närvarande är de flesta enhetsbaserade mål inte berättigade till arbetsflödet för konfiguration av självbetjäning. Om det enhetsbaserade mål som du behöver lägga till inte visas i destinationslistan kontaktar du din Adobe-konsult eller kundsupport för att få hjälp.

## Översikt {#overview}

Processen att lägga till ett nytt enhetsbaserat mål består av två huvudsteg. Först måste du konfigurera integreringen mellan Audience Manager och målpartnern. När du gjort det kan du skapa ett nytt enhetsbaserat mål.

## Förutsättningar {#prerequisites}

När du skapar det första enhetsbaserade målet med en integrerad plattform kontaktar du Adobe Consulting eller kundtjänst för att aktivera ID-synkronisering mellan Audience Manager och den integrerade plattformen för ditt konto. Detta krävs för korrekt synkronisering mellan Audience Manager och målplattformen.

## Steg 1. Autentisera med en målplattform {#step1}

Innan du kan skapa ett nytt enhetsbaserat mål måste du konfigurera integreringen mellan Audience Manager och målplattformen. Så här gör du:

1. Logga in på ditt Audience Manager-konto och gå till **[!DNL Administration > Integrated Accounts]**. Om du har en tidigare konfigurerad integrering med en målplattform bör du se den på den här sidan. I annat fall är sidan tom.
1. Klicka på **[!DNL Add Account]**.
1. Välj målplattformen som du vill autentisera med och klicka på **[!DNL Confirm]** för att omdirigeras till autentiseringssidan för den valda plattformen.

   ![integrerade plattformar](assets/dbd-integrated-platforms.png)

1. När du har autentiserat dig för destinationsplattformskontot omdirigeras du till Audience Manager där du ska se dina associerade annonskonton. Välj det annonserarkonto som du vill använda och klicka på **[!DNL Confirm]**.

## Steg 2. Skapa ett nytt enhetsbaserat mål {#step2}

När du har konfigurerat integreringen av målplattformen kan du skapa det nya målet. Så här gör du:

>[!NOTE]
>
>Du kan inte ändra namnet på ett befintligt enhetsbaserat mål. Ange ett namn som hjälper dig att identifiera målet korrekt.

1. Logga in på ditt Audience Manager-konto, gå till **[!DNL Audience Data > Destinations]** och klicka på **[!DNL Create Destination]**.
1. I avsnittet **[!DNL Basic Information]** anger du **[!DNL Name]** och **[!DNL Description]** för ditt nya mål och använder inställningarna i listan nedan:

   ![konfiguration](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: välj målplattformen som du vill skicka målgruppssegment till.
   * **[!DNL Account]**: välj önskat annonserarkonto som är associerat med den valda plattformen.
1. Klicka på **[!DNL Next]**.
1. Välj de [dataexportetiketter](/help/using/features/data-export-controls.md#controls-labels) som du vill ange för det här målet.
1. Klicka på **[!DNL Save]**.
1. I avsnittet **[!DNL Segment Mappings]** väljer du de målgruppssegment som du vill skicka till det här målet.
1. Spara målet.
