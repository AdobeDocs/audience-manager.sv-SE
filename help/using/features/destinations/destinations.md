---
description: I Audience Manager är målet ett tredjepartssystem (annonsserver, DSP, annonsnätverk osv.) som du vill dela data med. Destination Builder är det verktyg du använde för att skapa och hantera mål för cookies, URL eller server-to-server.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: I Audience Manager är målet ett tredjepartssystem (annonsserver, DSP, annonsnätverk osv.) som du vill dela data med. Destination Builder är det verktyg du använde för att skapa och hantera mål för cookies, URL eller server-to-server.
seo-title: 'Mål '
solution: Audience Manager
title: 'Mål '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: e141d04201b94bac30cdbe97818cb8eb91ebbaea

---


# Destinations Overview {#destinations}

I Audience Manager är målet ett tredjepartssystem (annonsserver, [!DNL DSP]annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] är det verktyg som du använde för att skapa och hantera cookies [!DNL URL]eller server-till-server-mål.

## Syfte och fördelar {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] och [!UICONTROL Destination Builder] låter dig skapa mål och skicka information om segmenterade användare till din datapartner. Detta hjälper dig att:

* **Skydda datavärde:** I stället för att skicka alla användardata till ett mål [!UICONTROL Destination Builder] kan du bara dela specifik information om kvalificerade användare.
* **Vidta åtgärder för dina data:** Genom att skicka data till en målpartner kan de snabbt utveckla och inrikta sig på kvalificerade målgruppssegment.
* **Minska den tekniska overheadkostnaden:** Affärsanvändare kan konfigurera mål säkert i [!UICONTROL Destination Builder] gränssnittet. Detta minskar tiden som krävs för testning före driftsättning. Med [!UICONTROL Destination Builder]hjälp av kan ni skapa, hantera och ta bort destinationer allt eftersom företagets behov förändras, utan att behöva gå igenom en lång utvecklingscykel.

## Tekniska överväganden {#technical-considerations}

<!-- destination-delivery-methods.xml -->

Dataöverföringen beror på hur din datapartner vill eller kan ta emot målinformation. Tekniska begränsningar eller tekniska begränsningar kan hindra en destination från att ta emot data via [!DNL URL]processer, cookies eller server-till-server. Samarbeta med din tredjepartspartner för att avgöra vilken metod de kan använda.

## Fundera på verksamheten {#business-considerations}

Affärsbeslut för att välja en leveransmetod jämfört med en annan beror på den tekniska kapaciteten hos målpartnern och vad du vill göra med kvalificerad användarinformation. Tekniska begränsningar kan till exempel begränsa dina alternativ om ett mål inte kan ta emot data med en viss leveransmetod. Om det inte finns några tekniska problem kan du skicka information baserat på hur du vill vidta åtgärder för dessa data. Exempel:

* [!DNL URL]s och cookie-baserade mål fungerar nästan synkront med användaråtgärder på en sida.
* Server-till-server-metoder är bra för att bygga djupgående målgruppssegment över tid.

## Måltyper och vanliga användningsområden {#destination-types}

Exemplen i följande tabell kan hjälpa dig att förstå när du ska använda ett visst mål och skillnaderna mellan olika typer.

| Måltyp | Används vanligen vid | Exempel | Överväganden |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Ni måste skicka data till andra Adobe Experience Cloud-lösningar. | Skicka data till Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Ni måste skicka målgruppssegment till personbaserade miljöer, som Facebook. | Leverera personaliserade erbjudanden till befintliga kunder utifrån deras inköpshistorik | Målgruppsanpassning görs med hjälp av hash-identifierare. Se [Personbaserade mål](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-till-server**) | <ul><li>Omedelbar dataöverföring krävs inte.</li><li>Samla in data för att bygga upp en stor målgruppspool med kvalificerade användare.</li></ul> | Samla in data över tid (timmar eller dagar) för att använda dem i en kampanj som ska köras vid ett senare datum. | <ul><li>Överför data om nya och tidigare webbplatsbesökare. </li><li>Besökarna behöver inte ses igen för att kvalificera sig för andra segment.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** eller **cookie**) | Ni måste överföra data omedelbart så att en destination kan vidta åtgärder mot en kvalificerad användare direkt. | Skicka data från en biljettinköpsplats. Använd en URL eller en cookie-destination för att kvalificera användaren och omedelbart återskapa målet. | <ul><li>Överför endast data om nya besökare. </li><li>Besökarna måste ses igen för att bli kvalificerade för segmentet.</li></ul> |
