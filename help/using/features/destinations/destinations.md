---
description: Upptäck fördelar, typer och användning av destinationer – alla system från tredje part, som t.ex. en annonsserver eller DSP, där du delar data. Använd Destination Builder för att skapa och hantera cookies, URL-adresser eller server-till-server-mål.
keywords: integrationskod, mål, målöversikt, mål, mål, mål, mål, mål, mål, mål, mål, mål, mål, mål, mål
landing-page-description: Upptäck fördelar, typer och användning av destinationer – alla system från tredje part, som t.ex. en annonsserver eller DSP, där du delar data. Använd Destination Builder för att skapa och hantera cookies, URL-adresser eller server-till-server-mål.
short-description: Discover the advantages, types, and uses of destinations – any third-party system, such as an ad server or DSP, where you share data. Use Destination Builder to create and manage cookies, URL, or server-to-server destinations.
seo-title: Destinations
solution: Audience Manager
title: Destinationer
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 14%

---

# [!UICONTROL Destinations] Översikt {#destinations}

I Audience Manager [!UICONTROL destination] är ett tredjepartssystem (annonsserver, [!DNL DSP], annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] är det verktyg du använde för att skapa och hantera [!UICONTROL cookie], [!DNL URL], eller [!UICONTROL server-to-server destinations].

## Syfte och fördelar {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] och [!UICONTROL Destination Builder] låter dig skapa [!UICONTROL destinations] och skicka information om segmenterade användare till din datapartner. Detta hjälper dig att:

* **Protect datavärde:** I stället för att skicka alla användardata till en [!UICONTROL destination], [!UICONTROL Destination Builder] I kan du bara dela specifik information om kvalificerade användare.
* **Vidta åtgärder för dina data:** Skicka data till en [!UICONTROL destination] partners hjälper dem att snabbt utveckla och inrikta sig på kvalificerade målgruppssegment.
* **Minska den tekniska overheadkostnaden:** Affärsanvändare kan konfigurera [!UICONTROL destinations] säkert i [!UICONTROL Destination Builder] gränssnitt. Detta minskar tiden som krävs för testning före driftsättning. Med [!UICONTROL Destination Builder]skapar, hanterar och tar bort [!UICONTROL destinations] allt efter företagets behov förändras, utan att behöva gå igenom en lång utvecklingscykel.

## Tekniska överväganden {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Leveransen av data beror på hur din datapartner vill eller kan ta emot [!UICONTROL destination] information. Tekniska eller tekniska begränsningar kan förhindra [!UICONTROL destination] från att ta emot data via [!DNL URL], [!UICONTROL cookie], eller [!UICONTROL server-to-server] -processer. Samarbeta med din tredjepartspartner för att avgöra vilken metod de kan använda.

## Fundera på verksamheten {#business-considerations}

Affärsbeslut för att välja en leveransmetod jämfört med en annan beror på den tekniska kapaciteten hos [!UICONTROL destination] och vad du vill göra med kvalificerad användarinformation. Tekniska begränsningar kan till exempel begränsa dina alternativ om en [!UICONTROL destination] kan inte ta emot data med en viss leveransmetod. Om det inte finns några tekniska problem kan du skicka information baserat på hur du vill vidta åtgärder för dessa data. Exempel:

* [!DNL URL]s och [!UICONTROL cookie-based destinations] arbeta nästan synkront med användaråtgärder på en sida.
* [!UICONTROL Server-to-server] metoder är bra att använda för att skapa djupgående målgruppssegment över tid.

## [!UICONTROL Destination] Typer och vanliga användningsområden {#destination-types}

Exemplen i följande tabell kan hjälpa dig att förstå när du ska använda en viss [!UICONTROL destination] och skillnaderna mellan de olika typerna.

| [!UICONTROL Destination] Typ | Används vanligen vid | Exempel | Överväganden |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Ni måste skicka data till andra Adobe Experience Cloud-lösningar. | Skicka data till Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Ni måste skicka målgruppssegment till personbaserade miljöer som Facebook. | Leverera personaliserade erbjudanden till befintliga kunder utifrån deras inköpshistorik | Målgruppsanpassning görs med hjälp av hash-identifierare. Se [Personbaserade mål](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-till-server**) | <ul><li>Omedelbar dataöverföring krävs inte.</li><li>Samla in data för att bygga upp en stor målgruppspool med kvalificerade användare.</li></ul> | Samla in data över tid (timmar eller dagar) för att använda dem i en kampanj som ska köras vid ett senare datum. | <ul><li>Överför data om nya och tidigare webbplatsbesökare. </li><li>Besökarna behöver inte ses igen för att kvalificera sig för andra segment.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** eller **Cookie**) | Ni måste överföra data omedelbart så att en destination kan vidta åtgärder mot en kvalificerad användare direkt. | Skicka data från en biljettinköpsplats. Använd en [!UICONTROL URL] eller [!UICONTROL cookie destination] för att kvalificera användaren och omedelbart återanpassa målgruppen. | <ul><li>Överför endast data om nya besökare. </li><li>Besökarna måste ses igen för att bli kvalificerade för segmentet.</li></ul> |
