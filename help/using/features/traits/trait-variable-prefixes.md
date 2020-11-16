---
description: I den här artikeln beskrivs de prefix som du måste koppla till nyckelvariabler när du skapar trait-regler.
seo-description: I den här artikeln beskrivs de prefix som du måste koppla till nyckelvariabler när du skapar trait-regler.
seo-title: Prefixkrav för nyckelvariabler
solution: Audience Manager
title: Prefixkrav för nyckelvariabler
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: 1c0d40082cd0753a9b4326aae764eb74aefb8be4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 5%

---


# Prefixkrav för nyckelvariabler {#prefix-requirements-for-key-variables}

I den här artikeln beskrivs de prefix som du måste koppla till nyckelvariabler när du skapar trait-regler.

<!-- r_tb_variable_prefixes.xml -->

## Syftet med viktiga variabelprefix

När du skapar [!UICONTROL Trait Builder] regler är det viktigt att prefera nyckelvariabeln med ett rekommenderat prefix. Dessa prefix identifierar vilken typ av data som skickas och hjälper till att undvika namnutrymmeskonflikter i [!DNL Audience Manager]. I allmänhet kan du ge en variabel valfritt namn, men data för en regel bearbetas inte om nyckelvariabelnamnet inte matchar variabelnamnet i ett händelseanrop.

## Prefix för nyckelvariabler

I följande tabell definieras de vanliga prefix som används av [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nyckelvariabelprefix </th> 
   <th colname="col2" class="entry"> Identifierar variabeln </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>Som kundspecifikt. Detta är nyckeldata som skickas in från dina egna egenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>På <span class="keyword"> Audience Manager</span> -nivå. Dessa data är enhetliga över hela <span class="keyword"> Audience Manager</span> . Se <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Attribut som stöds för DCS API-anrop</a> för en mer komplett lista.</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>Det innehåller <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP-rubrikinformation</a> . Innehåller rubrikparametrar som <code> referer</code>,<code> IP</code><code> accept-language</code>osv. </p> <p> <p>Obs! För kunder som använder DIL-versioner som är äldre än 9.0 fungerar inte datainsamling med <code> h_referer</code> signalen i Safari. I och med introduktionen av <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>kan webbläsare i Safari klassificera domänen demdex.net som en spårare och kommer att korta av referenten på datainsamlingsbegäran så att den bara innehåller origo i stället för den fullständiga URL:en. Se <a href="../../dil/dil-overview.md#get-implement-dil-code">Hämta och implementera DIL-kod</a> för den senaste DIL-versionen.<p>Signaler som använder det här prefixet visas inte i <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">Signalsökning</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Våra <span class="wintitle"> datainsamlingsservrar</span> tillåter överföring av privata parametrar. I princip kommer alla parametrar som börjar med <code> p_</code> att användas för utvärdering av egenskaper, men de kommer inte att loggas längre fram i kedjan och inte heller lagras. </p> <p>Exempel: givet <code> /event?p_age=23</code> och ett trait-liknande <code> YoungPeople = p_age &lt; 25</code>blir trait realiserat, men <code> p_age=23</code> key-value-paret tas bort efter begäran och loggas inte. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Översikt över grundläggande information](../../features/traits/create-onboarded-rule-based-traits.md)
>* [Hantera trait-regler](../../features/traits/manage-trait-rules.md#managing-trait-rules)

