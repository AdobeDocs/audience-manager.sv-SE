---
description: En URL-adress gör pixelanrop från en sida till målet. Följ de här instruktionerna för att skapa ett URL-mål med Destination Builder.
seo-description: A URL destination makes pixel calls from a page to your destination. Follow these instructions to create a URL destination with Destination Builder.
seo-title: Configure a URL Destination
solution: Audience Manager
title: Konfigurera en URL-destination
feature: Destination Basics
exl-id: b5af87c9-4460-43a7-9808-242eac876c39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 2%

---

# Konfigurera en [!DNL URL Destination] {#configure-url-destination}

A [!DNL URL destination] gör pixelanrop från en sida till [!DNL destination]. Följ dessa anvisningar för att skapa en [!DNL URL] [!DNL destination] med [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

Skapa en ny [!DNL URL] [!DNL destination], gå till **[!UICONTROL Audience Data > Destinations > Create New Destination]** och slutföra avsnitten enligt nedan.

## Grundläggande information {#basic-info}

Det här avsnittet innehåller fält och alternativ som startar [!DNL URL destination] skapande. Så här slutför du det här avsnittet:

1. Klicka **[!UICONTROL Basic Information]** för att visa kontrollerna.
2. Namnge [!DNL destination]. Undvik förkortningar och specialtecken.
3. *(Valfritt)* Beskriv [!DNL destination]. En kort beskrivning är ett effektivt sätt att definiera eller tillhandahålla mer information om en [!DNL destination].
4. I **[!UICONTROL Category]** lista, välj **[!UICONTROL Custom]**.
5. I **[!UICONTROL Environment]** väljer du den miljö där utlösaren [!DNL URL destination].
6. I **[!UICONTROL Type]** lista, klicka på **[!UICONTROL URL]**.
7. *(Valfritt)* Välj en **[!UICONTROL Auto-fill Destination Mapping]**. Alternativen är:
   * **[!UICONTROL Segment ID]**: Lägger till och skickar automatiskt segment-ID:t till [!DNL destination].
   * **[!UICONTROL Integration Code Value]**: Lägger automatiskt till och skickar segmentintegreringskoden till målmappningen. Integrationskoden är en unik identifierare som skapas och används av kunden. Det får innehålla högst 255 tecken.
8. Klicka **[!UICONTROL Next]** för att gå till [!UICONTROL Configuration] inställningar eller klicka på **[!UICONTROL Data Export Labels]** för att använda exportkontroller på [!DNL destination].

## [!UICONTROL Data Export Labels] {#data-export-labels-dest}

Det här avsnittet innehåller alternativ som kan användas [dataexportkontroller](../../features/data-export-controls.md) till [!DNL URL] mål. Hoppa över det här steget om du inte använder dataexportkontroller. Så här slutför du det här avsnittet:

1. Klicka **[!UICONTROL Data Export Labels]** för att visa kontrollerna.
2. Välj en etikett som motsvarar den dataexportkontroll som används på målet (se [Lägg till exportetiketter till ett mål](/help/using/features/destinations/add-data-export-labels.md) för mer information).
3. Klicka på **[!UICONTROL Save]**.

## Konfiguration {#configure-base-data}

Det här avsnittet innehåller alternativ som gör att du kan ange en bas [!DNL URL] och dataavgränsare som skickas in av [!DNL URL] sträng. Det här avsnittet är valfritt. Så här slutför du det här avsnittet:

1. Klicka **[!UICONTROL Configuration]** för att visa kontrollerna.
1. *(Valfritt)* Välj **[!UICONTROL Serialize]** kryssruta.
På så sätt kan du skicka segment till en [!DNL destination] sekventiellt i stället för att göra separata anrop för varje segment. Serialisering hjälper till att effektivisera dataöverföringar. Om du markerar den här kryssrutan visas URL- och avgränsningsfälten. Mer information finns i [Standard- och serienyckelpar](../../features/destinations/key-value-pairs.md).
1. Om du väljer **[!UICONTROL Serialize]** måste du också konfigurera URL- och avgränsningsfälten som beskrivs nedan.

| Fält | Beskrivning |
|--- |--- |
| [!UICONTROL Base URL] | Basdelen av en standard `HTTP` [!DNL URL] som inte ändras. Du måste också placera `%ALIAS%`  [platshållarmakro](../../features/destinations/destination-macros.md#destination-macros-defined) i bas-URL:en. Exempel på: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Secure URL] | Basdelen av en säker `HTTPS` [!DNL URL] som inte ändras. Du måste också placera `%ALIAS%`   [platshållarmakro](../../features/destinations/destination-macros.md#destination-macros-defined) i bas-URL:en. Exempel på: `https://www.myCompany.com/%alias%...` |
| [!UICONTROL Delimiter] | Symbolen som avgränsar segmentvariablerna i [!DNL URL] sträng. Det här är vanligtvis ett komma eller semikolon. Hämta den här informationen från din målpartner. |

## [!UICONTROL Segment Mappings] {#segment-mappings}

I det här avsnittet kan du söka efter och lägga till segment i [!UICONTROL destination]. Så här slutför du det här avsnittet:

1. Klicka **[!UICONTROL Segment Mappings]** för att visa kontrollerna.
1. I **[!UICONTROL Search and Add Segments]** börjar du skriva namnet på ett segment eller klickar på **[!UICONTROL Browse All Segments]** bläddra i en lista över tillgängliga segment.
1. Klicka **[!UICONTROL Add Selected Segments]** när du hittar det segment du vill använda. När du lägger till ett segment öppnas [!UICONTROL Edit Mapping] -fönstret.
1. I [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: Ange nyckelvärdepar som används av segmentet.
   * **[!UICONTROL Start Date]** och **[!UICONTROL End Date]**: Välj ett start- och slutdatum för [!DNL destination]. Om slutdatumet är tomt visas [!DNL destination] upphör aldrig att gälla.
1. Klicka på **[!UICONTROL Done]**.
