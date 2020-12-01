---
description: Generera en faktureringsrapport för Audience Marketplace för att visa dataflödesanvändningen för den föregående månaden för var och en av dina prenumeranter. Du kan skapa en rapport för föregående månad när som helst. Rapporten blir dock mer exakt när du genererar den den den 10:e dagen i den aktuella månaden eller senare.
seo-description: Generera en faktureringsrapport för Audience Marketplace för att visa dataflödesanvändningen för den föregående månaden för var och en av dina prenumeranter. Du kan skapa en rapport för föregående månad när som helst. Rapporten blir dock mer exakt när du genererar den den den 10:e dagen i den aktuella månaden eller senare.
seo-title: Fakturering för dataflödesleverantörer
solution: Audience Manager
title: Fakturering för dataflödesleverantörer
topic: DIL API
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 3%

---


# Fakturering för dataflödesleverantörer {#billing-for-data-feed-providers}

Generera en [!DNL Audience Marketplace] faktureringsrapport för att visa dataflödesanvändningen för den föregående månaden för var och en av dina prenumeranter. Du kan skapa en rapport för föregående månad när som helst. Rapporten blir dock mer exakt när du genererar den den den 10:e dagen i den aktuella månaden eller senare.

## Hämta en faktureringsrapport {#download-billing-report}

Så här hämtar du en rapport:

1. Gå till **[!UICONTROL Audience Marketplace > Receivables]**.
1. Klicka på **[!UICONTROL Generate Billing Report]**.

## Rapportfält definierade {#report-fields-defined}

En faktureringsrapport innehåller följande information.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rapportfält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Dataproviderns PID</span></b> </p> </td> 
   <td colname="col2"> <p>Ditt <span class="keyword"> Audience Manager</span>-dataleverantörs-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Dataproviderns namn</span></b> </p> </td> 
   <td colname="col2"> <p>Ditt företags- eller organisationsnamn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Köparens PID</span></b> </p> </td> 
   <td colname="col2"> <p>Buyer (prenumerant)-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Köparnamn</span></b> </p> </td> 
   <td colname="col2"> <p>Köparens företags- eller organisationsnamn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed-ID</span></b> </p> </td> 
   <td colname="col2"> <p>ID för datafeeden </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feednamn</span></b> </p> </td> 
   <td colname="col2"> <p>Dataflödets namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Användningsexempel för plan</span></b> </p> </td> 
   <td colname="col2"> <p>Användningsfall låter säljarna styra hur köparna använder data. Alternativen är: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segment och överlappning </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modeling </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Aktivering </li> 
    </ul> <p>Se <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Plantyper för datafeeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Måttenhet</span></b> </p> </td> 
   <td colname="col2"> <p>Anger CPM eller platt avgiftsfakturering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Listpris</span></b> </p> </td> 
   <td colname="col2"> <p>Prenumerationsavgiften för varje datafeed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Rabatterat pris</span></b> </p> </td> 
   <td colname="col2"> <p>Prenumerationsavgiften för en diskonterad datafeed. Se <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Rabatter för dataleverantörer</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Enheter</span></b> </p> </td> 
   <td colname="col2"> <p>Varierar efter flödespristyp: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Datautflöden med schablonbelopp: Returnerar endast 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM-dataflöden: Returnerar den faktiska användningsmängden för CPM-dataflöden. Om en prenumerant inte har angett visningsdata för en CPM-feed är cellen Units tom och flaggcellen är inställd på 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Total kostnad</span></b> </p> </td> 
   <td colname="col2"> <p>Beloppet <span class="keyword"> Audience Manager</span> fakturerar en köpare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Faktureringsperiod</span></b> </p> </td> 
   <td colname="col2"> <p> I rapporten är detta den sista dagen i föregående månad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Anmälningsdatum</span></b> </p> </td> 
   <td colname="col2"> <p>Datumet då en köpare angav prenumerations-/användningsinformation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Startdatum för prenumerationen</span></b> </p> </td> 
   <td colname="col2"> <p>Det datum då en köpare startade sin prenumeration på dataflöden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Slutdatum för prenumerationen</span></b> </p> </td> 
   <td colname="col2"> <p>Det datum då en köpare avslutade sin prenumeration på dataflöden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flagga</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Endast</i> för CPM-flöden. Flaggalternativen är: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Anger att en prenumerant har rapporterat användningsinformation till <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Anger att en prenumerant inte har rapporterat användningsinformation till <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Fakturering och Impression-allokering för CPM-dataflöden](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Fakturering och Impression-allokering för statiska avgiftsdatafeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Rapportera CPM-användning](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

