---
description: En cookie-destination returnerar och skriver data till en cookie i användarens webbläsare. Cookien innehåller data som kan läsas av andra plattformar som har åtkomst till sidan. Följ de här instruktionerna för att skapa en cookie-destination med [!UICONTROL Destination Builder].
seo-description: En cookie-destination returnerar och skriver data till en cookie i användarens webbläsare. Cookien innehåller data som kan läsas av andra plattformar som har åtkomst till sidan. Följ de här instruktionerna för att skapa en cookie-destination med [!UICONTROL Destination Builder].
seo-title: Konfigurera en cookie-destination
solution: Audience Manager
title: Konfigurera en cookie-destination
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---


# Konfigurera en cookie-destination {#create-cookie-destination}

En cookie-destination returnerar och skriver data till en cookie i användarens webbläsare. Cookien innehåller data som kan läsas av andra plattformar som har åtkomst till sidan. Följ de här instruktionerna för att skapa en cookie-destination med [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

Om du vill skapa ett nytt mål för cookie går du till **[!UICONTROL Audience Data > Destinations > Create New Destination]** och slutför avsnitten enligt nedan.

## Grundläggande information {#basic-information}

Det här avsnittet innehåller fält och alternativ som startar skapandet av cookie-målet. Så här slutför du det här avsnittet:

1. Klicka på **[!UICONTROL Basic Information]** för att visa kontrollerna.
2. Namnge målet. Undvik förkortningar och specialtecken.
3. *(Valfritt)* Beskriv målet. En kort beskrivning är ett effektivt sätt att definiera eller ange mer information om en destination.
4. Välj **[!UICONTROL Custom]** i listan **[!UICONTROL Category]**.
5. Välj **[!UICONTROL Browser]** i listan **[!UICONTROL Environment]**. Du kan inte konfigurera cookie-mål för inbyggda mobilmiljöer, som Android- eller iOS-appar.
6. Klicka på **[!UICONTROL Cookie]** i listan **[!UICONTROL Type]**.
7. *(Valfritt)* Markera ett  **[!UICONTROL Auto-fill Destination Mapping]**. Alternativen är:
   * **[!UICONTROL Segment ID]**: Lägger till och skickar automatiskt segment-ID:t till målet.
   * **[!UICONTROL Integration Code Value]**: Lägger automatiskt till och skickar segmentintegreringskoden till målmappningen. Integrationskoden är en unik identifierare som skapas och används av kunden. Det får innehålla högst 255 tecken.
8. Klicka på **[!UICONTROL Next]** om du vill gå till [!UICONTROL Configuration]-inställningarna eller klicka på **[!UICONTROL Data Export Labels]** om du vill använda exportkontroller på målet.

## Dataexportetiketter {#data-export-labels-cookies}

Det här avsnittet innehåller alternativ som tillämpar [dataexportkontroller](../../features/data-export-controls.md) på en cookie-destination. Hoppa över det här steget om du inte använder dataexportkontroller. Så här slutför du det här avsnittet:

1. Klicka på **[!UICONTROL Data Export Labels]** för att visa kontrollerna.
2. Välj en etikett som motsvarar den dataexportkontroll som används för målet (mer information finns i [Lägg till exportetiketter till ett mål](/help/using/features/destinations/add-data-export-labels.md)).
3. Klicka på **[!UICONTROL Save]**.

## Konfiguration {#configuration}

Det här avsnittet innehåller fält och alternativ som gör att du kan konfigurera cookien för ditt mål.

>[!NOTE]
>
>[!DNL Audience Manager] kodar data skrivna till målcookien. Blanksteg kodas till exempel som `%20` och semikolon kodas som `%3B`.

Så här slutför du det här avsnittet:

1. Klicka på **[!UICONTROL Configuration]** för att visa kontrollerna
1. Ge kakan ett namn. Undvik förkortningar och specialtecken.
1. Välj ett dataformatalternativ. Med dessa alternativ kan du välja avgränsare och avgränsare för nyckelvärdepar som skickar segmentdata till ett mål. Formatalternativen är:
   * **En tangent:** Gör att du kan ange tangenten i ett nyckelvärdepar. Du anger värdet när du har valt ett segment i [!UICONTROL Segment Mappings]-avsnittet nedan.
   * **Flera tangenter:** Här kan du ange tangent och värde för ett nyckel/värde-par. Du skapar nyckelvärdepar när du har valt ett segment i segmentmappningsavsnittet nedan.
Mer information om dessa dataelement finns i [Standard- och Serial Key-Value-par](../../features/destinations/key-value-pairs.md).
1. Klicka på **[!UICONTROL Save]**.

Alla andra inställningar är valfria. Mer information om inställningarna **[!UICONTROL Cookie Domain]** och **[!UICONTROL Publish data to]** finns i [Valfria inställningar för cookie-mål](/help/using/features/destinations/cookie-destination-options.md).

## Segmentmappningar {#segments-mapping}

I det här avsnittet kan du söka efter och lägga till segment i målet. Så här slutför du det här avsnittet:

1. Klicka på **[!UICONTROL Segment Mappings]** för att visa kontrollerna.
1. I rutan **[!UICONTROL Search and Add Segments]** börjar du skriva namnet på ett segment eller klickar på **[!UICONTROL Browse All Segments]** för att bläddra i en lista över tillgängliga segment.
1. Klicka på **[!UICONTROL Add Selected Segments]** när du hittar det segment du vill använda. Om du lägger till ett segment öppnas fönstret [!UICONTROL Edit Mapping].
1. I dialogrutan [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mapping]** gör att du kan ange ett värde för nyckeln som anges i avsnittet Konfiguration ovan.
   * **[!UICONTROL Publish from]** Med kan du ange start- och slutdatum för målet. Om slutdatumet är tomt upphör målet aldrig att gälla.
1. Klicka på **[!UICONTROL Save]**.
1. Klicka på **[!UICONTROL Done]**.