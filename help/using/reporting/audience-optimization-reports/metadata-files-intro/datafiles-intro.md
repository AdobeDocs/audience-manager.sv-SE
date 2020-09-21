---
description: En datafil innehåller indata för att visa, klicka eller konvertera. När informationen är korrekt formaterad kan du importera den till Audience Manager och använda den i Audience Optimization-rapporterna och för loggfiler som kan användas. Formatera datafilerna enligt specifikationerna i det här avsnittet.
seo-description: En datafil innehåller indata för att visa, klicka eller konvertera. När informationen är korrekt formaterad kan du importera den till Audience Manager och använda den i Audience Optimization-rapporterna och för loggfiler som kan användas. Formatera datafilerna enligt specifikationerna i det här avsnittet.
seo-title: Datafiler för Audience Optimization-rapporter och verkställbara loggfiler
solution: Audience Manager
title: Datafiler för Audience Optimization-rapporter och verkställbara loggfiler
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: log files
translation-type: tm+mt
source-git-commit: ff592184ba1785e3448aa449745d0e66ecba955b
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 3%

---


# Datafiler för Audience Optimization-rapporter och verkställbara loggfiler {#data-files-for-audience-optimization-reports}

En datafil innehåller indata för att visa, klicka eller konvertera. När dessa data är korrekt formaterade kan du importera dem till Audience Manager för att visa dem i [Audience Optimization-rapporterna](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) och skapa egenskaper med hjälp av [loggfilerna](/help/using/integration/media-data-integration/actionable-log-files.md). Formatera datafilerna enligt dessa specifikationer i det här avsnittet.

## Översikt {#overview}

Med en korrekt namngiven och formaterad datafil kan du importera, klicka och konvertera data till [Audience Optimization-rapporter](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). Detta är användbart när du arbetar med en partner som inte är integrerad med [!DNL Audience Manager] och du vill arbeta med deras data i den rapportsviten. Den här processen kräver separata filer för bild-, klicknings- och konverteringsdata. Blanda inte dessa händelser i en enda fil.

En datafil måste åtföljas av en metadatafil. Innehållet i metadatafilen matchar informationen i datafilen med relaterade, läsbara etiketter på rapportmenyerna. Mer information finns i [Översikt och mappningar för metadatafiler](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

Följande syntax definierar strukturen för ett välformaterat datafilnamn. Obs! *Kursiv* anger en variabel platshållare som ändras beroende på filinnehållet.

**Syntax:** `event type_yyyymmdd`

I ett filnamn:

* Händelsetypen anger att filen innehåller avbildningar, klickningar eller konverteringar. Skapa en separat fil för varje händelsetyp.
* Ett understreck skiljer händelsetypen och en tidsstämpel för årsdatum.
* Innan du överför filerna ska du komprimera dem med gzip och spara dem med `.gz` filtillägget.

Med tanke på dessa krav bör du namnge dina datafiler baserat på deras innehåll så här:

* Impressionsdata: `impressions_yyyymmdd.gz`
* Klicka på data: `clicks_yyyymmdd.gz`
* Konverteringsdata: `conversions_yyyymmdd.gz`

## Content Format for Data Files {#content-format}

Följande syntax definierar innehållsstrukturen i välformade datafiler. Observera att *kursiv* anger en variabelplatshållare och ersätts med en etikett i en faktisk datafil.

**Syntax:** `header label 1 | header label 2 ... header label n | version`

I filinnehållet:

* Rubriketiketterna måste finnas i den ordning som visas i tabellen nedan. Samma etiketter används för tryck och klick. Konverteringsfiler innehåller extra rubriker.
* Om du inte har data för en viss kolumn fyller du i fältet med ett `-1`.

* Filerna *måste* avslutas med ett versionsnummer. Den aktuella versionen är 1.1.
* Avgränsa filhuvuden och -innehåll med icke-utskrivbara ASCII 001-tecken. Om du inte kan använda ASCII 001 ska du separera sidhuvuden och data med en tabbavgränsare. Eftersom det här är tecken som inte skrivs ut visas endast ett rör `"|"` för visning i syntaxexemplet ovan.

**Fältetiketter**

Tabellen nedan listar och beskriver kolumnrubrikerna för datafilen. Sidhuvuden är skiftlägeskänsliga och måste visas enligt ordningen i tabellen. Alla datatyper är heltal (INT) om inget annat anges.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etikett </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tidsstämpel </p> </td> 
   <td colname="col2"> <p>Ett UTC-datum och en UTC-tid för intrycket, klickningen eller konverteringshändelsen. Använd <code> yyyy-MM-dd HH:mm:ss</code> formatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Användar-ID </p> </td> 
   <td colname="col2"> <p>Ditt ID för en besökare på platsen, kallas också för <span class="term"> dataleverantörens unika användar-ID</span> eller DPUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>Datakällans ID eller integrationskoden för annonseraren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>Affärsenhets-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kampanj-ID </p> </td> 
   <td colname="col2"> <p>Kampanj-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>Kreativt ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plats-ID </p> </td> 
   <td colname="col2"> <p>Plats-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> Numeriskt placerings-ID från annonsservern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Infog-order-ID </p> </td> 
   <td colname="col2"> <p>Infogningsorder-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taktiskt-ID </p> </td> 
   <td colname="col2"> <p>Taktiskt ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lodrätt-ID </p> </td> 
   <td colname="col2"> <p>ID för en lodrät eller kategoribaserad bransch. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kvantitet </p> </td> 
   <td colname="col2"> <p> Antalet artiklar som har sålts i en konverteringshändelse. </p> <p> <i>Endast för konvertering av datafiler.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intäkter </p> </td> 
   <td colname="col2"> <p>Inköp eller annat konverteringsbelopp. Datatyp: Flyt. </p> <p> <i>Endast för konvertering av datafiler.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Andra data </p> </td> 
   <td colname="col2"> <p>URL för konverteringslandsidan. Datatyp: Sträng. </p> <p> <i>Endast för konvertering av datafiler.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Händelsetyp </p> </td> 
   <td colname="col2"> <p>Konverteringstyp. Anger om en konvertering matchar eller inte. Alternativen är: </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: Impression </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: Klicka på </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: Okänd eller okänd </li> 
    </ul> <p> <i>Endast för konvertering av datafiler.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Ett obligatoriskt versionsnummer som visas i slutet av varje rad i en bild, ett klick eller en konverteringsdatafil. Den aktuella versionen är 1.1. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Ladda upp dina intryckta, klickningar eller konverteringsdatafiler till en Amazon S3-katalog för ditt [!DNL Audience Manager] konto. I det här avsnittet finns information om leverans-/katalogsökvägar, bearbetningstider och uppdateringar.

>[!IMPORTANT]
>
> Kontakta Audience Manager eller kundtjänst för att komma igång och konfigurera en [!DNL Amazon S3] katalog för dina datafiler.

**Syntax och exempel för leveranssökväg**

Data lagras i ett separat namnutrymme för varje kund i en [!DNL Amazon S3] katalog. Filsökvägen följer den syntax som visas nedan. Obs! *Kursiv* anger en variabelplatshållare. Andra element är konstanter eller nycklar och ändras inte.

**Syntax:** `.../log_ingestion/pid=AAM ID/dpid=d_src/logs/file type_yyyymmdd`

I följande tabell definieras vart och ett av dessa element i en filleveranssökväg.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Filparameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Detta är början på kataloglagringssökvägen. Du får den fullständiga sökvägen när allt är klart. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Detta nyckelvärdepar innehåller ditt <span class="keyword"> Audience Manager</span> kund-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Detta nyckelvärdepar innehåller det datakälla-ID som skickades vid ett händelseanrop. Den identifierar byrån som uppgifterna kommer från och knyter dem till en metadatafil som stöds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> En katalog på högre nivå för datafiler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>Ett filtypsnamn som anger vilken typ av data det innehåller och en leveranstidsstämpel. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempel på överföringssökväg och filnamn**

När du överför en fil ser sökvägen ut ungefär så här:

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**Filbehandlingstider och uppdateringar**

Datafilerna behandlas fyra gånger dagligen med regelbundna intervall.

Om du vill uppdatera dina data skickar du in en fil som innehåller alla visningar, klick eller konverteringar för en viss dag. I det här fallet är en dag dygnet runt, från en midnatt till nästa. Det är en god vana att använda UTC-tid för att definiera ditt dagsintervall.

## Nästa steg {#next-steps}

Granska kraven för att namnge och skapa metadatafiler. Information om hur du kommer igång finns i [Översikt och mappningar för metadatafiler](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
