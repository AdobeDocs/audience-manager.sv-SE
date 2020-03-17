---
description: Den här proceduren kräver en AdWords-återmarknadsföringslista, pixelkod och ett mål för Audience Manager-URL. Det kallas även en återmarknadsföringslista för integrering av sökannonser (RLSA). Gäller endast betald sökning.
seo-description: Den här proceduren kräver en AdWords-återmarknadsföringslista, pixelkod och ett mål för Audience Manager-URL. Det kallas även en återmarknadsföringslista för integrering av sökannonser (RLSA). Gäller endast betald sökning.
seo-title: Skicka segment till en Google AdWords Remarketing-lista
solution: Audience Manager
title: Skicka segment till en Google AdWords Remarketing-lista
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Skicka segment till en Google Ads Remarketing-lista {#send-segments-to-a-google-adwords-remarketing-list}

Den här proceduren kräver en [!DNL Google Ads] återmarknadsföringslista, pixelkod och ett Audience Manager- [!DNL URL] mål. Det kallas även en återmarknadsföringslista för integrering av sökannonser ([!DNL RLSA]). Gäller endast betald sökning.

>[!IMPORTANT]
>Observera att detta inte är en produkterad integrering av de två systemen.

Så här ställer du in en [!DNL Google Ads] återmarknadsföringslista som ett [!DNL Audience Manager] URL-mål:

1. I ditt [!DNL Google Ads] konto [skapar du en lista](https://support.google.com/adwords/answer/2454064?hl=en) över återmarknadsföring av webbplatser och skriver ned ditt konverterings-ID.
1. Använd följande URL som mall för bas-URL och säker URL. Ersätt avsnittet xxxxxxxx med ditt konverterings-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. I Audience Manager [skapar du ett URL-mål](../../features/destinations/create-url-destination.md) eller redigerar ett befintligt mål. Använd följande inställningar när du skapar målet:
   * Typ: URL
   * Serialisera: Aktiverad
   * Avgränsare: Semikolon (;)

1. Lägg till koden från steg 2 i [!UICONTROL Segment Mappings] fälten [!DNL URL] och [!DNL URL] [!DNL Secure URL] i målavsnittet. Lägg till prefix i koden med `http:` och `https:` i [!DNL URL] respektive [!DNL Secure URL] fält.

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
   >Om du arbetar med flera segment ska du skaffa en ny pixel för varje segment som du vill mappa till ett Google Ads-mål. Detta garanterar att data tillämpas på rätt lista för återmarknadsföring.

1. När du mappar ett nytt segment till det här målet i Audience Manager definierar du mappningen som `aam=segmentID` och ersätter `segmentID` med segmentets ID.
1. När du definierar en bucket i [!DNL Google Ads]skapar du en regel som matchar mappningen som definieras i steg 6.

En slutförd mappning kan se ut ungefär så här:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [Mål](../../features/destinations/destinations.md)
>* [Skapa ett URL-mål](../../features/destinations/create-url-destination.md)
>* [Om AdWords Remarketing Lists](https://support.google.com/adwords/answer/2472738)
>* [Hur AdWords Remarketing fungerar](https://support.google.com/adwords/answer/2454000)

