---
description: Kolumnrubriketiketter har definierats.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Grupphanteringsverktyg - ordlista
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# Grupphanteringsverktyg - ordlista{#bulk-management-tools-glossary}

Kolumnrubriketiketter har definierats.

>[!IMPORTANT]
>
>Masshanteringsverktygen är inte ett officiellt Adobe-erbjudande som stöds. Felsökning och support via kundtjänst hanteras från fall till fall.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i användargränssnittet för [!DNL Audience Manager] respekteras i [!UICONTROL Bulk Management Tools].

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kolumnrubrik </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>ID för en <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings">-datakälla </a> som du vill returnera eller tilldela gruppvis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>Ett <a href="../../features/derived-signals.md"> härlett signal </a>-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> beskrivning</span> </p> </td> 
   <td colname="col2"> <p>En kort, informativ beskrivning som du kan ge ett objekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId </span> </p> </td> 
   <td colname="col2"> <p>ID för det <a href="../../features/destinations/destinations.md">-mål </a> som du vill mappa eller ta bort. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>Ett särskilt ID som tilldelas ett segment när det mappas till ett mål. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>ID för segmentet eller mappen trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> namn</span> </p> </td> 
   <td colname="col2"> <p>Namnet på det objekt du arbetar med. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>ID för ett segment eller en trait-mapp som innehåller andra mappar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>Segment-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey </span> </p> </td> 
   <td colname="col2"> <p>Signaler är databitar som skickas till <span class="keyword"> Audience Manager </span> baserat på användaraktivitet. Dessa överförs som <a href="../../reference/key-value-pairs-explained.md"> nyckelvärdepar </a>. Källnyckeln är en konstant som inte ändras. Det hjälper till att kategorisera källvärdet som kan ändras. Se <a href="../../features/derived-signals.md"> Härledda signaler</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue </span> </p> </td> 
   <td colname="col2"> <p>Källvärdet är en variabel som skickas som en del av <a href="../../reference/key-value-pairs-explained.md">-nyckelvärdepar</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate </span> </p> </td> 
   <td colname="col2"> <p>Anger när ett segment kan börja skickas till ett mål. Använder formatet <i>åååå-mm-dd</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey </span> </p> </td> 
   <td colname="col2">Nyckeln som används i den härledda signalen. Se <a href="../../features/derived-signals.md"> Härledda signaler</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue </span> </p> </td> 
   <td colname="col2"> <p>Värdet skickades med en härledd signalnyckel. Se <a href="../../features/derived-signals.md"> Härledda signaler</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias </span> </p> </td> 
   <td colname="col2"> <p>Ett ID skickades till ett icke-cookie-baserat mål. För ett cookie-baserat mål är det här nyckeln i ett <a href="../../reference/key-value-pairs-explained.md"> nyckel/värde-par </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>Den faktiska egenskap eller segmentregel som används för att samla in data. En gruppbegäran returnerar reglerna som skapats i <span class="keyword"> Audience Manager </span> med <a href="../../features/traits/about-trait-builder.md"> trait rule builder </a> eller <a href="../../features/segments/segment-builder.md"> segment rule builder </a>. Du kan också använda de här verktygen för att skapa regler och tillämpa dem samtidigt när du uppdaterar ett segment eller en egenskap. </p> <p>Se även <a href="../../reference/bulk-management-tools/bulk-rules.md"> Skapa eller uppdatera Trait Rules och Segment Rules </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType </span> </p> </td> 
   <td colname="col2"> <p>En sträng som identifierar trait-typen. Alternativen är: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel utlöses av DIL när en användare kvalificerar sig för ett segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias </span> </p> </td> 
   <td colname="col2"> <p>Nyckeln i ett <a href="../../reference/key-value-pairs-explained.md"> nyckel/värde-par </a> skickades till en cookie-destination. </p> </td> 
  </tr> 
 </tbody> 
</table>
