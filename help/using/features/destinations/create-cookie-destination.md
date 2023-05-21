---
description: En cookie-destination returnerar och skriver data till en cookie i användarens webbläsare. Cookien innehåller data som kan läsas av andra plattformar som har åtkomst till sidan. Följ de här instruktionerna för att skapa en cookie-destination med [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: Konfigurera en cookie-destination
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 2%

---

# Konfigurera en cookie-destination {#create-cookie-destination}

En cookie-destination returnerar och skriver data till en cookie i användarens webbläsare. Cookien innehåller data som kan läsas av andra plattformar som har åtkomst till sidan. Följ de här instruktionerna för att skapa en cookie-destination med [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Om du vill skapa en ny cookie-destination går du till **[!UICONTROL Audience Data > Destinations > Create New Destination]** och slutföra avsnitten enligt nedan.

## Grundläggande information {#basic-information}

Det här avsnittet innehåller fält och alternativ som startar skapandet av cookie-målet. Så här slutför du det här avsnittet:

1. Klicka **[!UICONTROL Basic Information]** för att visa kontrollerna.
2. Namnge målet. Undvik förkortningar och specialtecken.
3. *(Valfritt)* Beskriv målet. En kort beskrivning är ett effektivt sätt att definiera eller ange mer information om en destination.
4. I **[!UICONTROL Category]** lista, välj **[!UICONTROL Custom]**.
5. I **[!UICONTROL Environment]** lista, välj **[!UICONTROL Browser]**. Du kan inte konfigurera cookie-mål för inbyggda mobilmiljöer, som Android- eller iOS-appar.
6. I **[!UICONTROL Type]** lista, klicka på **[!UICONTROL Cookie]**.
7. *(Valfritt)* Välj en **[!UICONTROL Auto-fill Destination Mapping]**. Alternativen är:
   * **[!UICONTROL Segment ID]**: Lägger till och skickar automatiskt segment-ID:t till målet.
   * **[!UICONTROL Integration Code Value]**: Lägger automatiskt till och skickar segmentintegreringskoden till målmappningen. Integrationskoden är en unik identifierare som skapas och används av kunden. Det får innehålla högst 255 tecken.
8. Klicka **[!UICONTROL Next]** för att gå till [!UICONTROL Configuration] inställningar eller klicka på **[!UICONTROL Data Export Labels]** om du vill använda exportkontroller på målet.

## Dataexportetiketter {#data-export-labels-cookies}

Det här avsnittet innehåller alternativ som kan användas [dataexportkontroller](../../features/data-export-controls.md) till en cookie-destination. Hoppa över det här steget om du inte använder dataexportkontroller. Så här slutför du det här avsnittet:

1. Klicka **[!UICONTROL Data Export Labels]** för att visa kontrollerna.
2. Välj en etikett som motsvarar den dataexportkontroll som används på målet (se [Lägg till exportetiketter till ett mål](/help/using/features/destinations/add-data-export-labels.md) för mer information).
3. Klicka på **[!UICONTROL Save]**.

## Konfiguration {#configuration}

Det här avsnittet innehåller fält och alternativ som gör att du kan konfigurera cookien för ditt mål.

>[!NOTE]
>
>[!DNL Audience Manager] kodar data skrivna till målcookien. Blanksteg kodas till exempel som `%20` och semikolon kodas som `%3B`.

Så här slutför du det här avsnittet:

1. Klicka **[!UICONTROL Configuration]** för att visa kontrollerna
1. Ge kakan ett namn. Undvik förkortningar och specialtecken.
1. Välj ett dataformatalternativ. Med dessa alternativ kan du välja avgränsare och avgränsare för nyckelvärdepar som skickar segmentdata till ett mål. Formatalternativen är:
   * **Enkel nyckel:** Här kan du ange nyckeln i ett nyckelvärdepar. Du anger värdet när du har markerat ett segment i [!UICONTROL Segment Mappings] nedan.
   * **Flera tangenter:** Här kan du ange nyckel och värde för ett nyckelvärdepar. Du skapar nyckelvärdepar när du har valt ett segment i segmentmappningsavsnittet nedan.
Se [Standard- och serienyckelpar](../../features/destinations/key-value-pairs.md) om du vill ha mer information om dessa dataelement.
1. Klicka på **[!UICONTROL Save]**.

Alla andra inställningar är valfria. Mer information om **[!UICONTROL Cookie Domain]** och **[!UICONTROL Publish data to]** inställningar, se [Valfria inställningar för cookie-mål](/help/using/features/destinations/cookie-destination-options.md).

## Segmentmappningar {#segments-mapping}

I det här avsnittet kan du söka efter och lägga till segment i målet. Så här slutför du det här avsnittet:

1. Klicka **[!UICONTROL Segment Mappings]** för att visa kontrollerna.
1. I **[!UICONTROL Search and Add Segments]** börjar du skriva namnet på ett segment eller klickar på **[!UICONTROL Browse All Segments]** om du vill bläddra i en lista över tillgängliga segment.
1. Klicka **[!UICONTROL Add Selected Segments]** när du hittar det segment du vill använda. När du lägger till ett segment öppnas [!UICONTROL Edit Mapping] -fönstret.
1. I [!UICONTROL Edit Mapping] dialog:
   * **[!UICONTROL Mapping]** gör att du kan ange ett värde för nyckeln som anges i avsnittet Konfiguration ovan.
   * **[!UICONTROL Publish from]** Med kan du ange start- och slutdatum för målet. Om slutdatumet är tomt upphör målet aldrig att gälla.
1. Klicka på **[!UICONTROL Save]**.
1. Klicka på **[!UICONTROL Done]**.
