---
description: På Marketplace går datainköpare till forskning och prenumererar på offentliga och privata dataflöden. Följ de här stegen för att prenumerera på en offentlig datafeed.
seo-description: På Marketplace går datainköpare till forskning och prenumererar på offentliga och privata dataflöden. Följ de här stegen för att prenumerera på en offentlig datafeed.
seo-title: Hantera prenumerationer på dataflöden
solution: Audience Manager
title: Hantera prenumerationer på dataflöden
topic: DIL API
uuid: 7305adb6-cbb8-4430-8204-2243095c0ba5
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '2186'
ht-degree: 1%

---


# Hantera prenumerationer på dataflöden {#manage-data-feed-subscriptions}

I [!UICONTROL Marketplace] går datainköpare till forskning och prenumererar på offentliga och privata dataflöden. Följ de här stegen för att prenumerera på en offentlig datafeed.

## Prenumerera på en offentlig datafeed {#subscript-public-data-feed}

I [!UICONTROL Marketplace] går datainköpare till forskning och prenumererar på offentliga och privata dataflöden. Följ de här stegen för att prenumerera på en offentlig datafeed.

<!-- t_subscribe_feed.xml -->

Så här prenumererar du på en allmän datafeed:

1. Gå till **[!UICONTROL Audience Marketplace > Marketplace]**. Använd sökfunktionen eller bläddra igenom listan för att hitta en datafeed.

   ![prenumerera](assets/subscribe1.png)

1. Klicka på namnet på den datafeed som du vill använda. Sidan [planinformation](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) öppnas för vald feed.

   ![plan-details](assets/plan-details.png)

1. Välj ett användningsfall i prenumerationstabellen och:
   * Flytta reglaget **[!UICONTROL Subscription]** till **[!UICONTROL On]**.
   * Klicka på **[!UICONTROL Review & Subscribe]**. Då öppnas fönstret [!UICONTROL Terms and Conditions].

   ![prenumerera](assets/subscribe3.png)

1. I fönstret [!UICONTROL Terms and Conditions]:

   * **Viktigt:** Låt  **[!UICONTROL ID sync]** kryssrutan vara markerad. Den här inställningen hjälper till att förbättra matchningsfrekvensen hos din DataProvider.
   * Markera rutan Villkor och klicka på **[!UICONTROL Accept]** för att slutföra prenumerationsprocessen.

   ![prenumerera](assets/subscribe4.png)

### Nästa steg

När du har prenumererat på en datafeed:

* Verifiera prenumerationen genom att kontrollera din [!UICONTROL Traits]-mapp. Se [Lagring för prenumererade datafeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee).

* Granska fakturerings- och betalningsdokumentationen. Se de relaterade länkarna nedan.

### Bästa praxis {#best-practices}

Här följer en uppsättning metodtips som du bör följa när du arbetar med [!UICONTROL Audience Marketplace]:

När du utforskar nya datauppsättningar från tredje part och från andra leverantörer via [!UICONTROL Audience Marketplace], rekommenderar vi att du aktiverar dataflöden för [!UICONTROL Segments & Overlap]. På så sätt kan användarna utforska data genom att bygga segment för att utvärdera målgruppens storlek och köra överlappningsrapporter för att få inledande målgruppsinsikter. De flesta dataleverantörer erbjuder denna användning kostnadsfritt, så du kan utföra analysen utan extra kostnad.

När du kör överlappningsrapporter bör du följa dessa metodtips för att vara säker på att du får användbara resultat.

1. Se till att de överlappande datauppsättningarna är lika vad gäller datatyp och insamlingsmetoder, till exempel:
   * Besöksgeografi
   * Cookie jämfört med Mobile ID
   * Fönstret Lookback
   * Offline- kontra onlineaktivitet
   * Den frekvens med vilken dataleverantören uppdaterar data

1. Överlappningen kan växa något över tiden, så se till att du tillåter upp till 30 dagar att skicka innan du kör överlappningsrapporter så att data kan synkroniseras.
1. Överlappningen kan öka om ni använder data från en dataleverantör i flera marknadsföringskampanjer.
och initiativ. Detta ger fler möjligheter för användare från de två datauppsättningarna att synkronisera.
1. Det finns ingen garanti för att datauppsättningarna kommer att överlappa varandra. För att en överlappning ska vara giltig måste en användare från kundens datauppsättning kopplas till data
providerdatauppsättning under rapportens tidsram. Om kundens mediedata inte delades ut till användarna i dataleverantörens datauppsättning kommer det aldrig att finnas någon överlappning.
1. Tänk inte på låg överlappning som något dåligt. Utnyttja den låga överlappningen för potentiella kunder och engagera nya användare.

## Prenumerera på en privat datafeed {#subscript-private-data-feed}

Köpare prenumererar på privata dataflöden och planer i **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_private_feed.xml -->

>[!TIP]
>
>Ibland kan dataleverantörer erbjuda en rabatt på ett privat dataflöde. Du kanske vill fråga om en eventuell rabatt när du skickar in din prenumerationsansökan.

Så här prenumererar du på en privat datafeed:

1. Klicka på dataflödets namn i [!UICONTROL Marketplace].
1. Klicka på **[!UICONTROL Request Access]**. Då öppnas dialogrutan för förfrågan.
1. Skriv en anteckning som uttrycker ditt intresse för dataflödet i dialogrutan för begäran och klicka på **[!UICONTROL Send]**. Säljaren granskar ditt meddelande och godkänner eller avvisar din förfrågan. I väntan på godkännande visas&quot;Begärt&quot; i listan [!UICONTROL Marketplace] för den datafeeden.

   * **[!UICONTROL Request approved]**: Statusen i  [!UICONTROL Marketplace] listan ändras till &quot;Åtkomst beviljad&quot; så får du ett automatiskt meddelande. Nu kan du prenumerera på feeden. Mer information finns i [Prenumerera på en offentlig datafeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed).
   * **[!UICONTROL Request denied]**: Texten &quot;Begärd&quot; tas bort från  [!UICONTROL Marketplace] listan för feeden. Du kan försöka prenumerera igen eller välja en annan feed.

## Rabatter på dataflöden för köpare {#buyer-discount}

I [!UICONTROL Audience Marketplace] kan leverantörerna erbjuda köpare en rabatt på det publicerade priset för en [!DNL CPM]-dataström eller en datafeed med schablonsats. Rabattbelopp är dock inte synliga för köpare i [!DNL Marketplace]-feedlistan. Men du kan också be om en rabatt när du prenumererar på ett privat dataflöde eller när du begär mer information om ett visst flöde.

## Begär rabatt {#request-discount}

<!-- marketplace-buyer-discounts.xml -->

<table id="table_3C6E58F593BA48EC89ACBD9A26E4E74F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Köparstatus </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Aktuella prenumeranter</b> </p> </td> 
   <td colname="col2"> <p>Om du redan prenumererar på en privat datafeed och vill begära en rabatt: </p> 
    <ol id="ol_A58D419EBB9349E9B1225202535130F6"> 
     <li id="li_D0DDC8AC6E9C4675AA4630D63FE8F071"> <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe"> Avbeställ </a> beställningen. </li> 
     <li id="li_05A5379F2A944FB28AB39C196DDE3A1D">Kontakta DataProvider och begär ett rabatterat pris. </li> 
     <li id="li_B1B5AA6F6CC64512A02D5E8861A5F266">Om leverantören ger dig rabatt återprenumererar du på feeden den 1<sup>st</sup> dagen i nästa månad. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Nya prenumeranter på privata dataflöden</b> </p> </td> 
   <td colname="col2"> <p>Be om rabatt i din prenumerationsansökan. Se <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed"> Prenumerera på en privat datafeed</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Potentiella prenumeranter</b> </p> </td> 
   <td colname="col2"> <p>En <a href="../../../features/audience-marketplace/marketplace-private-feeds.md"> potentiell prenumerant</a> är en datamottagare som har begärt åtkomst till en privat datafeed, som har fått säljarens godkännande, men som inte har prenumererat på denna feed. Så här begär du en rabatt som potentiell prenumerant: </p> 
    <ol id="ol_9CECDA92E7894B20AC8A777D78962188"> 
     <li id="li_618B64160CF24549AFCA73E006DCA35A">Gå till <b><span class="uicontrol"> Audience Marketplace &gt; Marketplace</span></b>. </li> 
     <li id="li_FE52A06B30FC4858B48AF81954365FE9">Klicka på namnet på den feed du har godkänts för. </li> 
     <li id="li_763C050AC9464BE380D00F6085B6E540">Klicka på <b><span class="uicontrol"> Begär mer information</span></b>. Be om rabatt i din informationsförfrågan till säljaren. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Granska rabatterade feeds {#review-discounted-feeds}

Så här granskar du dina rabatterade feeds:

1. Gå till **[!UICONTROL Audience Marketplace > Marketplace]**.
1. Klicka på namnet på en feed som du redan prenumererar på.
1. Titta på kolumnerna [!UICONTROL Price] och [!UICONTROL Your Price] i tabellen [!UICONTROL Plan Details]. Om fodret diskonteras:

   * Det ursprungliga priset markeras med en röd linje.
   * Avgiften i kolumnen [!UICONTROL Your Price] är lägre än avgiften i kolumnen [!UICONTROL Price].

I exemplet får köparen 10 % rabatt på [!UICONTROL Segments and Overlap]-planen i **[!UICONTROL Software Audience Feed]**.

![](assets/buyer-discount.png)

## Söka efter data för prenumerationsflöden {#find-subscribed-data-fee}

Data (egenskaper) för dina dataflöden visas i sina egna mappar för lagring av egenskaper. Gå till **[!UICONTROL Audience Data > Traits]** och expandera mappen **[!UICONTROL 3rd-Party Data]** för att visa och arbeta med egenskaperna i dina prenumererade feeds. Leta efter undermappen som har namngivits efter din DataProvider. Dessa innehåller mappar som namnges efter den enskilda datafeeden och listegenskaper som matningen ger.

<!-- marketplace-feed-storage.xml -->

![](assets/subscribe5.png)

## Avbeställ en datafeed {#unsubscribe}

Datainköpare avbeställer dataflöden och planer i **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_unsubscribe_feed.xml -->

Så här avslutar du en prenumeration på en datafeed:

1. Klicka på dataflödets namn i [!UICONTROL Marketplace].
1. I avsnittet [!UICONTROL Use Case] letar du reda på den plan du vill använda och flyttar reglaget **[!UICONTROL Subscription]** till **[!UICONTROL Off]**.

## Inaktivering av datafeed: Varför det händer och hur man svarar {#data-feed-deactivation-reasons}

I [!UICONTROL Audience Marketplace] kan dataleverantörer återkalla åtkomsten till dina prenumererade dataflöden. Bli inte orolig om det här händer dig. Vi har det du behöver. Granska det här avsnittet för processer och procedurer för inaktivering av dataflöden.

## Vanliga orsaker till inaktivering av datamatning {#reasons-for-deactivation}

<!-- marketplace-subscriber-deactivated.xml -->

Det kan vara förvirrande eller till och med upprörande om en feed du prenumererar på är avstängd. Dataleverantörer kan dock inaktivera en datafeed av olika anledningar. Några vanliga orsaker:

* **Fakturering:** Dataleverantörer inaktiverar ett flöde om du konsekvent är försenad med avgiftsbetalningar eller om du inte betalar dina avgifter.
* **Feed Updates:** Data providers need to deactivate feeds when they update their feed taxonomy or cost structure.
* **Inaktiva köpare:** Dataleverantörer förbehåller sig rätten att inaktivera feeds om prenumeranterna inte visar några utgifter under en längre period.
* **Inaktiva säljare:** Dataleverantörer som lämnar  [!UICONTROL Audience Marketplace] kommer att inaktivera och ta bort alla sina dataflöden.

>[!TIP]
>
>Kontakta din dataleverantör direkt om du tror att en datafeed har inaktiverats av misstag. Din [!DNL Adobe]-konsult kan hjälpa dig med kontaktinformation eller ytterligare support.

## E-post för inaktivering {#deactivation-email}

När en dataleverantör inaktiverar en av dina datafeeds skickar [!DNL Audience Manager] ett e-postmeddelande till de användare i företaget som har [!UICONTROL Administrator] behörighet. Ibland kan e-postfilter klassificera det här meddelandet som skräppost. Därför kanske du saknar det här viktiga meddelandet. Det här e-postmeddelandet innehåller följande element som kan hjälpa dig att identifiera inaktiveringsmeddelandet:

* **Från:** E-postmeddelandet om inaktivering kommer från  `aam-noreply@adobe.com`. Proffstips: Svara inte på det här e-postmeddelandet.

* **Ärenderad:** Prenumerationen på  *dataflödets namn* avbryts.

* **Bifogade filer:** E-postmeddelandet innehåller en bifogad fil med namnet &quot;  `list-of-affected-entities-by-feed-revocation.csv`.&quot; Det är ett invecklat sätt att säga att bilagan innehåller alla egenskaper som ingår i det avbrutna flödet. Som datainköpare bör du granska den här bilagan. Det hjälper dig att hitta och ta bort inaktiverade egenskaper från dina segment och [algoritmiska modeller](../../../features/algorithmic-models/understanding-models.md).

## Inaktiverad traits-lista {#deactivation-trait-list}

Listan som medföljer ett e-postmeddelande om inaktivering innehåller fälten som visas nedan.

<table id="table_5C3800F9D8AA43EFAB4690959A721F63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Datafeed-ID</span></b> </p> </td> 
   <td colname="col2"> <p>ID för den inaktiverade datafeeden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Namn på datafeed</span></b> </p> </td> 
   <td colname="col2"> <p>Namnet på den inaktiverade datafeeden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Trait SID</span></b> </p> </td> 
   <td colname="col2"> <p>Inaktiverade trait-ID:n. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Trait Name</span></b> </p> </td> 
   <td colname="col2"> <p>Inaktiverade trait-namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Segment-SID</span></b> </p> </td> 
   <td colname="col2"> <p>ID för segmentet som innehåller inaktiverade egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Segmentnamn</span></b> </p> </td> 
   <td colname="col2"> <p>Namnet på det segment som innehåller inaktiverade egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID för Algo-modell</span></b> </p> </td> 
   <td colname="col2"> <p>ID för den algoritmiska modellen som innehåller inaktiverade egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Namn på Algo-modell</span></b> </p> </td> 
   <td colname="col2"> <p>Namnen på algoritmiska modeller som innehåller inaktiverade egenskaper. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ta bort inaktiverade egenskaper {#remove-deactivated-traits}

Som datainköpare ansvarar du för att ta bort egenskaperna i ett avbrutet flöde från alla aktiva/pågående eller inaktiva segment. Borttagningsalternativen är:

* Massborttagning med [REST API:er](../../../api/rest-api-main/rest-api-main.md) eller [grupphanteringsverktygen](../../../reference/bulk-management-tools/bulk-management-intro.md).

* Sök manuellt efter påverkade segment och ta bort inaktiverade egenskaper med [!UICONTROL Segment Builder]. Se [Ta bort egenskaper från ett segment](../../../features/segments/segment-builder.md#segment-builder-controls-traits).

>[!NOTE]
>
>Att ta bort egenskaper från aktiva algoritmiska modeller eller mål påverkar noggrannheten för skala och målinriktning. Försök ersätta återkallade egenskaper med nya, aktiva egenskaper om det är möjligt.

[Avbeställ den inaktiverade ](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe) datafeedbacken när du har tagit bort alla återkallade egenskaper från ditt konto. Om detta är en tillfällig inaktivering kan du återprenumerera när dataprovidern har slutfört de ändringar som krävs och återaktiverar flödet. Precis som med de flesta andra saker kan bra kommunikation med dina partner (DataProvider och [!DNL Adobe]) hjälpa dig att arbeta med den här processen.

## Sidan med avtalsinformation i Audience Marketplace {#marketplace-buyer-details}

När du klickar på namnet på en dataplan i [!UICONTROL Marketplace] innehåller [!DNL Audience Manager] information som kan hjälpa dig att göra välgrundade val när det gäller att prenumerera på en datafeed.

<!-- marketplace-buyer-details.xml -->

![](assets/plan-details-numbered.png)

Den här sidan ger dig följande information:

1. **Grundläggande planinformation**. Detta inkluderar foderinformation som:
   * Namn på datafeed. Som visas ovan är namnet på denna feed&quot;Exempeldatafeed&quot;.
   * Dataleverantörens namn.
   * ID för datafeed;
   * Beskrivning;
   * Antal egenskaper i flödet.

1. Knappar för planinformation.
   * Klicka på **[!UICONTROL Explore All Traits]** om du vill se information om alla egenskaper i den valda datafeeden.
   * Klicka på **[!UICONTROL Request More Details]** för att ställa frågor till dataleverantören om den valda datafeeden eller för att begära en rabatt. Den här funktionen skickar dina kommentarer och frågor direkt till DataProvider.

1. Data Feed Report Metrics. I Venndiagrammet (och relaterade mätvärden) visas hur ni ser överlappande data under de senaste 30 dagarna. Se [Marketplace: Om](marketplace-data-buyers.md#about-marketplace) för mer information.
   * **[!UICONTROL 30 Day Overlapped Uniques]**: Antalet unika användare på ditt konto som överlappar användarna på leverantörens konto. En definition av unika användare finns i AAM UUID i [index för ID:n i Audience Manager](/help/using/reference/ids-in-aam.md).
   * **[!UICONTROL 30 Day Provider Unique Users]**: Antalet unika användare som kommer från leverantörens konto.
   * **[!UICONTROL Your Unique Users]**: Antalet unika användare som kommer från ditt konto.

1. **[!UICONTROL Plan Details]** Tabell. I den här tabellen visas de användningsfall som du kan prenumerera på datafeeden för samt dess prismodell. Se [Förstå användningsexempel för dataflöden](#use-cases).

1. Planera åtgärdsknappar.
   * Klicka på **[!UICONTROL Cancel]** om du vill lämna sidan utan att göra några ändringar.
   * Klicka på **[!UICONTROL Review & Subscribe]** om du vill prenumerera på en datafeed. Den här knappen är nedtonad tills du växlar till [!UICONTROL Subscription] för att växla till [!UICONTROL On]. Se även [Prenumerera på en offentlig datafeed](#subscript-public-data-feed) och [Prenumerera på en privat datafeed](#subscript-private-data-feed).

## Användningsexempel för datafeed {#use-cases}

Som [!UICONTROL Audience Marketplace]-datainköpare kan du köpa data för överlappning, modellering och aktiveringsanvändning. Varje användningsfall är utformat för ett specifikt ändamål och begränsar vad du kan göra med informationen. Dessa fallbeskrivningar kan hjälpa er att fatta rätt beslut om vilken typ av dataplan ni ska köpa.

## Gör jämförelser med segment och överlappningsplaner {#comparisons}

<!-- c_use_cases_for_buyers.xml -->

### Segment och överlappning

I det här exemplet kan du jämföra dina egenskaper med leverantörens egenskaper i en [trait-to-trait-överlappande rapport.](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) Du kan också skapa eller lägga till leverantörsegenskaper i ett segment och göra ytterligare jämförelser med  [segment-till-](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) trait- och  [segment-till-](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) segmentrapporter. Överlappningsjämförelser kan hjälpa dig:

* **Nå fler:** Låg överlappning innebär att dina egenskaper innehåller användare du inte har sett tidigare. Du kanske vill att dessa egenskaper ska försöka nå nya användare.
* **Förbättra befintliga målgrupper:** Hög överlappning innebär att dina egenskaper liknar de som ägs av dataleverantören. Ni vill kanske att dessa egenskaper ska bidra till att förbättra en redan utvecklad målgrupp.

### Algoritmiska modeller

Med det här användningsexemplet kan du utvärdera leverantörens egenskaper mot dina egenskaper med [algoritmisk modellering](../../../features/algorithmic-models/understanding-models.md#understanding-models). I vårt algoritmiska modelleringssystem används till exempel en av dina egenskaper som utgångspunkt för jämförelse med en leverantörsegenskap. När modellen körs kan den visa om målgrupper i leverantörsledet delar konverteringsattribut som liknar dina egenskaper.

### Aktivering

Med det här användningsexemplet kan du skicka data till ett [mål](../../../features/destinations/destinations.md). I [!DNL Audience Manager] är målet ett tredjepartssystem (annonsserver, [!DNL DSP], [!DNL DMP], Exchange osv.) som du vill dela data med. Med ett [!UICONTROL Activation]-användningsfall kan du dock inte köra överlappningsrapporter eller testa data i en algoritmisk modell.

>[!MORELIKETHIS]
>
>* [Fakturering och Impression-allokering för CPM-dataflöden](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Fakturering och Impression-allokering för statiska avgiftsdatafeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Rapportera CPM-användning](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
>* [Prenumerera på en offentlig datafeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)
>* [Rabatter för datainköpare](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
>* [Marketplace: Om](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)

