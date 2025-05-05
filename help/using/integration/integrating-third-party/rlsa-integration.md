---
description: Den här proceduren kräver en AdWords-återmarknadsföringslista, pixelkod och ett Audience Manager URL-mål. Det kallas även en återmarknadsföringslista för integrering av sökannonser (RLSA). Gäller endast betald sökning.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Skicka segment till en Google AdWords Remarketing-lista
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Skicka segment till en Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

Den här proceduren kräver en [!DNL Google Ads]-återmarknadsföringslista, pixelkod och Audience Manager [!DNL URL] [!DNL destination]. Det kallas även en återmarknadsföringslista för sökannonsering ([!DNL RLSA])-integrering. Gäller endast betald sökning.

>[!IMPORTANT]
>Observera att detta inte är en produkterad integrering av de två systemen.

Så här konfigurerar du en [!DNL Google Ads]-remarketing-lista som en [!DNL Audience Manager] [!DNL URL destination]:

1. I ditt [!DNL Google Ads]-konto [skapar du en ny marknadsföringslista för en webbplats](https://support.google.com/tagmanager/answer/6106960?hl=en) och skriver ned ditt konverterings-ID.
1. Använd följande URL som mall för bas-URL och säker URL. Ersätt avsnittet xxxxxxxx med ditt konverterings-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. [Skapa en [!DNL URL destination]](../../features/destinations/create-url-destination.md) eller redigera en befintlig [!DNL destination] i Audience Manager. Använd följande inställningar när du skapar [!DNL destination]:
   * Typ: URL
   * Serialisera: Aktiverat
   * Avgränsare: Semikolon (&semi; )

1. I avsnittet [!UICONTROL Segment Mappings] i [!DNL URL] [!DNL destination] lägger du till koden från steg 2 i fälten [!DNL URL] och [!DNL Secure URL]. Lägg till `http:` och `https:` i fälten [!DNL URL] och [!DNL Secure URL] som prefix.

   >[!IMPORTANT]
   >
   >Ersätt kodade et-tecken `&` med okodade et-tecken `&`

   Osäker [!DNL URL]-kod:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Säker [!DNL URL]-kod:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klicka på **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Om du arbetar med flera segment hämtar du en ny pixel för varje segment som du vill mappa till [!DNL Google Ads] [!DNL destination]. Detta garanterar att data tillämpas på rätt lista för återmarknadsföring.

1. När du mappar ett nytt segment till denna/detta [!DNL destination] i Audience Manager definierar du mappningen som `aam=segmentID` och ersätter `segmentID` med ID:t för ditt segment.
1. När du definierar en bucket i [!DNL Google Ads] skapar du en regel som matchar mappningen som definieras i steg 6.

En slutförd mappning kan se ut ungefär så här:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Skapa en [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Om AdWords Remarketing Lists](https://support.google.com/adwords/answer/2472738)
>* [Hur AdWords Remarketing fungerar](https://support.google.com/adwords/answer/2454000)
