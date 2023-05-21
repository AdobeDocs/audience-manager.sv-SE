---
description: Du kan skicka kvalificerade segment till Google Ad Manager via en integrering på klientsidan (webbläsaren) eller via en integrering på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för Google Publisher-taggar i Audience Manager.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Skapa en GPT-destination
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---

# Skapa en GPT-destination {#create-a-gpt-destination}

Du kan skicka kvalificerade segment till [!DNL Google Ad Manager] via en integrering på klientsidan (webbläsare) eller en integration på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för [!DNL Google Publisher Tags] i Audience Manager.

## Destinationer 

I Audience Manager *`destination`* är ett annat system (annonsserver, [!DNL DSP], annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som gör att du kan skapa och hantera dessa dataleveransprocesser. Målfunktionerna för Audience Manager finns i *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Kom igång genom att klicka **[!UICONTROL Add New Destination]** och följ stegen nedan.

## Grundläggande information

Slutför [!UICONTROL Basic Information] avsnitt:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** från [!UICONTROL Type] nedrullningsbar lista.
1. Klicka **[!UICONTROL Next]** och gå vidare till [!UICONTROL Configuration] och [!UICONTROL Segment Mappings] -avsnitt.

## Cookie-konfiguration

Ange följande för att slutföra [!UICONTROL Configuration] sektion (andra fält är valfria):

1. **Cookie-namn:** Ange ett kort beskrivande namn för din cookie.
1. **Dataformat:** Välj **[!UICONTROL "Single Key"]** alternativ.
1. **Nyckel:** Ange ett nyckelnamn.
1. **Serialisera:** Välj **[!UICONTROL Enable]** kryssrutan.
1. **Serieavgränsare:** Använd endast kommatecken.

## Segmentmappningar

Så här lägger du till ett segment i en cookie-destination:

1. Hitta segment: The [!UICONTROL Segment Mappings] I finns två sökverktyg som hjälper dig att hitta segment. Så här söker du efter ett segment:

   * Alternativ 1: Börja skriva ett segmentnamn i sökfältet. Fältet uppdateras automatiskt baserat på den angivna texten. Klicka **[!UICONTROL Add]** när du har hittat det segment du vill använda.
   * Alternativ 2: Klicka **[!UICONTROL Browse All Segments]** om du vill öppna ett fönster där du kan bläddra efter segment efter namn eller lagringsplats. Klicka **[!UICONTROL Add Selected Segments]** när det är klart.

1. **Lägg till mappningar:** Ange segment-ID i mappningsfältet i mappningsfönstret och klicka på **[!UICONTROL Save]**.

1. Klicka på **[!UICONTROL Done]**.
