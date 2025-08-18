---
description: Beskriver hur du konfigurerar steg och funktioner som är specifika för den regelbaserade processen att skapa anpassade egenskaper.
keywords: skapa egenskap;skapa egenskaper
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Skapa regelbaserade eller introduktionskassor
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---

# Skapa [!UICONTROL Rules-Based] eller [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Beskriver hur du konfigurerar steg och funktioner som är specifika för processen att skapa [!UICONTROL rules-based] och [!UICONTROL onboarded]-egenskaper.

<!-- c_tb_rules_traits.xml -->

## Grundläggande information för Traits {#basics}

I [!UICONTROL Trait Builder] kan du med [!UICONTROL Basic Information]-inställningarna skapa nya eller redigera befintliga [!UICONTROL traits]. [!UICONTROL Basic Information]-inställningarna är desamma för [!UICONTROL rules-based], [!UICONTROL onboarded] och [!UICONTROL algorithmic traits]. Om du vill skapa en ny [!UICONTROL trait] anger du ett namn (undvik specialtecken), en [!UICONTROL data source] och väljer en [!UICONTROL storage folder]. Andra [!UICONTROL Basic Information]-fält är valfria.

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
   <td colname="col1"> <b><span class="uicontrol"> namn </span></b> </td> 
   <td colname="col2"> <p>The trait name. Obligatoriskt. </p> <p>Maximal längd: 255 tecken. </p> <p> <p>Obs! Undvik följande specialtecken när du namnger egenskaper: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommatecken </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Streck </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Bindestreck </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Tabbar </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Lodrät stapel- eller lodsymbol </li> 
      </ul> </p> </p> <p>Detta minskar antalet bearbetningsfel när du konfigurerar en <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> inkommande datafilöverföring</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Beskrivning</span></b> </td> 
   <td colname="col2"> Några ord som kan beskriva syftet eller funktionen med trakten. Valfritt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Data Source</span></b> </td> 
   <td colname="col2"> Associerar egenskapen med en viss DataProvider. Obligatoriskt. <p>Använd den första listrutan för att filtrera mellan Audience Manager datakällor, Adobe Analytics rapporteringsprogram eller båda. Använd sedan den andra listrutan för att välja datakälla.</p><p> Om du inte använder Adobe Analytics rapportprogramsviter är datakälltypväljaren inaktiverad och standardinställningen är endast Audience Manager datakällor.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Händelsetyp </span></b> </td> 
   <td colname="col2"> Tilldelar egenskapen till en typ eller kategori, vanligtvis enligt funktion (t.ex. konvertering, besökare, partner, sidvy). Valfritt. <p> Mer information om hur du skapar konverteringsegenskaper finns i videon <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Skapa konverteringsegenskaper i Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Integrationskod </span></b> </td> 
   <td colname="col2"> Ett fält för ett ID, SKU eller annat värde som används av dina interna affärsprocesser. Valfritt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> kommentarer</span></b> </td> 
   <td colname="col2"> Allmän information om en egenskap. Valfritt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Lagra i </span></b> </td> 
   <td colname="col2"> Avgör vilken lagringsmapp som egenskapen tillhör. Obligatoriskt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datakategori </span></b> </td> 
   <td colname="col2"> Klassificerar egenskaper enligt vanliga kategorier. <p>Obs! Traits tillhör endast en kategori. Valfritt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ange ett förfallointervall för [!UICONTROL Trait] {#set-expiration-interval}

I [!UICONTROL Trait Builder] kan du med [!UICONTROL Advanced Options] ange ett time-to-live-intervall ([!DNL TTL]) för en [!UICONTROL trait]. [!DNL TTL] definierar hur många dagar en kvalificerad besökare stannar kvar i en [!UICONTROL trait] (120 dagar är standard). Om värdet är 0 upphör aldrig [!UICONTROL trait]-medlemskapet att gälla.

<!-- t_tb_ttl.xml -->

### Ange TTL för en [!UICONTROL trait]

1. Expandera avsnittet [!UICONTROL Advanced Options] och ange ett tal för att ange ett [!DNL TTL]-värde för [!UICONTROL trait].
1. Klicka på **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Segmenttid till Live (förklaras)](../../features/traits/segment-ttl-explained.md)
