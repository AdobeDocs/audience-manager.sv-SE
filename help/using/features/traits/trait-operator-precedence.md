---
description: Trait Builder utvärderar uttryck i den ordning som de anges nedan, från hög till låg prioritet. Trait-element som definieras av operatorer med hög prioritet utvärderas först, före andra prioritetsoperatorer. I det här avsnittet rangordnas varje operator efter prioritet, från hög till låg.
seo-description: Trait Builder utvärderar uttryck i den ordning som de anges nedan, från hög till låg prioritet. Trait-element som definieras av operatorer med hög prioritet utvärderas först, före andra prioritetsoperatorer. I det här avsnittet rangordnas varje operator efter prioritet, från hög till låg.
seo-title: Operationsordning i Trait Builder
solution: Audience Manager
title: Operationsordning i Trait Builder
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---


# Operationsordning i Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] utvärderar uttryck i den ordning som anges nedan, från hög till låg prioritet. Trait-element som definieras av operatorer med hög prioritet utvärderas först, före andra prioritetsoperatorer. I det här avsnittet rangordnas varje operator efter prioritet, från hög till låg.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operatorprioritet </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Kommentarer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parentes </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Uttryck inom parentes utvärderas alltid först och följer prioritetsordningen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Jämförelseoperatorer </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Härnäst utvärderas mindre än, större än, mindre än/lika med, större än/lika med. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Likhetsoperatorer </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Lika med, inte lika med, utvärderas efter föregående operatorer. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> OCH</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> ELLER</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Arbeta med booleska uttryck (AND, OR, NOT) i TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Arbeta med jämförelseoperatorer i TraitBuilder](../../features/traits/trait-comparison-operators.md)

