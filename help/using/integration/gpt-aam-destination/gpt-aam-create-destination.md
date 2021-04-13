---
description: Du kan skicka kvalificerade segment till Google Ad Manager via en klientintegration (på webbläsarsidan) eller en integration på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för Google Publisher-taggar i Audience Manager.
seo-description: Du kan skicka kvalificerade segment till Google Ad Manager via en klientintegration (på webbläsarsidan) eller en integration på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för Google Publisher-taggar i Audience Manager.
seo-title: Skapa en GPT-destination
solution: Audience Manager
title: Skapa en GPT-destination
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Tredjepartsintegrering
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 7%

---

# Skapa en GPT-destination {#create-a-gpt-destination}

Du kan skicka kvalificerade segment till [!DNL Google Ad Manager] via en integrering på klientsidan (webbläsarsidan) eller en integrering på serversidan. Om du väljer integrering på klientsidan måste du skapa ett cookie-baserat mål för [!DNL Google Publisher Tags] i Audience Manager.

## Destinationer 

I Audience Manager är en *`destination`* vilket annat system som helst (annonsserver, [!DNL DSP], annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som gör att du kan skapa och hantera dessa dataleveransprocesser. Målfunktionerna för Audience Manager finns i *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Kom igång genom att klicka på **[!UICONTROL Add New Destination]** och följa stegen nedan.

## Grundläggande information

Så här slutför du avsnittet [!UICONTROL Basic Information]:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** i listrutan [!UICONTROL Type].
1. Klicka på **[!UICONTROL Next]** och gå vidare till avsnitten [!UICONTROL Configuration] och [!UICONTROL Segment Mappings].

## Cookie-konfiguration

Ange följande för att slutföra [!UICONTROL Configuration]-avsnittet (andra fält är valfria):

1. **Cookie-namn:** Ange ett kort beskrivande namn för din cookie.
1. **Dataformat:** Välj  **[!UICONTROL "Single Key"]** alternativet.
1. **Nyckel:** Ange ett nyckelnamn.
1. **Serialisera:** Markera  **[!UICONTROL Enable]** kryssrutan.
1. **Seriell avgränsare:** Använd endast kommatecken.

## Segmentmappningar

Så här lägger du till ett segment i en cookie-destination:

1. Hitta segment: Avsnittet [!UICONTROL Segment Mappings] innehåller två sökverktyg som hjälper dig att hitta segment. Så här söker du efter ett segment:

   * Alternativ 1: Börja skriva ett segmentnamn i sökfältet. Fältet uppdateras automatiskt baserat på den angivna texten. Klicka på **[!UICONTROL Add]** när du har hittat det segment du vill använda.
   * Alternativ 2: Klicka på **[!UICONTROL Browse All Segments]** för att öppna ett fönster där du kan bläddra efter segment efter namn eller lagringsplats. Klicka på **[!UICONTROL Add Selected Segments]** när du är klar.

1. **Lägg till mappningar:** Ange segment-ID i mappningsfältet i mappningsfönstret och klicka på  **[!UICONTROL Save]**.

1. Klicka på **[!UICONTROL Done]**.
