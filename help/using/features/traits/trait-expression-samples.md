---
description: Exempel som du kan referera till när du skapar uttryck i kodredigeraren i Expression Builder.
seo-description: Exempel som du kan referera till när du skapar uttryck i kodredigeraren i Expression Builder.
seo-title: Exempeluttryck med booleska operatorer och jämförelseoperatorer
solution: Audience Manager
title: Exempeluttryck med booleska operatorer och jämförelseoperatorer
uuid: ee74c376-2099-4816-8694-43f58845a0ac
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Exempeluttryck med booleska operatorer och jämförelseoperatorer {#sample-expressions-with-boolean-and-comparison-operators}

Exempel som du kan referera till när du skapar uttryck i kodredigeraren [!UICONTROL Expression Builder] .

## Översikt över kodexempel {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Skapa egna regler med [!UICONTROL Expression Builder] kodredigeraren. Följande exempel kan hjälpa dig att komma igång. I vissa av exemplen används variabeln som prefix för *`key`* `c_` att identifiera den som en användardefinierad variabel. Inkludera `c_` prefixet (eller någon annan namnkonvention) för *`key`* variabeln om dina händelseanrop skickar data till [!DNL Audience Manager] med den syntaxen.

## Booleska uttryck {#boolean-expressions}

### AND-exempel

Regeln fastställer krav på kvalificering av egenskaper med hjälp av booleska [!UICONTROL AND] operatorer.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exempelkod </th> 
   <th colname="col2" class="entry"> För att bli berättigad måste besökaren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">Leta efter ett visst märke och en viss modell. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">Hitta produkten på en sökresultatsida (sökning = "1" eller "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### ELLER-exempel

I denna regel fastställs krav på kvalificering av egenskaper med hjälp av [!DNL Boolean] och [!UICONTROL OR] [!UICONTROL AND] operatorer.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exempelkod </th> 
   <th colname="col2" class="entry"> För att bli berättigad måste besökaren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Uppfyll villkoren som anges av variabler <code><i>a </i></code> eller <code><i>b </i></code> och <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Intervallexempel med större än, mindre än, lika med

I den här regeln fastställs krav för kvalificering av egenskaper utifrån ett intervall.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exempelkod </th> 
   <th colname="col2" class="entry"> För att bli berättigad måste besökaren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Uppfyll alla prisvillkor mellan 1.00 och 100.00. </td> 
  </tr> 
 </tbody> 
</table>