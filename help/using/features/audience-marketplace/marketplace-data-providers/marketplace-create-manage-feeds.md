---
description: En datafeed kräver ett namn, en beskrivning, en datakälla och en plantyp. Feeds inaktiveras tills du sparar och aktiverar feeden. Konfigurera offentliga eller privata dataflöden i Audience Marketplace > Mina delade data. Endast tillgängligt för dataförsäljare.
seo-description: En datafeed kräver ett namn, en beskrivning, en datakälla och en plantyp. Feeds inaktiveras tills du sparar och aktiverar feeden. Konfigurera offentliga eller privata dataflöden i Audience Marketplace > Mina delade data. Endast tillgängligt för dataförsäljare.
seo-title: Skapa, prissätta och hantera dataflöden
solution: Audience Manager
title: Skapa, prissätta och hantera dataflöden
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 1%

---

# Skapa, prissätta och hantera dataflöden {#create-price-and-manage-data-feeds}

## Skapa en offentlig eller privat datafeed {#create-public-private-data-feed}

En datafeed kräver ett namn, en beskrivning, en datakälla och en plantyp. Feeds inaktiveras tills du sparar och aktiverar feeden. Konfigurera offentliga eller privata dataflöden i **[!UICONTROL Audience Marketplace > My Shared Data]**. Endast tillgängligt för dataförsäljare.

<!-- t_data_feed.xml -->

Du måste ha administratörsbehörighet för att skapa en offentlig eller privat datafeed.
Så här skapar du en datafeed:

1. Klicka på **[!UICONTROL New Data Feed]**.
1. Namnge datafeeden. Datainköpare kan söka efter din feed baserat på namnet.
1. Ge en kort beskrivning (högst 255 tecken).

   En bra beskrivning bör beskriva ditt foder korrekt. Du kan till exempel inkludera text för marknadsföringskategorier, demografiska data och geografisk täckning (t.ex. [!DNL US] eller Nordamerika). Beskrivningstexten är sökbar och hjälper köpare att hitta eller utvärdera din feed. En bra beskrivning är en viktig del av att locka abonnenter till dataflödet.
1. Välj en datakälla bland **[!UICONTROL Data Source]**-alternativen. Dataflöden är begränsade till en enda datakälla. Du kan inte tilldela flera datakällor till samma datafeed.

   >[!IMPORTANT]
   >
   >Alla nuvarande och framtida egenskaper som tillhör den här datakällan delas med era datainköpare som en del av denna feed.

1. I [!UICONTROL Plan Types] markerar du de alternativ du vill använda och klickar på **[!UICONTROL Add Plan]**.

   Feeds kan innehålla flera planer. Planer kan innehålla flera användningsfall. Mer information finns i [Planera typer för dataflöden](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Klicka på **[!UICONTROL Save]** om du vill spara din datafeed *utan att* aktivera den.
1. Så här sparar och aktiverar du en datafeed:
   1. Flytta reglaget **[!UICONTROL Availability]** till **[!UICONTROL Active]**.
   1. Klicka på **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Det går inte att ta bort sparade och aktiverade dataflöden.
   >* Köpare ser endast aktiva feeds.


### Valfritt: Skapa en privat datafeed

Flytta reglaget till i [!UICONTROL Settings]-avsnittet:

* **[!UICONTROL Private]** och  **[!UICONTROL Branded]**: Köparens  [!UICONTROL Marketplace] lista visar säljarens namn i leverantörskolumnen och alla andra data är dolda.

* **[!UICONTROL Private]** och  **[!UICONTROL Unbranded]**: Köparens  [!UICONTROL Marketplace] lista visar endast dataflödets namn och beskrivning. DataProvider-namnet visas som [!UICONTROL Private Seller].

För att se hur en privat feed ser ut för köpare, se avsnittet köpare i [Privata datafeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

## Inaktivera en abonnents datafeed {#deactivate-data-feed}

Som [!UICONTROL Audience Marketplace]-dataleverantör kan du återkalla köparåtkomst till en prenumererad datafeed. Du kan ta bort en köpare från ett flöde av orsaker som försenad betalning/utebliven betalning av avgifter eller om de använder felaktiga uppgifter.

<!-- marketplace-deactiva4te-subscribers.xml -->

Så här återkallar du en prenumerant:

1. I [!UICONTROL My Shared Data] hittar du den feed som prenumeranten använder.

   >[!NOTE]
   >
   >Datamatningar med försenade konton flaggas med en ikon för triangel-/utropstecken.

1. Klicka i kolumnen [!UICONTROL Subscribers] på det blå nummer som räknar prenumeranter för den aktuella feeden. Sidan med prenumerationsinformation öppnas.
1. Flytta reglaget **[!UICONTROL Subscription]** till **[!UICONTROL Off]**. Då öppnas en bekräftelsedialogruta.
1. Klicka på **[!UICONTROL Yes]** på popup-menyn [!UICONTROL Confirmation] för att inaktivera en prenumeration eller **[!UICONTROL Cancel]** för att avsluta utan att göra några prenumerationsändringar.

### Vad som händer när du har inaktiverat en prenumerant

Om du återkallar åtkomsten till en datafeed skickas ett e-postmeddelande till alla administratörsanvändare på datainköparens konto. E-postmeddelandet innehåller en bifogad fil med en lista över återkallade egenskaper. Den här listan hjälper prenumeranter att hitta och ta bort inaktiverade egenskaper från sina segment och modeller.

### Deaktivering av fakturering och matning

När du har tagit bort åtkomsten till en datafeed ansvarar abonnenterna för avgifter för föregående eller nuvarande månad, beroende på när du inaktiverade denna.

## Planera typer för datafeeds {#plan-types}

[!DNL Plan types] är viktiga komponenter i en  [!UICONTROL Audience Marketplace] datafeed. Som dataleverantör kan du skapa flera användningsfall och prisalternativ för dina feeds. Dessutom kan det vara en bra strategi att skapa ett antal planer för varje dataflöde. Detta ger köparna olika alternativ att välja mellan när de letar efter data att modellera eller skicka till en destination.

[Skapa en ](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) datafeed att välja  [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Alternativ för plantyper och användningsfall {#plan-types-use-cases}

<!-- c_feed_options.xml -->

Med [!UICONTROL Use Case]-inställningarna kan säljarna styra hur köpare kan använda dina data.

### Segment och överlappning

Ett **[!UICONTROL Segments and Overlap]**-användningsfall skapar en plan där köpare kan jämföra trait-data i en [trait-to-trait-överlappningsrapport](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Dessutom kan köpare lägga till data i segment och jämföra dem med [segment-till-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md)- och [segment-till-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md)-rapporterna.

Varje datafeed måste innehålla minst ett [!UICONTROL Segments and Overlap]-användningsfall. Köpare kan inte prenumerera på andra planer i en datafeed om den inte innehåller ett [!UICONTROL Segments and Overlap]-användningsfall, antingen för sig själv eller i kombination med ett annat användningsfall.

Överlappningsjämförelser kan hjälpa köpare:

* **Nå fler kunder:** Låg överlappning visar att era egenskaper innehåller användare som köparen inte har sett tidigare. Därför kan köpare vilja att dessa egenskaper lägger till nya användare i sina målgruppssegment.
* **Förbättra befintliga målgrupper:** Hög överlappning innebär att era egenskaper innehåller användare som liknar de som en köpare redan känner till. Därför kanske köpare vill att dessa egenskaper ska bidra till riktade, stegvisa förbättringar för framtagna målgrupper.

Priser för detta fall enligt följande:

* Måttenhet: Schablonavgift
* Pris: Kostnadsfritt ($0.00)

### Modeling

Ett **[!UICONTROL Modeling]**-användningsfall skapar en plan där köpare kan jämföra dina egenskaper med sina med [algoritmisk modellering](../../../features/algorithmic-models/understanding-models.md#understanding-models). Köpare tittar på modellresultaten för att hitta nya målgrupper i era data som delar konverteringsattribut som liknar deras egna. Priser för detta fall enligt följande:

* Måttenhet: Schablonavgift
* Pris: Rabatterad kurs eller marknadspris

### Aktivering

Med ett **[!UICONTROL Activation]**-användningsfall kan köpare skicka data till ett [mål](../../../features/destinations/destinations.md). I det här fallet kan köpare inte jämföra data med en överlappningsrapport eller i en algoritmisk modell. Priser för detta fall enligt följande:

* Måttenhet: [!DNL CPM]
* Pris: [!DNL CPM] marknadsränta

## Fakturerings- och prisalternativ {#billing}

Fakturerings- och prisalternativen styr hur köpare betalar för dina data.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Alternativ </th> 
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Faktureringscykel</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Månadsvis i </span></b> Arrearsis är det enda alternativet. Faktureringscykeln avslutas den 10:e dagen i varje månad. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Måttenhet</span></b> </td> 
   <td colname="col2">Debitera datainköpare till en CPM-taxa eller en fast avgift. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Med CPM-priser måste datainköpare själva rapportera användningen. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Med fast avgift rapporterar inte datainköpare om användningen eftersom de debiteras en fast avgift. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Pris</span></b> </td>
   <td colname="col2"> Det belopp som en säljare debiterar köparen som CPM-ränta eller fast avgiftspris, i dollar. </td>
  </tr> 
 </tbody> 
</table>

## Versionsinformation {#plan-notes}

I fältet **[!UICONTROL Additional Notes]** tar du lite tid till att beskriva varje dataplan i en feed. En bra, kort beskrivning hjälper köpare att förstå innehållet eller syftet med varje plan i ett dataflöde. Köpare kan läsa dataflöden och planera beskrivningar när de söker efter eller utvärderar nya datakällor.

## Hantera förfrågningar från privata dataflöden {#manage-private-requests}

Leverantörsarbetsflöden för hantering av privata feedbegäranden från köpare.

Om du vill granska, godkänna eller avvisa köparförfrågningar går du till [!UICONTROL My Shared Data] och:

<!-- t_private_feed_workflows.xml -->

1. Klicka på namnet på den privata datafeeden.
2. Klicka på **[!UICONTROL Access Requests]** för att granska alla köpare som vill ha tillgång till din datafeed.
3. Klicka på bockmarkeringen i [!UICONTROL Allow Access]-avsnittet i varje begäranderuta för att godkänna en begäran eller krysset för att neka åtkomst.
4. Bekräfta eller avbryt den valda åtgärden i bekräftelsefönstret.

## Rabatter för dataleverantörer {#discounts}

I [!UICONTROL Audience Marketplace] kan du minska det publicerade priset för en datafeed för enskilda prenumeranter. Du kan erbjuda rabatter till prenumeranter som har lämnat in en prenumerationsansökan eller till prenumeranter som har begärt information om en datafeed. Rabatterna gäller [!DNL CPM] och feeds med schablonbelopp. Rabatter kan vara användbara när du vill erbjuda prenumerationsincittioner för nya kunder eller belöna kundlojalitet.

## Använd rabatter på en datafeed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Om du vill rabattera en feed lägger du till ett rabattbelopp i % i rabattfältet och bekräftar dina ändringar. Dataleverantörer kan radera dataflöden i [!UICONTROL Audience Marketplace] från antingen:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

I de här exemplen har säljaren lagt till 10 % rabatt i [!UICONTROL Software Audience]-dataflödet.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Granska rabatterade feeds {#review-discounted-feeds}

Dataleverantörer kan se alla sina prenumeranter och rabatterade feeds i **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Privata dataflöden](../../../features/audience-marketplace/marketplace-private-feeds.md)

