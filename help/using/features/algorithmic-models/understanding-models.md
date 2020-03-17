---
description: Bygg och hantera de egenskaper och segment som används i algoritmisk modellering, som också kallas look-alike-modellering. Modellfunktionerna finns i Målgruppsdata > Modeller.
keywords: relative weight, lookalike
seo-description: Bygg och hantera de egenskaper och segment som används i algoritmisk modellering, som också kallas look-alike-modellering. Modellfunktionerna finns i Målgruppsdata > Modeller.
seo-title: Om algoritmiska modeller
solution: Audience Manager
title: Om algoritmiska modeller
topic: DIL API
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Om algoritmiska modeller {#about-algorithmic-models}

Bygg och hantera de egenskaper och segment som används i algoritmisk modellering, som också kallas look-alike-modellering. Modellfunktionerna finns i **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Förstå algoritmiska modeller {#understanding-models}

Avsnitten nedan representerar en granskning av algoritmisk modellering i [!DNL Audience Manager]. De beskriver hur modellering fungerar, fördelarna och arbetsflödet.

<!-- understanding-models.xml -->

## Hitta nya användare med algoritmisk modellering {#find-new-users}

Med algoritmisk modellering kan ni identifiera nya, unika målgrupper genom automatiserad dataanalys. Processen startar när du väljer ett trait- eller segment, ett tidsintervall samt datakällor från första och tredje part. Dina val innehåller indata för den algoritmiska modellen. När analysprocessen körs letar programmet efter berättigade användare baserat på delade egenskaper från den valda populationen. När du är klar är dessa data tillgängliga i [Trait Builder](../../features/traits/about-trait-builder.md) där du kan använda dem för att skapa egenskaper baserat på [precision och räckvidd](../../features/traits/trait-accuracy-reach.md). Dessutom kan du skapa segment som kombinerar algoritmiska egenskaper med regelbaserade egenskaper och lägga till andra kvalificeringskrav med booleska uttryck och jämförelseoperatorer. Algoritmisk modellering ger ett dynamiskt sätt att extrahera värde från alla tillgängliga trait-data.

## Fördelar {#advantages}

De största fördelarna med att använda [!DNL Audience Manager] modellering är:

* **Noggrannhet:** Algoritmen körs regelbundet, vilket bidrar till att hålla resultaten aktuella och relevanta.
* **Automatisering:** Du behöver inte hantera en stor uppsättning statiska regler. Algoritmen hittar målgrupper åt er.
* **Spara tid och minska arbetet:** Med vår modelleringsprocess behöver ni inte gissa vilka egenskaper/segment som kan fungera eller lägga tid på att identifiera nya målgrupper med kampanjer. Modellen kan göra detta åt dig.
* **Tillförlitlighet:** Modellering fungerar med processer för identifiering och kvalificering på serversidan som utvärderar dina egna data och utvalda tredjepartsdata som du har tillgång till. Det innebär att du inte behöver se besökarna på din webbplats för att kvalificera dem för ett yrke.

## Arbetsflöde {#workflow}

Du hanterar modeller i **[!UICONTROL Audience Data > Models]**. På en hög nivå omfattar arbetsflödesprocessen följande:

* Markera de baslinjedata som du vill att algoritmen ska utvärdera. Detta omfattar egenskaper eller segment, tidsintervall och datakällor (egna data och tredjepartsdata som du redan har tillgång till via [!DNL Audience Manager]). När du skapar en modell kan du utesluta de egenskaper som du inte vill ska påverkas av modellen.
* Spara modellen. När den har sparats körs den algoritmiska utvärderingsprocessen automatiskt. Observera att det kan ta upp till 7 dagar innan den här processen är klar. [!DNL Audience Manager] skickar ett e-postmeddelande till dig när algoritmen har slutförts och resultaten är tillgängliga för att skapa egenskaper.
* Skapa algoritmiska egenskaper i [!UICONTROL Trait Builder].
* Kombinera egenskaper i segment i [!UICONTROL Segment Builder].
* Skapa och skicka segmentdata till ett mål.

## Felsökning {#troubleshooting}

Vi inaktiverar alla algoritmiska modeller som inte kan generera data för tre på varandra följande körningar. Observera att du inte kan ange status för modellen till aktiv i efterhand. Vi rekommenderar att du skapar modeller från datakällor med tillräckliga egenskaper för att kunna samla in data från dina modeller.

## TraitWeight - introduktion {#understanding-traitweight}

[!UICONTROL TraitWeight] är en egen algoritm som utformats för att automatiskt upptäcka nya egenskaper. Den jämför spårade data från era nuvarande egenskaper och segment mot alla andra data från första och tredje part som ni har tillgång till via [!DNL Audience Manager]. I det här avsnittet finns en beskrivning av den algoritmiska [!UICONTROL TraitWeight] identifieringsprocessen.

<!-- traitweight.xml -->

![](assets/algo_model.png)

Följande steg beskriver [!UICONTROL TraitWeight] utvärderingsprocessen.

### Steg 1: Skapa en baslinje för Trait Comparison

Om du vill skapa en baslinje mäter [!UICONTROL TraitWeight] alla egenskaper som är kopplade till en målgrupp med 30, 60 eller 90 dagars intervall. Därefter rangordnas egenskaperna efter frekvens och korrelation. Frekvensantalet mäter gemensamma värden. Korrelation mäter sannolikheten för att en egenskap förekommer endast i den ursprungliga målgruppen. Särdrag som ofta verkar vara mycket gemensamma, vilket är en viktig egenskap som används för att ställa in ett viktat poängvärde när de kombineras med egenskaper som upptäcks i de valda datakällorna.

### Steg 2: Hitta samma egenskaper i datakällan

När en baslinje har skapats för jämförelse letar algoritmen efter identiska egenskaper i de valda datakällorna. I det här steget [!UICONTROL TraitWeight] utför ett frekvensantal för alla identifierade egenskaper och jämför dem med baslinjen. Till skillnad från baslinjen rangordnas dock ovanliga egenskaper högre än de som förekommer oftare. Sällsynta egenskaper sägs vara mycket specifika. [!UICONTROL TraitWeight] bedömer kombinationer av gemensamma grundläggande egenskaper och ovanliga (mycket specifika) egenskaper hos datakällan som mer inflytelserika eller önskvärda än egenskaper som är gemensamma för båda datauppsättningarna. Vår modell känner faktiskt igen dessa stora, vanliga egenskaper och tilldelar inte alltför hög prioritet till datauppsättningar med höga korrelationer. Sällsynta egenskaper får högre prioritet eftersom de troligtvis representerar nya, unika användare än vad som är fallet med en hög gemensam nivå över hela linjen.

### Steg 3: Tilldela bredd

I det här steget rangordnas [!UICONTROL TraitWeight] nyligen upptäckta egenskaper efter påverkan eller önskvärdhet. Viktskalan är ett procentvärde mellan 0 % och 100 %. Fällor rankade närmare 100 % innebär att de är mer som målgruppen i din baslinjepopulation. Dessutom är kraftigt viktade egenskaper värdefulla eftersom de representerar nya, unika användare som kan bete sig på samma sätt som er etablerade, grundläggande målgrupp. Tänk på att egenskaper med hög enhetlighet i baslinjen och hög specificitet i jämförda datakällor är mer värdefulla än egenskaper som är gemensamma för varje datauppsättning. [!UICONTROL TraitWeight]

### Steg 4: Poänganvändare

Varje användare i de valda datakällorna får ett poängvärde som är lika med summan av alla vikter för de inflytelserika egenskaperna för den användarens profil. Användarpoängen normaliseras sedan till mellan 0 och 100 %.

### Steg 5: Visa och arbeta med resultat

Audience Manager visar viktade modellresultat i [!UICONTROL Trait Builder]. När du vill skapa en algoritmisk egenskap [!UICONTROL Trait Builder] kan du skapa egenskaper baserat på den viktade poäng som genereras av algoritmen under en datakörning. Du kan välja en högre precision om du bara vill kvalificera användare som har mycket höga användarpoäng och därför är mycket lika den ursprungliga målgruppen, i stället för den övriga målgruppen. Om du vill nå en större publik (räckvidd) kan du minska noggrannheten.

### Steg 6: Utvärdera vikten av ett tåg i olika bearbetningscykler

Utvärderar regelbundet vikten av en egenskap baserat på storleken och förändringen i populationen av den egenskapen [!UICONTROL TraitWeight] . Detta inträffar när antalet användare som är kvalificerade för den egenskapen ökar eller minskar med tiden. Detta beteende syns tydligast i egenskaper som blir mycket stora. Anta till exempel att algoritmen använder trait A för modellering. När populationen av trait A ökar, utvärderas vikten av den egenskapen på nytt och kan tilldela en lägre poäng eller ignorera den. [!UICONTROL TraitWeight] I det här fallet är trait A för vanligt eller stort för att säga något om sin befolkning. När värdet för Trait A har [!UICONTROL TraitWeight] reducerats (eller ignorerats i modellen) minskar det algoritmiska traits population. Förteckningen över inflytelserika egenskaper återspeglar utvecklingen av baspopulationen. Använd listan över de inflytelserika egenskaperna för att förstå varför dessa förändringar inträffar.

Relaterade länkar:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [Noggrannhet och räckvidd](../../features/traits/trait-accuracy-reach.md)

## Uppdateringsschema för algoritmiska modeller och egenskaper {#update-schedule}

Skapa och uppdatera scheman för nya eller befintliga algoritmiska modeller och egenskaper.

<!-- c_model_update_schedule.xml -->

### Schema för att skapa och uppdatera algoritmiska modeller

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Typ av aktivitet </th>
   <th colname="col2" class="entry"> Beskrivning </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Skapa eller klona en modell</b> </td>
   <td colname="col2"> <p>För nya eller klonade algoritmiska modeller körs skapandeprocessen en gång om dagen på: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17:00 EST (november - mars) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6:00 EDT (mars - november) </li> 
     </ul> </p> <p>Modeller som byggts eller klonats efter att tidsgränsen för skapandet har uppnåtts behandlas följande dag. </p> <p>Om den första körningen av en modell inte genererar några data körs den en andra gång, nästa dag. Om det andra försöket inte genererar några data kommer det att göras ett tredje försök nästa dag. Modellen kommer att sluta köras om det tredje försöket inte genererar några data. I det här fallet inaktiverar vi modellen. Se mer i <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Felsökning av algoritmiska modeller</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Uppdatera en modell</b> </td> 
   <td colname="col2"> <p>Under idealiska förhållanden körs befintliga modeller på vardagar, minst en gång var sjunde dag. Om du t.ex. skapar en modell (med deadline) på måndag, uppdateras den följande måndagen senast. </p> <p>En modell körs igen om den uppfyller något av följande villkor: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Den senaste körningen misslyckades. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Den har körts innan OCH har inte körts alls under de senaste 7 dagarna OCH modellen har minst en aktiv egenskap kopplad till sig. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Schema för generering och uppdatering av algoritmisk trait

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ av aktivitet </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Skapa ett varumärke</b> </td> 
   <td colname="col2"> <p>Processen att skapa egenskaper körs varje dag, måndag till fredag. I allmänhet visas nya algoritmiska egenskaper i användargränssnittet inom 48 timmar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Uppdatera ett spår</b> </td> 
   <td colname="col2"> <p>Befintliga egenskaper uppdateras minst en gång var 7:e dag och följer schemat för modelluppdateringar. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modelllistvy {#models-list-view}

Listvyn är en central arbetsyta som du kan använda för att skapa, granska och hantera modeller.

<!-- c_models_list_view.xml -->

Listsidan Modeller innehåller funktioner och verktyg som hjälper dig att:

* Skapa nya modeller.
* Hantera befintliga modeller (redigera, pausa, ta bort eller klona).
* Sök efter modeller efter namn.
* Skapa algoritmiska egenskaper med valfri modell.

## Sammanfattningsvy för modeller {#models-summary-view}

På sammanfattningssidan visas modellinformation som namn, räckvidd/precision, bearbetningshistorik och egenskaper som skapats från modellen. Sidan innehåller även inställningar som gör att du kan skapa och hantera modeller. Klicka på ett modellnamn i sammanfattningslistan för att se information om det.

<!-- c_models_summary.xml -->

Modellsammanfattningssidan innehåller följande avsnitt.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Avsnitt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Grundläggande information</span> </p> </td>
   <td colname="col2"> <p>Innehåller grundläggande information om modellen, till exempel dess namn och när den senast kördes. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Modellområde och precision</span> </p> </td> 
   <td colname="col2"> <p>Visar <a href="../../features/traits/trait-accuracy-reach.md"> noggrannhet och nålar</a> data för den senaste modellkörningen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Modellbearbetningshistorik</span> </p> </td> 
   <td colname="col2"> <p>Visar bearbetningsdatum och -tid för de senaste 10 körningarna och om data har genererats på dessa körningar. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Influentiella egenskaper</span> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Influential Traits</span> table: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Visar de 50 mest inflytelserika egenskaperna som bäst representeras i modellens baslinjepopulation. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Rangordna varje egenskap efter dess <span class="wintitle"> relativa vikt</span> . Den <span class="wintitle"> relativa vikten</span> sorterar nyligen identifierade egenskaper i ordning av påverkan eller önskvärdhet. Viktskalan är ett procentvärde mellan 0 % och 100 %. Fällor rankade närmare 100 % innebär att de är mer som målgruppen i din baslinjepopulation. Se <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Förstå TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Visar en 30-dagars unix och den totala trait-populationen för varje egenskap. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Traits Using Model</span> </p> </td>
   <td colname="col2"> <p>Visar en lista över algoritmiska egenskaper baserat på den valda modellen. Klicka på ett trait-namn eller trait-ID om du vill ha mer information om trait. Välj <b><span class="uicontrol"> Skapa nytt spår med modell</span></b> för att gå till processen för att skapa algoritmiska egenskaper. </p> <p>Avsnittsetiketten ändras baserat på modellens namn. Anta att du skapar en modell och ger den namnet Modell A. När du läser in sammanfattningssidan ändras namnet på det här avsnittet till <span class="wintitle"> Traits Using Model A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Mål](../../features/destinations/destinations.md)
>* [Traits](../../features/traits/trait-details-page.md)
>* [Segment](../../features/segments/segments-purpose.md)

