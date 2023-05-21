---
description: Beskriver hur du konfigurerar steg och funktioner som är specifika för den regelbaserade processen att skapa anpassade egenskaper.
keywords: skapa egenskap;skapa egenskaper
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Skapa regelbaserade eller registrerade traits
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 3%

---

# Skapa [!UICONTROL Rules-Based] eller [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Beskriver hur du konfigurerar steg och funktioner som är specifika för [!UICONTROL rules-based] och [!UICONTROL onboarded] processen att skapa egenskaper.

<!-- c_tb_rules_traits.xml -->

## Grundläggande information för Traits {#basics}

I [!UICONTROL Trait Builder], [!UICONTROL Basic Information] gör att du kan skapa nya eller redigera befintliga [!UICONTROL traits]. The [!UICONTROL Basic Information] inställningarna är desamma för [!UICONTROL rules-based], [!UICONTROL onboarded] och [!UICONTROL algorithmic traits]. Skapa en ny [!UICONTROL trait], ange ett namn (undvik specialtecken), [!UICONTROL data source]och väljer [!UICONTROL storage folder]. Övriga [!UICONTROL Basic Information] -fält är valfria.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Definierade grundläggande informationsfält

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gränssnittselement </th> 
   <th colname="col2" class="entry"> Förklaring </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Namn</span></b> </td> 
   <td colname="col2"> <p>The trait name. Obligatoriskt. </p> <p>Maximal längd: 255 tecken. </p> <p> <p>Obs! Undvik följande specialtecken när du namnger egenskaper: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommatecken </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Streck </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Bindestreck </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Tabbar </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Lodrät stapel- eller lodsymbol </li> 
      </ul> </p> </p> <p>Detta minskar antalet bearbetningsfel när du ställer in en <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> överföring av inkommande datafil</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Beskrivning</span></b> </td> 
   <td colname="col2"> Några ord som kan beskriva syftet eller funktionen med trakten. Valfritt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datakälla</span></b> </td> 
   <td colname="col2"> Associerar egenskapen med en viss DataProvider. Obligatoriskt. <p>Använd den första listrutan för att filtrera mellan Audience Manager och datakällor, Adobe Analytics rapportsviter eller båda. Använd sedan den andra listrutan för att välja datakälla.</p><p> Om du inte använder Adobe Analytics rapportprogramsviter är datakälltypväljaren inaktiverad och standardinställningen är endast Audience Manager datakällor.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Händelsetyp</span></b> </td> 
   <td colname="col2"> Tilldelar egenskapen till en typ eller kategori, vanligtvis enligt funktion (t.ex. konvertering, besökare, partner, sidvy). Valfritt. <p> Mer information om hur du skapar konverteringsegenskaper finns i <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Video om att skapa konverteringsegenskaper i Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Integreringskod</span></b> </td> 
   <td colname="col2"> Ett fält för ett ID, SKU eller annat värde som används av dina interna affärsprocesser. Valfritt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kommentarer</span></b> </td> 
   <td colname="col2"> Allmän information om en egenskap. Valfritt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Lagra i</span></b> </td> 
   <td colname="col2"> Avgör vilken lagringsmapp som egenskapen tillhör. Obligatoriskt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datakategori</span></b> </td> 
   <td colname="col2"> Klassificerar egenskaper enligt vanliga kategorier. <p>Obs! Fastigheter tillhör endast en kategori. Valfritt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ange en [!UICONTROL Trait] Förfallointervall {#set-expiration-interval}

I [!UICONTROL Trait Builder], [!UICONTROL Advanced Options] gör att du kan ange en time-to-live-inställning ([!DNL TTL]) intervall för [!UICONTROL trait]. [!DNL TTL] definierar hur många dagar en kvalificerad besökare stannar kvar på en [!UICONTROL trait] (120 dagar är standard). Med inställningen 0 [!UICONTROL trait] upphör aldrig att gälla.

<!-- t_tb_ttl.xml -->

### Ange TTL för en [!UICONTROL trait]

1. Expandera [!UICONTROL Advanced Options] och ange ett tal för [!DNL TTL] värdet för [!UICONTROL trait].
1. Klicka på **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Förklara segmenttiden till Live](../../features/traits/segment-ttl-explained.md)

