---
description: En privat datafeed är ett alternativ som gör att leverantörerna kan begränsa köparåtkomsten till sina data. Dataleverantörer och köpare bör granska informationen innan de skapar och prenumererar på privata dataflöden.
seo-description: A private data feed is an option that lets providers limit buyer access to their data. Data providers and buyers should review this information before creating and subscribing to private data feeds.
seo-title: Private Data Feeds
solution: Audience Manager
title: Privata datafeeds
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
exl-id: 34eb6194-c57b-4836-a6df-6889a2cec703
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 0%

---

# Privata datafeeds {#private-data-feeds}

En privat datafeed är ett alternativ som gör att leverantörerna kan begränsa köparåtkomsten till sina data. Dataleverantörer och köpare bör granska informationen innan de skapar och prenumererar på privata dataflöden.

<!-- c_marketplace_privatefeed.xml -->

## Privata datafeeds för leverantörer {#private-data-feeds-providers}

Som leverantör kan dina dataflöden vara offentliga eller privata. Med ett privat dataflöde kan du begränsa köparens åtkomst till dina data, inklusive namnet på dataförsäljaren. Du kanske vill skapa en privat datafeed för att kunna erbjuda specialerbjudanden, rabatter eller när sekretess och åtkomstkontroll är viktigt. Med en privat datafeed kan ni granska och godkänna köparförfrågningar. När du har godkänt en begäran ser flödet ut precis som en offentlig datafeed till köparen. Du kan visa och hantera alla dina feeds i **[!UICONTROL Audience Marketplace > My Shared Data]**. Som framgår nedan är den här typen av feed markerad &quot;Privat&quot; i statuskolumnen.

![](assets/my_shared_data.png)

### Hantera flödesbegäranden

Om du klickar på namnet på en privat datafeed från [!UICONTROL My Shared Data] kommer du till en sida som innehåller flera flikar. Klicka på en flik för att hantera dina förfrågningar om privat datafeed.

![](assets/shared_data_tabs.png)

I följande tabell definieras rollen eller funktionerna som tillhandahålls av varje åtgärdsflik.

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabb </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> aktuella prenumeranter</span></b> </p> </td> 
   <td colname="col2"> <p>Visar en lista över godkända köpare som har prenumererat på en privat datafeed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> potentiella prenumeranter</span></b> </p> </td> 
   <td colname="col2"> <p>Visar en lista över godkända köpare som inte har prenumererat på en privat datafeed. </p> <p>Med ett godkännande kan köpare visa en datafeed som om den vore offentlig. Detta ger dem möjlighet att granska och utvärdera dina feeds innan de prenumererar. Du kan även erbjuda rabatter på dataflöden till köpare som anges som potentiella prenumeranter. När köparen prenumererar flyttas deras profil till <b><span class="uicontrol"> aktuella prenumeranter</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> åtkomstbegäranden</span></b> </p> </td>
   <td colname="col2"> <p>Visar nya prenumerationsbegäranden för en privat datafeed. Klicka på den här fliken om du vill granska, godkänna eller avvisa köparförfrågningar. </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Godkända köpare flyttar till <b><span class="uicontrol"> potentiella prenumeranter</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Avvisade köpare flyttar till <b><span class="uicontrol"> nekad åtkomst</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> informationsförfrågningar</span></b> </p> </td>
   <td colname="col2"> <p>Visar en lista över godkända köpare som ännu inte har prenumererat på en datafeed och som har begärt mer information om dina feeds. </p> <p>Med ett godkännande kan köpare visa en datafeed som om den vore offentlig. Detta ger dem möjlighet att granska och utvärdera dina feeds innan de prenumererar. Du kan även erbjuda rabatter på dataflöden till köpare som begär åtkomst. Om du svarar på en informationsbegäran tas köparprofilen bort från den här fliken. Om de inte har prenumererat finns köpprofilen fortfarande i <b><span class="uicontrol"> potentiella prenumeranter</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Nekad åtkomst</span></b> </p> </td> 
   <td colname="col2"> <p>Visar nekade prenumerationsbegäranden för en privat datafeed. </p> <p>Ändra <span class="wintitle">-avvisningsstatus </span> till <b><span class="uicontrol"> Tillåt</span></b> om du vill omgodkänna nekade köpare. Detta flyttar köparen till <b><span class="uicontrol"> potentiella prenumeranter</span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Nästa steg

Följande dokumentation kan hjälpa dig att komma igång med privata dataflöden.

* [Skapa en offentlig eller privat datafeed](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [Granska, godkänn eller avvisa privata feedbegäranden](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [Privata datafeeds för köpare](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## Privata datafeeds för köpare {#private-data-feeds-for-buyers}

Som köpare visas privata datafeeds på [Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) precis som andra erbjudanden. I det här fallet visar dock matningslistan inte sammanfattningsinformation för traits, unique users, and user overlap. Datasäljaren kan även välja att visa eller dölja sitt namn i kolumnen [!UICONTROL Provider] i listan [!UICONTROL Marketplace]. När säljaren har godkänt din prenumerationsförfrågan blir alla data i en privat feed tillgängliga för dig (den fungerar precis som en offentlig feed). I exemplet [!UICONTROL Marketplace] nedan visas de tre olika flödestyperna som är tillgängliga för dig som köpare.

![](assets/buyer_marketplace.png)

Några flödestyper är:

Tabellen beskriver hur dessa olika flödestyper visar eller döljer data.

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feed-typ </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Offentlig</span></b> </p> </td> 
   <td colname="col2"> <p>Providerns namn, egenskaper och unika data visas i listan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> privat utan profilering</span></b> </p> </td> 
   <td colname="col2"> <p>Leverantörens namn är inställt på "Privat säljare" och du kan inte se antalet trait, unika data och trait-överlappningsdata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> privat med profilering</span></b> </p> </td> 
   <td colname="col2"> <p>Providerns namn visas i listan men du kan inte se antalet trait, unika data och trait-överlappningsdata. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Nästa steg

Se [Prenumerera på en privat datafeed](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) för att begära åtkomst.

## Ställa in delningsrelationen mellan Data Provider och Data Buyer {#set-up-sharing-relationship}

### Steg 1 - Aktivera - Dataprovider och Datainköpare

Det första steget i processen kräver ingripande från Adobe Consulting eller kundtjänst. Dataleverantören och datainköparen bör kontakta Adobe Consulting eller kundtjänst för att begära aktiveringen.

### Steg 2 - Dataprovider - Skapa nya data-Source

I ditt Audience Manager-konto skapar du en ny cookie-datakälla med:

* **Audience Manager ID** som inkommande nyckel;
* Alternativet **Dela aktiverad** har markerats.

![](assets/create-datasource.png)

När du har klickat på **Spara** skapas en ny undermapp automatiskt i **Traits Storage > Tredjepartsdata**.

![](assets/folder-structure.png)

### Steg 3 - Dataprovider - Identifiera egenskaper för delning

I det här steget identifierar du de egenskaper som du vill dela med din partner. Du kan antingen skapa nya egenskaper eller redigera befintliga egenskaper. Du behöver i vilket fall som helst egenskaperna:

* Ska kopplas till datakällan som du skapade som en del av steg 2.
* Ska lagras i den nya undermappen, under data från tredje part.

Läs mer om att [skapa egenskaper](/help/using/features/traits/create-onboarded-rule-based-traits.md) och [redigera egenskaper](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### Steg 4 - Dataprovider - Skapa datafeed

Skapa sedan en datafeed för att dela dina egenskaper med dataläsaren. Mer information om hur du skapar en datafeed finns i [Skapa en offentlig eller privat datafeed](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md).

>[!IMPORTANT]
>
>Välj alternativet Privat i Inställningar. Om du anger det här fältet som Allmänt kan alla Audience Marketplace-kunder prenumerera på din feed.

![](assets/create-data-feed.png)

### Steg 5 - Datainköpare - Begär åtkomst

Gå till **Audience Marketplace > Marketplace**. Sök efter den datafeed som har skapats av DataProvider i föregående steg. Klicka på **Begär åtkomst**. Den utsedda kontakten från dataleverantörssidan får nu ett e-postmeddelande. Se även [Prenumerera på en privat datafeed](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### Steg 6 - Dataprovider - Bevilja åtkomst

Gå till **Audience Marketplace > Mina delade data** och sök efter den feed du skapade i steg 4. Klicka på den nya åtkomstbegäran och klicka på **Tillåt åtkomst** för att godkänna begäran. Se även [Granska, godkänn eller avvisa privata feedbegäranden](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests).

### Steg 7 - Datainköpare - Aktivera prenumeration

När dataleverantören har beviljat åtkomst till dataflödet kan du se feeden på ditt konto i **Audience Marketplace > Marketplace**. Granska informationen, aktivera prenumerationsknappen och klicka på **Granska och prenumerera**. Mer information om var du hittar tredjepartsegenskaper finns i [Lagring för abonnerade datafeeds](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee).

Observera att dessa egenskaper bara kan redigeras i DataProvider-kontot.
