---
description: Den här proceduren kräver en AdWords-återmarknadsföringslista, pixelkod och ett Audience Manager URL-mål. Det kallas även en återmarknadsföringslista för integrering av sökannonser (RLSA). Gäller endast betald sökning.
seo-description: Den här proceduren kräver en AdWords-återmarknadsföringslista, pixelkod och ett Audience Manager URL-mål. Det kallas även en återmarknadsföringslista för integrering av sökannonser (RLSA). Gäller endast betald sökning.
seo-title: Skicka segment till en Google AdWords-lista för återmarknadsföring
solution: Audience Manager
title: Skicka segment till en Google AdWords-lista för återmarknadsföring
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

Den här proceduren kräver en [!DNL Google Ads] återmarknadsföringslista, pixelkod och ett Audience Manager [!DNL URL] [!DNL destination]. Det kallas även en återmarknadsföringslista för integrering av sökannonser ([!DNL RLSA]). Gäller endast betald sökning.

>[!IMPORTANT]
>Observera att detta inte är en produkterad integrering av de två systemen.

Så här ställer du in en [!DNL Google Ads] återmarknadsföringslista som en [!DNL Audience Manager] [!DNL URL destination]:

1. I ditt [!DNL Google Ads] konto [skapar du en lista](https://support.google.com/adwords/answer/2454064?hl=en) över återmarknadsföring av webbplatser och skriver ned ditt konverterings-ID.
1. Använd följande URL som mall för bas-URL och säker URL. Ersätt avsnittet xxxxxxxx med ditt konverterings-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. I Audience Manager [skapar du en [!DNL URL destination]](../../features/destinations/create-url-destination.md) eller redigerar en befintlig [!DNL destination]. Använd följande inställningar när du skapar [!DNL destination]:
   * Typ: URL
   * Serialisera: Aktiverad
   * Avgränsare: Semikolon (;)

1. Lägg till koden från steg 2 i [!UICONTROL Segment Mappings] fälten [!DNL URL] och i [!DNL destination]avsnittet i [!DNL URL][!DNL Secure URL] . Lägg till prefix i koden med `http:` och `https:` i [!DNL URL] respektive [!DNL Secure URL] fält.

   >[!IMPORTANT]
   >
   >Ersätt kodade et-tecken `&` med okodade et-tecken `&`

   Osäker [!DNL URL] kod:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Säker [!DNL URL] kod:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klicka på **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Om du arbetar med flera segment ska du hämta en ny pixel för varje segment som du vill mappa till ett [!DNL Google Ads][!DNL destination]. Detta garanterar att data tillämpas på rätt lista för återmarknadsföring.

1. När du mappar ett nytt segment till det här [!DNL destination] i Audience Manager definierar du mappningen som `aam=segmentID` och ersätter `segmentID` med segmentets ID.
1. När du definierar en bucket i [!DNL Google Ads]skapar du en regel som matchar mappningen som definieras i steg 6.

En slutförd mappning kan se ut ungefär så här:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL-mål]](../../features/destinations/destinations.md)
>* [Skapa en [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Om AdWords Remarketing Lists](https://support.google.com/adwords/answer/2472738)
>* [Hur AdWords Remarketing fungerar](https://support.google.com/adwords/answer/2454000)

