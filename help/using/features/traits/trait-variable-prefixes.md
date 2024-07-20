---
description: I den här artikeln beskrivs de prefix som du måste koppla till nyckelvariabler när du skapar trait-regler.
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: Prefixkrav för nyckelvariabler
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# Prefixkrav för nyckelvariabler {#prefix-requirements-for-key-variables}

I den här artikeln beskrivs de prefix som du måste koppla till nyckelvariabler när du skapar trait-regler.

<!-- r_tb_variable_prefixes.xml -->

## Syftet med viktiga variabelprefix

När du skapar [!UICONTROL Trait Builder]-regler är det viktigt att prefera nyckelvariabeln med ett rekommenderat prefix. Dessa prefix identifierar vilken typ av data som skickas och hjälper till att undvika namnområdeskonflikter i [!DNL Audience Manager]. I allmänhet kan du ge en variabel valfritt namn, men data för en regel bearbetas inte om nyckelvariabelnamnet inte matchar variabelnamnet i ett händelseanrop.

## Prefix för nyckelvariabler

Följande tabell definierar de vanliga prefix som används av [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nyckelvariabelprefix </th> 
   <th colname="col2" class="entry"> Anger variabeln </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>Som kundspecifikt. Detta är nyckeldata som skickas in från dina egna egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>På nivån <span class="keyword"> Audience Manager</span>. Dessa data är enhetliga i hela ekosystemet <span class="keyword"> Audience Manager </span>. Se <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attribut som stöds för DCS API-anrop </a> för en mer fullständig lista.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Det innehåller <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP-huvudinformation </a>. Innehåller rubrikparametrar som <code> referer</code>,<code> IP</code>, <code> accept-language</code> osv. </p> <p> <p>Obs! För kunder som använder DIL-versioner som är äldre än 9.0 fungerar inte datainsamling med signalen <code> h_referer</code> i Safari. I och med introduktionen av <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a> kan webbläsare i Safari klassificera domänen demdex.net som en spårare och kommer att korta av referenten på datainsamlingsbegäran så att den bara innehåller origo i stället för den fullständiga URL:en. Se <a href="../../dil/dil-overview.md#get-implement-dil-code">Hämta och implementera DIL-kod</a> för den senaste DIL-versionen.<p>Signaler som använder det här prefixet visas inte i <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signalsökning</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Våra <span class="wintitle"> datainsamlingsservrar </span> tillåter överföring av privata parametrar. I princip kommer alla parametrar som börjar med <code> p_</code> att användas för utvärdering av egenskaper, men de kommer inte att loggas längre fram i kedjan eller lagras. </p> <p>Exempel: givet <code> /event?p_age=23</code> och ett trait som <code> YoungPeople = p_age &lt; 25</code> kommer trait att realiseras, men nyckelvärdepar <code> p_age=23</code> kommer att tas bort efter begäran och kommer inte att loggas. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Grundläggande informationsöversikt](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Hantera trait-regler](../../features/traits/manage-trait-rules.md#managing-trait-rules)
