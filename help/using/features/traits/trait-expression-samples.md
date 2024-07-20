---
description: Exempel som du kan referera till när du skapar uttryck i kodredigeraren i Expression Builder.
seo-description: Examples you can refer to for creating expressions in the Expression Builder code editor.
seo-title: Sample Expressions With Boolean and Comparison Operators
solution: Audience Manager
title: Exempeluttryck med booleska operatorer och jämförelseoperatorer
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: Traits
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 0%

---

# Exempeluttryck med booleska operatorer och jämförelseoperatorer {#sample-expressions-with-boolean-and-comparison-operators}

Exempel som du kan referera till när du skapar uttryck i kodredigeraren för [!UICONTROL Expression Builder].

## Översikt över kodexempel {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Skapa egna trait-regler med kodredigeraren [!UICONTROL Expression Builder]. Följande exempel kan hjälpa dig att komma igång. Vissa av exemplen föregår variabeln *`key`* med `c_` för att identifiera den som en användardefinierad variabel. Inkludera prefixet `c_` (eller någon annan namnkonvention) för variabeln *`key`* om dina händelseanrop skickar data till [!DNL Audience Manager] med den syntaxen.

## Booleska uttryck {#boolean-expressions}

### AND-exempel

Regeln fastställer krav på kvalificering av egenskaper med hjälp av booleska operatorer [!UICONTROL AND].

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exempelkod </th> 
   <th colname="col2" class="entry"> För att kvalificera sig måste besökaren </th> 
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

Den här regeln ställer in krav på kvalificering av egenskaper med hjälp av operatorerna [!DNL Boolean] [!UICONTROL OR] och [!UICONTROL AND].

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exempelkod </th> 
   <th colname="col2" class="entry"> För att kvalificera sig måste besökaren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> Uppfyll villkoren som anges av variablerna <code><i>a </i></code> eller <code><i>b </i></code> och <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## Intervallexempel med större än, mindre än, lika med

I den här regeln fastställs krav för kvalificering av egenskaper med hjälp av ett intervall.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exempelkod </th> 
   <th colname="col2" class="entry"> För att kvalificera sig måste besökaren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> Uppfyll alla prisvillkor mellan 1.00 och 100.00. </td> 
  </tr> 
 </tbody> 
</table>
