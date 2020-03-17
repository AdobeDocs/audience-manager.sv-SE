---
description: Beskriver hur du konfigurerar steg och funktioner som är specifika för den regelbaserade processen att skapa anpassade egenskaper.
keywords: create trait;create traits
seo-description: Beskriver hur du konfigurerar steg och funktioner som är specifika för den regelbaserade processen att skapa anpassade egenskaper.
seo-title: Skapa regelbaserade eller introduktionskunskaper
solution: Audience Manager
title: Skapa regelbaserade eller introduktionskunskaper
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Skapa regelbaserade eller introduktionskunskaper {#create-rules-based-or-onboarded-traits}

Beskriver hur du konfigurerar steg och funktioner som är specifika för processen att skapa [!UICONTROL rules-based] - och [!UICONTROL onboarded] egenskaper.

<!-- c_tb_rules_traits.xml -->

## Grundläggande information för Traits {#basics}

I [!UICONTROL Trait Builder]kan du med [!UICONTROL Basic Information] inställningarna skapa nya eller redigera befintliga egenskaper. Inställningarna [!UICONTROL Basic Information] är desamma för regelbaserade, onboardbaserade och algoritmiska egenskaper. Ange ett namn (undvik specialtecken), en datakälla och välj en lagringsmapp om du vill skapa ett nytt varumärke. Andra [!UICONTROL Basic Information] fält är valfria.

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
      </ul> </p> </p> <p>Detta minskar antalet bearbetningsfel när du konfigurerar en <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> inkommande datafilöverföring</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Beskrivning</span></b> </td> 
   <td colname="col2"> Några ord som kan beskriva syftet eller funktionen med trakten. Valfritt. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datakälla</span></b> </td> 
   <td colname="col2"> Associerar egenskapen med en viss DataProvider. Obligatoriskt. <p>Använd den första listrutan för att filtrera mellan datakällor i Audience Manager, rapportsviter i Adobe Analytics eller båda. Använd sedan den andra listrutan för att välja datakälla.</p><p> Om du inte använder rapportsviter från Adobe Analytics inaktiveras typväljaren för datakällan och används som standard endast för datakällor i Audience Manager.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Händelsetyp</span></b> </td> 
   <td colname="col2"> Tilldelar egenskapen till en typ eller kategori, vanligtvis enligt funktion (t.ex. konvertering, besökare, partner, sidvy). Valfritt. <p> Mer information om hur du skapar konverteringsegenskaper finns i <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Skapa konverteringsegenskaper i videon</a>om Audience Manager. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Integrationskod</span></b> </td> 
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
   <td colname="col2"> Klassificerar egenskaper enligt vanliga kategorier. <p>Obs!  Fastigheter tillhör endast en kategori. Valfritt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ange ett förfallointervall för trait {#set-expiration-interval}

I [!UICONTROL Trait Builder]kan du [!UICONTROL Advanced Options] ange ett intervall för time-to-live ([!DNL TTL]) för en egenskap. [!DNL TTL] definierar hur många dagar en kvalificerad besökare stannar kvar i ett spår (120 dagar är standard). Om värdet är 0 upphör aldrig ditt medlemskap för varumärken.

<!-- t_tb_ttl.xml -->

### Ange TTL-värde för ett tecken

1. Expandera [!UICONTROL Advanced Options] avsnittet och ange ett tal för att ange ett [!DNL TTL] värde för egenskapen.
1. Klicka på **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Förklara segmenttiden till Live](../../features/traits/segment-ttl-explained.md)

