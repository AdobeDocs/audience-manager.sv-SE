---
description: Du kan skicka kvalificerade segment till DFP via en integrering på klientsidan (webbläsarsidan) eller via en integrering på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för Google Publisher-taggar i Audience Manager.
seo-description: Du kan skicka kvalificerade segment till DFP via en integrering på klientsidan (webbläsarsidan) eller via en integrering på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för Google Publisher-taggar i Audience Manager.
seo-title: Skapa ett GPT-mål
solution: Audience Manager
title: Skapa ett GPT-mål
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Skapa ett GPT-mål {#create-a-gpt-destination}

Du kan skicka kvalificerade segment till [!DNL DFP] via en klientintegration (på webbläsarsidan) eller en integration på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för [!DNL Google Publisher Tags] i Audience Manager.

## Mål 

I Audience Manager *`destination`* är a vilket annat system som helst (annonsserver, [!DNL DSP]annonsnätverk etc.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som gör att du kan skapa och hantera dessa dataleveransprocesser. Målfunktionerna för Audience Manager finns i *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Kom igång genom att klicka **[!UICONTROL Add New Destination]**och följa stegen nedan.

## Grundläggande information

Så här slutför du [!UICONTROL Basic Information] avsnittet:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** i [!UICONTROL Type] listrutan.
1. Klicka **[!UICONTROL Next]** och gå vidare till avsnitten [!UICONTROL Configuration] och [!UICONTROL Segment Mappings] .

## Cookie-konfiguration

Ange följande för att slutföra [!UICONTROL Configuration] avsnittet (andra fält är valfria):

1. **Cookie-namn:** Ange ett kort beskrivande namn för din cookie.
1. **Dataformat:** Välj **[!UICONTROL "Single Key"]** alternativet.
1. **Nyckel:** Ange ett nyckelnamn.
1. **Serialisera:** Markera **[!UICONTROL Enable]** kryssrutan.
1. **Serieavgränsare:** Använd endast kommatecken.

## Segmentmappningar

Så här lägger du till ett segment i en cookie-destination:

1. Hitta segment: Avsnittet innehåller två sökverktyg som hjälper dig att hitta segment [!UICONTROL Segment Mappings] . Så här söker du efter ett segment:

   * Alternativ 1: Börja skriva ett segmentnamn i sökfältet. Fältet uppdateras automatiskt baserat på den angivna texten. Klicka **[!UICONTROL Add]** när du har hittat det segment du vill använda.
   * Alternativ 2: Klicka **[!UICONTROL Browse All Segments]** för att öppna ett fönster där du kan bläddra efter segment efter namn eller lagringsplats. Klicka **[!UICONTROL Add Selected Segments]** när du är klar.

1. **Lägg till mappningar:** Ange segment-ID i mappningsfältet i mappningsfönstret och klicka på **[!UICONTROL Save]**.

1. Klicka på **[!UICONTROL Done]**.