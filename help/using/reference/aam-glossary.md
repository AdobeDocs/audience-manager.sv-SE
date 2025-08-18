---
description: Definitioner och länkar till mer läsning.
seo-description: Definitions and links to further reading.
seo-title: Glossary
solution: Audience Manager
title: Ordlista
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: Reference
exl-id: 9e2ee3d3-01b2-4038-abda-fedf0f16f163
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 96%

---

# Ordlista{#glossary}

Definitioner och länkar till mer läsning.

## A-B {#a-b}

**Algoritmiska modeller**

Använd [!UICONTROL Algorithmic Modeling] som ett sätt att nå ut utanför kärnan av de användare du har identifierat. Funktionen hjälper er att identifiera nya, unika målgrupper genom automatiserad dataanalys. Hantera [!UICONTROL Algorithmic Models] i **[!UICONTROL Audience Data > Models]**.

Se [Förstå algoritmiska modeller](../features/algorithmic-models/algo-models-overview.md).

**BAAAM**

[!UICONTROL Bulk Management Tools]. [!UICONTROL Bulk Management Tools] i [!DNL Audience Manager] är en Microsoft Excel-baserad uppsättning verktyg med vilka du kan skapa, ändra eller ta bort flera objekt samtidigt med en enda åtgärd. Du kan arbeta med datakällor, härledda signaler, destinationer, mappar, segment och traits. Funktionen använder ett Microsoft Excel-kalkylblad med makron som gör säkra, autentiserade anrop till [!DNL Audience Manager] API:erna.

Se [Verktyg för satsvis hantering](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. En [!UICONTROL CDF]-fil är en satsvis nedladdning av data som samlats in av [!DNL Audience Manager] och som gör att ni kan arbeta med [!DNL Audience Manager]-data utanför de gränser som gäller för användargränssnittet. En [!UICONTROL CDF]-fil innehåller samma data som ett [!DNL Audience Manager]-händelseanrop (`/event`) skickar till våra servrar. Det inkluderar data som användar-ID, trait-ID, segment-ID och alla andra parametrar som samlats in i ett händelseanrop.

Se [Kunddataflöden](../features/cdf-files.md).

**CRM-ID**

CRM-ID är det ID med vilket kunderna identifierar användare i sina egna CRM-system. I stället för CRM-ID använder vi termen DPUUID i Audience Manager.

Se DPUUID i [Index över ID:n i Audience Manager](../reference/ids-in-aam.md).



**Kundadresserbar målgrupp**

I [Addressable Audience](/help/using/features/addressable-audiences.md) representerar detta mätvärde enheter som:
* Har fått antingen ett regelbaserat eller registrerat trait under tillbakablicksperioden
  **OCH**
* Har en ID-synkronisering med den valda destinationen oavsett synkroniseringstidpunkten.



**Kundattribut**

Se [Kundattribut](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=sv-SE) i [!DNL Experience Cloud Core Services] produktdokumentationen.



**Kundmatchningsfrekvens**

Kundadresserbar målgrupp ÷ Kundens totala målgrupp uttryckt som %. Se [Addressable Audience](/help/using/features/addressable-audiences.md).



**Kundens totala målgrupp**

I [Addressable Audience](/help/using/features/addressable-audiences.md) representerar det här mätvärdet antalet enheter som antingen har fått ett regelbaserat trait på era webbplatser eller som har fått ett registrerat trait under tillbakablicksperioden.



**demdex.net**

Demdex.net är en äldre domän som drivs av [!DNL Adobe]. Den återspeglar det ursprungliga namnet på [!DNL Audience Manager] före förvärvet ( [!DNL Demdex]). [!DNL Adobe] förvärvades [!DNL Demdex] 2011 och företaget omprofilerades som [!DNL Audience Manager]. Alla HTTP-anrop till `demdex.net`-domäner är anrop som skickas till [!DNL Adobe].

Se [Förstå anrop till Demdex-domänen](../reference/demdex-calls.md).



**DAID**

[!UICONTROL Device Advertising IDs] är unika enhetsidentifierare som används för att identifiera mobila enheter. Dessa ID:n tilldelas av enhetstillverkaren, inte av Adobe. Vi har stöd för iOS och Android-enhets-ID i [!DNL Audience Manager].

Se [Index över ID:n i Audience Manager](../reference/ids-in-aam.md).



**Destination**

I [!DNL Audience Manager] är ett mål ett annat system (annonsserver, DSP, annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] i användargränssnittet innehåller de verktyg som du kan använda för att skapa och hantera sådana dataleveransprocesser. [!DNL Audience Manager]-destinationsfunktionerna finns i **[!UICONTROL Audience Data > Destinations]**.



**DIL**

[!UICONTROL Data Integration Library] är ett API-bibliotek som används av [!DNL Audience Manager] för att samla in data om användarinteraktioner. Se [API för Data Integration Library (DIL)](../dil/dil-overview.md).



**dpm**

[!UICONTROL Data Provider Match]. Talar om för interna [!DNL Adobe]-system att ett anrop från [!DNL Audience Manager] eller ID-tjänsten skickas i kunddata för synkronisering eller begäran om ID. Se [Förstå anrop till Demdex-domänen](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Tidigare kallat [!DNL Marketing Cloud] ID (MID eller MCID). [!DNL Experience Cloud]-ID är centralt för ID-tjänsten. Det är en unik och beständig identifierare för era webbplatsbesökare. Se Cookies och [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=sv-SE).



**Mapp-trait**

Automatisk gruppering av traits i mapp-taxonomin. Varje mapp i hierarkin skapar automatiskt ett trait som kan användas för att definiera segment.

Se [Mapp-traits: Om](../features/traits/about-folder-traits.md).



**Frekvensbegränsning**

Ett begränsat antal gånger som en annonsör vill visa en viss kampanj för en slutanvändare. Du kan konfigurera olika värden för frekvensbegränsning i [!UICONTROL Segment Builder].

Se [Recency och frekvens](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

Google Advertising ID, det unika enhets-ID som Google tilldelar maskinvaruenheter som kör Android-operativsystemet. Se [Index över ID:n i Audience Manager](../reference/ids-in-aam.md).



**GUID**

En akronym för global unik identifierare. Vi använder inte termen GUID i [!DNL Audience Manager]. I vårt fall är GUID detsamma som [!DNL Audience Manager] UUID.
Se [Index över ID:n i Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identifierare för annonsörer, det unika enhets-ID som Apple tilldelar sina produkter. Se [Index över ID:n i Audience Manager](../reference/ids-in-aam.md).



**Inkommande**

Den process som ni kan använda för att skicka målgruppsdata från andra källor till [!DNL Audience Manager]. Se [Skicka målgruppsdata](/help/using/integration/sending-audience-data/send-audience-data.md).



**Integreringskod**

När ni arbetar med [!DNL Audience Manager]-gränssnittet eller API:t kan ni lägga till en integreringskod när ni skapar traits, segment och datakällor. Integreringskoder har olika syften i dessa fall:

* [!UICONTROL Traits]: en integreringskod är ett fält för ett ID, en SKU eller annat värde som används av era interna affärsprocesser. Valfritt.
* [!UICONTROL Segments]: en integreringskod är ett fält för ett användardefinierat ID eller annan företagsspecifik information. Valfritt.
* [!UICONTROL Data Sources]: integreringskoder krävs när ni vill skapa enhetsövergripande datakällor, använda Adobe Experience Platform Identity Service eller arbeta med [!UICONTROL Profile Merge Rules]. Mer information finns i [Skapa en datakälla](../features/manage-datasources.md#create-data-source).

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Se [Algoritmiska modeller](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Se [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. [!UICONTROL PCS] är en stor databas som körs på Apache Cassandra. Den lagrar data som tas emot för aktiva användare vid server till server-överföringar och [!DNL DCS]. [!UICONTROL PCS]-data består av enhets-ID, autentiserade profil-ID:n och tillhörande traits.

Se [Komponenter för datainsamling](../reference/system-components/components-data-collection.md).



**Profillänk**

Se [Beskrivning av alternativen för regler för profilsammanslagning](../features/profile-merge-rules/merge-rule-definitions.md).



**Regler för profilsammanslagning**

Med [!UICONTROL Profile Merge Rules] kan du styra vilken typ av data som används i [!DNL Audience Manager] för segmentering.

Se [Beskrivning av alternativen för regler för profilsammanslagning](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realisering**

Den åtgärd med vilken en besökare på er webbplats kvalificerar för ett trait. Ni kan använda verktyget [Visitor Profile Viewer](../features/visitor-profile-viewer.md) för att få information om hur traits realiseras för specifika användare.

## S-T {#s-t}

**Segment**

Ett segment (eller en målgrupp) är en uppsättning användare som delar gemensamma attribut.

Se [Segment: Syfte, sammansättning och regler](../features/segments/segments-purpose.md).



**Segmentadresserbar publik**

I [Addressable Audience](/help/using/features/addressable-audiences.md) representerar det här mätvärdet antalet användare som har tillhört segmentet under rapportens tillbakablicksperiod och som har en aktiv ID-synkronisering på er webbplats. Segment kan innehålla era förstapartsdata samt andra- och tredjepartsdata via traits som registrerats på [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).



**Segmentets totala population**

I [Addressable Audience](/help/using/features/addressable-audiences.md) representerar det här mätvärdet antalet enheter som var medlemmar i ert segment under rapportens tillbakablicksperiod.



**Matchningsfrekvens för segment**

Segmentadresserbar publik ÷ Total segmentpopulation uttryckt i %. Se [Addressable Audience](/help/using/features/addressable-audiences.md).



**Signal**

Signaler är de minsta dataenheterna i [!DNL Audience Manager] och uttrycks som nyckelvärdespar.

Se [Signaler, traits och segment](../reference/signal-trait-segment.md).



**Trait**

Ett trait är en kombination av en eller flera signaler. Se [Signaler, traits och segment](../reference/signal-trait-segment.md).



**Trait-population**

Se [Trait- och segmentpopulationsdata i Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Time-to-Live)**

TTL definierar hur många dagar en kvalificerad besökare stannar i ett trait. TTL anges för traits och inte för segment. Besökare försvinner från ett segment om ett kvalificerande trait inte identifieras före slutet av TTL-intervallet. Läs mer i [Förklaring av segment and TTL (Time-to-Live) för traits](/help/using/features/traits/segment-ttl-explained.md).



## U-V {#u-v}

**UUID**

[!DNL Audience Manager] Unikt användar-ID. Se [Index över ID:n i Audience Manager](../reference/ids-in-aam.md).



**Besökar-ID**

[!DNL Experience Cloud] ID-tjänsten (tidigare besökar-ID) tillhandahåller ett universellt, beständigt ID som identifierar era besökare i alla lösningar i [!DNL Experience Cloud].

Se dokumentationen för [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=sv-SE).

## W-X-Y-Z {#w-z}
