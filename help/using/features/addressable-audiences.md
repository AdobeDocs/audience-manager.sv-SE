---
description: En översikt över funktionen Addressable Audience och användningsexempel.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Adresserbara målgrupper
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

En översikt över [!UICONTROL Addressable Audience] exempel.

## Vad är en [!UICONTROL Addressable Audience]? {#addressable-audience-description}

The [!UICONTROL Addressable Audiences] funktionen visar överlappningen mellan de målgrupper du ser i alla dina egenskaper där [!DNL Audience Manager] samlar in data och det valda målet. Ta en titt på bilden nedan för att få en förståelse för detta koncept. Överlappningen mellan varje cirkel representerar olika typer av adresserbara målgrupper.

![](assets/addressableAudienceVenn.png)


| Mått | Beskrivning |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] för [!UICONTROL Destination] | Antal alla enheter som har interagerat med alla [!DNL Audience Manager] på plattformsnivå under rapportens kontrollperiod och som kan matchas med det [!UICONTROL destination]. <br><br>Det här måttet är användbart eftersom det visar dig: <ul><li>Summans storlek [!UICONTROL addressable audience] att [!DNL Audience Manager] kan nå ut till en viss målgrupp [!UICONTROL destination].</li><li>Så stor är [!DNL Audience Manager] profilpoolen är avsedd för en målplattform och deras målgrupper.</li></ul> |
| [!UICONTROL Customer Total Audience] | Antal enheter som antingen [!UICONTROL rule-based trait] på dina egenskaper eller [!UICONTROL onboarded trait] från dina offlinefiler under backupfönstret. |
| [!UICONTROL Customer Addressable Audience] | Antal överlappande enheter som antingen [!UICONTROL rule-based trait] eller en [!UICONTROL onboarded trait] under kontrollfönstret och de enheter som vi har en ID-synkronisering med den valda [!UICONTROL destination] oberoende av synkroniseringstidpunkten.<br><br>Detta mått representerar enheter som:<ul><li>Har skapat antingen en [!UICONTROL rule-based] eller en [!UICONTROL onboarded trait] under backupfönstret `AND`</li><li>Har en ID-synkronisering med vald [!UICONTROL destination] oberoende av synkroniseringstidpunkten.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ‡ [!UICONTROL Customer Total Audience] uttryckt i procent. |
| [!UICONTROL Total Segment Population] | Antal enheter som är medlemmar i [!UICONTROL segment] under rapportens kontrollperiod. |
| [!UICONTROL Segment Addressable Audience] | Antalet användare som har tillhört [!UICONTROL segment] under rapportens kontrollperiod och ha en aktiv ID-synkronisering på din webbplats. [!UICONTROL Segments] kan inkludera egna data från första part samt data från andra och tredje part via [!UICONTROL traits] förvärvat i [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Tips: När det används med 1-dagars summeringsperiod kan det här måttet hjälpa dig att förstå det aktuella läget för din [!UICONTROL segments]. Det beror på att [!UICONTROL Segment Addressable Audience] mått representerar användare som stannat i en [!UICONTROL segment] under föregående dag. Kombinera detta med det faktum att [!DNL Audience Manager] uppdateringar [!UICONTROL Addressable Audiences] varje dag, med en kombination av detta mätvärde och en uppslagsperiod som ger den senaste ögonblicksbilden av ditt [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ‡ [!UICONTROL Total Segment Population] uttryckt i procent. |

## [!UICONTROL Addressable Audiences] Gränssnitt {#addressable-audience-interface}

The [!UICONTROL Addressable Audience] funktionen gör detta abstrakta koncept till kvantifierbara data. I [!DNL Audience Manager], visar den här funktionen målgruppen överlappning med datavisualiseringar som ger snabböverskådlig information tillsammans med numeriska data i tabellform.

[!UICONTROL Addressable Audiences] finns i **[!UICONTROL Audience Data > Destinations]**. Välj **[!UICONTROL Integrated Platforms > Device-Based]** för att se adresserbara målgruppsmått.

![](assets/addressable-audiences-landing.png)

De tre mätvärdena du kan se på [!UICONTROL Addressable Audiences] landningssidan representerar:

| Mått | Beskrivning |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Det här måttet representerar [!UICONTROL Customer Addressable Audience] (beskrivs i tabellen ovan) *de senaste 30 dagarna.* |
| **[!UICONTROL Match Rate]** | Det här måttet representerar [!UICONTROL Addressable Audience Match Rate] (beskrivs i tabellen ovan) *de senaste 30 dagarna*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Antal alla enheter som har interagerat med alla [!DNL Audience Manager] på plattformsnivå under rapportens kontrollperiod och som kan matchas med detta [!UICONTROL destination]. Se [Plattformsnivåstatistik](/help/using/features/addressable-audiences.md#platform-level-metrics) för mer information. |

Klicka på namnet på en [!UICONTROL server-to-server destination] för att visa era adresserbara målgruppsdata. Obs! Den här funktionen returnerar data för [!UICONTROL server-to-server destinations] och åtkomst kräver administratörsbehörighet.

![](assets/addressableAudiences.png)

Genom att granska dessa data kan du

* **Prognos och planering:** [!UICONTROL Segment Addressable Audience] data ger er större detaljrikedom i de segment ni planerar att skicka till en målgrupp för målgruppsanpassning och aktivering.

* **Prestandagranskningar:** The [!UICONTROL Addressable Audiences] är också ett felsökningsverktyg. Ni kan granska kampanjens resultat, förstå kampanjens räckvidd och dubbelkontrollera med partners för målinriktning/aktivering om ni inte ser de resultat ni förväntar er.

### Prospektera med data från tredje part och effekter för matchningsfrekvenser

Innan man köper data från tredje part för att värva målgrupper kan man validera överlappningen med andra dataleverantörer. Detta kan hjälpa er att fatta ett välgrundat beslut innan ni köper nya data. ID-synkroniseringen för inköpt information från tredje part är inte bara beroende av att dina data överlappar varandra, utan även av tredjepartsleverantörernas fotavtryck med alla andra [!DNL Audience Manager] kunder. Dina [!DNL Adobe] kan hjälpa er att identifiera ytterligare relevanta datakällor för att optimera prospekteringskampanjer.

### Mobilanvändare och matchningsfrekvenser

Det finns luckor när du försöker ansluta [!DNL Safari] eller mobilappsanvändare där det inte finns några tredjepartsleverantörer [!DNL cookies] presenter. Det gör det svårt att synkronisera användare med vissa partners eftersom endast de [!DNL Adobe] ID:n för synkroniserad tredje part [!DNL cookies] finns i medieleveransloggarna. Det här är en anledning till varför du kanske ser [låg matchningsfrekvens](../features/addressable-audiences.md#low-match-rates) för [!UICONTROL destinations].

## Datumintervall i [!UICONTROL Addressable Audiences] och [!UICONTROL Destinations] {#date-ranges}

Läs avsnitten nedan om tillgängliga datumintervall och hur data lagras utifrån varje intervall i rapporter för [!UICONTROL Addressable Audience] eller [!UICONTROL Destination].

## Tillgängliga datumintervall och tidszoner {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Rapporter om [!UICONTROL Addressable Audiences] och [Destinationer](../features/destinations/destinations.md) använder samma datumintervall. Alternativen för datumintervall är:

* [!UICONTROL Last 1 Day] (Det här intervallet går från midnatt till midnatt under föregående 24-timmarsperiod. Det är inte ett reellt mått eller ett mått för aktuell tid.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alla datum- och datumintervall anges i [!DNL UTC] tidszon. Se [Tidszoner i Audience Manager](../reference/aam-time-zones.md).

## Data i datumintervallintervall {#date-range-intervals}

The [!UICONTROL Addressable Audience] och [!UICONTROL Destination] mätvärden returnerar ett antal unika användare för det valda tidsintervallet. En besökare räknas till exempel bara en gång, även om de kommer till platsen flera gånger. Det första besöket är det unika besöket och registreras. De följande besöken är återkommande besök och räknas inte eftersom de inte är unika.

Datumintervall innehåller data för det valda tidsintervallet eller äldre. Och data försvinner från varje rapportintervall när tiden går. Låt oss anta att du ser 2 besökare efter att du har valt [!UICONTROL Last 30 Days] alternativ. I rapporterna kan följande besökare:

* *Kommer att* som ingår i resultaten som returneras av de längre tidsintervallen (60 dagar, 90 dagar och Livstid).
* *Kommer inte att* som ingår i de kortare intervall som föregår [!UICONTROL Last 30 Day] (Aktuell, 7 dagar och 14 dagar).

Och på dag 31 visas de här besökarna bara på 60 dagar, 90 dagar och [!UICONTROL Lifetime] resultat. De har åldrats utanför 30-dagarsintervallet. Besökarna kommer inte att åldras [!UICONTROL Lifetime] intervall.

## [!UICONTROL Addressable Audiences] Mått {#addressable-audience-metrics}

I det här avsnittet beskrivs de typer av mätvärden som tillhandahålls av [!UICONTROL Addressable Audiences].

### Kundnivåstatistik {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Dessa värden returnerar data för egenskaper som realiseras när besökare kommer till er webbplats eller när ni skickar inkommande datafiler till [!DNL Audience Manager]. Dessa mått ger en heltäckande bild av målgruppens storlek för ditt konto.

| Mått | Beskrivning |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Antal överlappande enheter som antingen [!UICONTROL rule-based trait] eller en [!UICONTROL onboarded trait] under kontrollfönstret och de enheter som vi har en ID-synkronisering med det valda målet, oavsett synkroniseringstidpunkten.<br><br>Detta mått representerar enheter som:<ul><li>Har skapat antingen en [!UICONTROL rule-based] eller en [!UICONTROL onboarded trait] under backupfönstret `AND`</li><li>Har en ID-synkronisering med vald [!UICONTROL destination] oberoende av synkroniseringstidpunkten.</li></ul> |
| [!UICONTROL Customer Total Audience] | Antal enheter som antingen [!UICONTROL rule-based trait] på dina egenskaper eller [!UICONTROL onboarded trait] från dina offlinefiler under backupfönstret. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] ‡ [!UICONTROL Customer Total Audience] uttryckt i procent. |

### Matchningsmått på segmentnivå {#segment-level-metrics}

Dessa mått returnerar data på [!UICONTROL segment] medlemskap. De ger en mer detaljerad och korrekt bild av målgruppens storlek för var och en av era [!UICONTROL segments].

>[!NOTE]
>
>Det sätt som fönstret för att titta tillbaka tillämpas på [!UICONTROL segment] nivån skiljer sig från den på kundnivå. Besökarna kan komma till webbplatsen och förverkliga [!UICONTROL trait] För 10 dagar sedan kunde de kvalificera sig för en [!UICONTROL segment] sedan dess och släppt ut ur [!UICONTROL segment] För 2 dagar sedan. När 7-dagars summering används räknas de här besökarna på [!UICONTROL segment] men inte på kundnivå.

| Mått | Beskrivning |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Antalet användare som har tillhört [!UICONTROL segment] under rapportens kontrollperiod och ha en aktiv ID-synkronisering på din webbplats. Segmenten kan innehålla egna data från första part samt data från andra part och tredje part via [!UICONTROL traits] förvärvat i [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Tips: När det används med 1-dagars summeringsperiod kan det här måttet hjälpa dig att förstå det aktuella läget för din [!UICONTROL segments]. Det beror på att [!UICONTROL Segment Addressable Audience] mått representerar användare som stannat i en [!UICONTROL segment] under föregående dag. Kombinera detta med det faktum att [!DNL Audience Manager] uppdateringar [!UICONTROL Addressable Audiences] varje dag, med en kombination av detta mätvärde och en uppslagsperiod som ger den senaste ögonblicksbilden av ditt [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Antal enheter som är medlemmar i [!UICONTROL segment] under rapportens kontrollperiod. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] ‡ [!UICONTROL Total Segment Population] uttryckt i procent. |

### Plattformsnivåstatistik {#platform-level-metrics}

Det här måttet returnerar data om aktiviteter som samlats in över alla [!DNL Audience Manager] kunder. De kan ge en bredare bild av kundens målgrupp jämfört med de samlade [!DNL Audience Manager] kunder.

| Mått | Beskrivning |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Antal alla enheter som har interagerat med alla [!DNL Audience Manager] på plattformsnivå under rapportens kontrollperiod och som kan matchas med det [!UICONTROL destination]. <br><br>Det här måttet är användbart eftersom det visar dig:<ul><li>Storleken på [!UICONTROL total addressable audience] att [!DNL Audience Manager] kan nå ett visst mål.</li><li>Så stor är [!DNL Audience Manager] profilpoolen är avsedd för en målplattform och deras målgrupper.</li></ul> |

## Jämför [!UICONTROL Customer] och [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Du borde inte jämföra [!UICONTROL Customer Addressable Audience] och [!UICONTROL Segment Addressable Audience] för att avgöra om den ena är större än den andra. Dessa är separata, olika och oberoende mätvärden. Såsom beskrivs i definitionerna ovan, härleds vart och ett av dessa från olika datauppsättningar. Därför bör du undvika att dra några slutsatser om ett mätvärde är större än det andra. Allt du kan säga när du jämför dessa är att:

* [!UICONTROL Customer Addressable Audiences] baseras på [!UICONTROL trait] realiseringar *för era egna data från första part*. Detta ger en bred, heltäckande bild av er integrering med en datapartner.

* [!UICONTROL Segment Addressable Audiences] baseras på segmentkvalifikationer *för era egna data från första part, plus data från andra och tredje part*. Det här måttet ger en mer detaljerad och korrekt bild av [!UICONTROL addressable audiences] på en målplattform.

## Orsaker till låg matchningsfrekvens för [!UICONTROL Addressable Audiences] {#low-match-rates}

Vanliga element som ligger bakom låg [!UICONTROL Addressable Audience] matchningsfrekvenser eller avvikelser i rapporterade tal.

| Orsak | Beskrivning |
|---|---|
| Mobiltrafik | Mest [!UICONTROL server-to-server] integreringar är beroende av synkroniseringsprocesser som hanteras av tredje part [!DNL cookies]. Mobilmiljöer använder dock inte externa leverantörer [!DNL cookies]. Detta resulterar i att [!UICONTROL Addressable Audiences] siffror kan verka låga jämfört med [!UICONTROL segment] storlek. <br><br>Från och med januari 2018 kan du aktivera mobila målgrupper i samma [!DNL Google] och [!DNL Adobe Advertising Cloud] destinationer som konfigurerats för [!UICONTROL cookie-based] målgrupper. Detta innebär att du kan skicka [!UICONTROL segments] med kombinerad [!DNL cookie] och ditt mobil-ID-medlemskap [!DNL Google] och [!DNL Advertising Cloud] destinationer, tänk på att [!UICONTROL Addressable Audiences] bara visa överlappningen mellan [!DNL cookie] ID:n och mål. [!DNL Audience Manager] skickar 100 % av de mobila målgrupperna till [!UICONTROL destinations], men mobilmålgrupperna mäts inte av [!UICONTROL Addressable Audience] mätvärden. <br><br>**Anteckning**: Ta till exempel en [!UICONTROL segment] med en befolkning på 1 000 000. Om du mappar detta [!UICONTROL segment] till [!DNL Google] eller [!DNL Adobe Advertising Cloud] mål, du kanske ser ett [!UICONTROL Addressable Audience] 700 000 enheter och en [!UICONTROL Match Rate] av 70 %. Medlemskapet på 700 000 består av [!DNL cookie] ID:n som har ett ID-synkroniserat med [!UICONTROL destination]. Dina [!UICONTROL Addressable Audience] kan faktiskt vara mycket högre, eftersom adresserbara mobil-ID:n inte visas i det här måttet. |
| [!DNL Safari] Trafik | [!DNL Safari] blockerar tredje part [!DNL cookies]. Detta förhindrar [!DNL Audience Manager] från synkronisera ID:n med [!UICONTROL destination]. Med introduktionen av [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/)kan du förvänta dig [!UICONTROL addressable audiences] inte inkludera [!DNL Safari] -användare. |
| Spårade mediaexponeringar | På grund av de bästa metoderna för annonsservrar görs inga ID-synkroniseringar i annonstaggar. Kunder som gör en stor mängd annonsering utanför webbplatsen synkroniserar inte användare med tredjepartsintegreringar i dessa miljöer. Dessutom kan en stor mängd insamlade mediefunktionsdata minska [!UICONTROL addressable audience] tal. |

## Felsökning med [!UICONTROL Addressable Audiences] {#troubleshooting}

Förutom att använda matchningsfrekvenser kan du även använda [!UICONTROL Addressable Audiences] som ett felsökningsverktyg.

Anta att du skickar ett segment till en [!UICONTROL destination] och [!UICONTROL destination] visar låga rapportnummer. Kontrollerar [!UICONTROL Addressable Audience] resultaten visar om detta är ett tekniskt problem eller bara ett fall med låg matchningsfrekvens. En låg matchningsfrekvens visar din [!UICONTROL destination] är inte så bra för de valda segmenten. En skillnad i [!UICONTROL total addressable audience] tal mellan [!DNL Audience Manager] och [!UICONTROL destination] anger ett integrerings-, synkroniserings- eller annat tekniskt problem. Kontakta i så fall din kontoansvarige.
