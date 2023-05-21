---
description: Inköpare av datauppgifter från Audience Marketplace går med på att rapportera alla annonsvisningar som gjorts med hjälp av egenskaper som ingår i dataflödet och som prissatts på basis av en kostnad per tusen annonsvisningar (CPM). CPM-användningen ska användas den 5:e dagen i varje kalendermånad och inkluderar data för föregående månad. Avgiftsbelagda abonnenter behöver inte rapportera användningen.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Fakturering för köpare av dataflöden
keywords: Rapportering på segmentnivå, segmentnivå, segmentnivå
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2002'
ht-degree: 0%

---

# Fakturering för köpare av dataflöden {#billing-for-data-feed-buyers}

Dataköpare i Audience Marketplace går med på att rapportera alla annonsvisningar som gjorts med hjälp av egenskaper som finns i dataflödet och som prissatts enligt en självkostnad per tusen annonsvisningar ([!DNL CPM]). [!DNL CPM] användning förfaller den 5:e dagen i varje kalendermånad och innehåller uppgifter för föregående månad. Prenumeranter på fasta avgifter behöver inte rapportera användning.

<br>

## Så här rapporterar du CPM-användning {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] Dataköpare går med på att rapportera alla annonsvisningar som gjorts med hjälp av egenskaper i dataflödet och som prissatts utifrån en kostnad per tusen annonsvisningar ([!DNL CPM]). [!DNL CPM] användning förfaller den 5:e dagen i varje kalendermånad och omfattar uppgifter för föregående månad. Avgiftsbelagda abonnenter behöver inte rapportera användningen.

[!UICONTROL Audience Marketplace] erbjuder två sätt att rapportera [!DNL CPM] användning:

* **Rapportering på segmentnivå**: det här är vad som rekommenderas [!DNL CPM] användningsrapporteringsmetod. När du rapporterar [!DNL CPM] på segmentnivå fylls rapportavsnittet på dataflödesnivå automatiskt i med motsvarande användningsbelopp, baserat på de algoritmer som beskrivs i [Kostnadsattribuering för CPM-datafeeds](#cost-attribution).
* **Rapportering på dataflödesnivå**: den här metoden kräver att du rapporterar [!DNL CPM] användning för varje dataflöde, baserat på de algoritmer som beskrivs i [Kostnadsattribuering för CPM-datafeeds](#cost-attribution). Den här metoden är dock mer krävande och felbenägen än rapportering på segmentnivå.

<br>

## Rapportera CPM-användning på segmentnivå {#segment-level-report}

The [!UICONTROL Segment Usage] Med -fliken kan du rapportera användning på segmentnivå samtidigt som du visar de segment som grupperats efter de mål som de är mappade till.

Efter rapportering [!DNL CPM] användning på segmentnivå, [!UICONTROL Audience Marketplace] tilldelar automatiskt motsvarande dataflöden korrekt användning, baserat på [Kostnadsattribuering för CPM-datafeeds](#cost-attribution).

Till rapport [!DNL CPM] användning på segmentnivå:

1. Gå till **[!UICONTROL Audience Marketplace > Payables]**.
1. Välj **[!UICONTROL Segment Usage]** -fliken.
1. Fyll i användningen för era segment. Du kan använda [!UICONTROL Search] för att filtrera segmenten om du bara behöver rapportera användningen för vissa av dem.
1. Klicka på **[!UICONTROL Edit Segments Usage]**.
1. Ange [!DNL CPM] användningsmängd i [!UICONTROL Usage] kolumn.
1. Klicka **[!UICONTROL Save]** när du är klar och gå igenom bekräftelsedialogrutan.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Klicka på **[!UICONTROL Confirm]**.

Se även vår videodemonstration av hur du kan rapportera användning på segmentnivå:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Rapportera CPM-användning på dataflödesnivå {#feed-level-report}

Rapportering på dataflödesnivå är mer tidsödande och leder till felprocesser, eftersom du måste beräkna individuellt [!DNL CPM] Användning för varje datafeed. Vi rekommenderar att du [Rapportera CPM-användning på segmentnivå](#segment-level-report) i stället.

Till rapport [!DNL CPM] användning på segmentnivå:

1. Gå till **[!UICONTROL Audience Marketplace > Payables]**.
2. Välj **[!UICONTROL Feed Usage]** -fliken.
3. Använd kommandot [!UICONTROL Search] för att filtrera dataflödena och identifiera de som du behöver rapportera användning för.
4. Klicka på **[!UICONTROL Edit Feeds Usage]**.
5. Beräkna [!DNL CPM] Användning av varje dataflöde baserat på [Kostnadsattribuering för CPM-datafeeds](#cost-attribution)och ange det i dialogrutan [!UICONTROL Usage] kolumn.
6. Klicka **[!UICONTROL Save]** när du är klar och gå igenom bekräftelsedialogrutan.

   ![bekräfta-feed-användning](assets/confirm-feed-usage.png)

7. Klicka på **[!UICONTROL Confirm]**.

<br>

## Massrapportering

Minska antalet fel och förluster vid rapportering [!DNL CPM] kan du använda alternativet för massrapportering för att hämta en [!DNL CSV] som innehåller dataflödena och segmenten, fylla i användningen och överföra den tillbaka till [!DNL Audience Manager]. Du kan använda massrapportering för att rapportera både feed- och segmentanvändning.

Uppdatera [!DNL CPM] massanvändning:

1. Gå till **[!UICONTROL Audience Marketplace > Payables]**.
1. Välj **[!UICONTROL Feed Usage]** eller **[!UICONTROL Segment Usage]** beroende på vilken typ av rapportering du vill uppdatera.
1. Klicka **[!UICONTROL Edit Feeds Usage]** eller **[!UICONTROL Edit Segments Usage]**.
1. Klicka **[!UICONTROL download the current usage]** för att vara säker på att du använder en giltig CSV-fil.
1. Öppna filen på datorn och fyll i användningsrapporten.
1. Klicka **[!UICONTROL Choose a CSV file]** för att överföra den uppdaterade användningsrapporten.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] validerar filen så snart du överför den och frågar om den upptäcker några fel i filen.

<br>

### Valideringsfel för massrapportering

| Felmeddelande | Beskrivning | Korrigera |
| ------------- | -------------| -----|
| Ogiltiga indata | [!DNL Audience Manager] upptäckte en ändring i [!DNL CSV] filschema, t.ex. saknade kolumner eller ändringar i kolumnrubriker. | Undvik att ändra tabellstrukturen. |
| Hittades inte | För [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] kunde inte identifiera [!UICONTROL Segment ID] och [!UICONTROL Destination ID] kombinationen. För [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] kunde inte identifiera [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]och [!UICONTROL Use Case] kombinationen. | För [!UICONTROL Segment Level Reporting]kontrollera [!UICONTROL Segment ID] och [!UICONTROL Destination ID] kombination. För [!UICONTROL Feed Level Reporting]kontrollera [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]och [!UICONTROL Use Case] kombination. |
| Dubblettposter hittades | [!DNL Audience Manager] identifierade dubblettposter med olika avtrycksvärden. | Granska rapporten och se till att du inte rapporterar olika användningsvärden för samma datafeed eller segment. |
| Värden stöds inte | [!DNL Audience Manager] identifierade icke-numeriska värden i [!DNL Audience Manager] kolumn. | Granska rapporten och se till att du bara anger numeriska värden i [!DNL Audience Manager] kolumn. |
| Sidhuvuden för obligatoriska fält saknas | [!DNL Audience Manager] saknade tabellrubriker har identifierats för obligatoriska fält. För [!UICONTROL Segment Level Reporting]är de obligatoriska fälten: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. För [!UICONTROL Feed Level Reporting]är de obligatoriska fälten: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Granska rapporten och kontrollera att tabellrubrikerna inte har ändrats. |

>[!NOTE]
>Ta bort rader från [!DNL CSV] användningsrapporten har ingen effekt på den befintliga användningsrapporten. [!DNL Audience Manager] bearbetar bara de fält som ingår i rapporten.

<br>

## [!DNL CPM] Rapportera bästa praxis

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Rapportera alltid det totala antalet visningar</b> </p> </td> 
   <td colname="col2"> <p>För CPM-inställningssummor: </p>
   <p> Rapportera det totala antalet visningar, utan decimaler. Audience Manager beräknar automatiskt CPM-värdet baserat på det totala antal som du rapporterar.</p><p>Om du behöver rapportera 1 234 567 visningar ska du rapportera exakt så. Du behöver inte dividera det totala antalet visningar med 1 000 för att beräkna CPM.</p><p>De egenskaper som används för att optimera webb- eller appinnehåll (innehållsoptimering) med verktyg som Adobe Target eller ett analysmål bidrar inte till användningssummorna för CPM-planer. Dataleverantörerna kompenseras normalt för optimering av innehåll med hjälp av rabattplaner.</p><p>Se <a href="#cost-attribution">Kostnadsattribuering för CPM-datafeeds</a> för mer information. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Använd månadsvis rapportering</b> </p> </td> 
   <td colname="col2"> <p>Rapportsystemet stängs efter den 5:e varje månad. Om du inte rapporterar CPM-användningen innan dess måste du lägga till beloppet i rapporten för nästa månad. Exempel: du använder 1 000 visningar i oktober, missar rapportdeadline i oktober och använder 1 000 visningar i november. I så fall rapporterar du det totala antalet oktober och november (2000) i december mellan den 1 och 5.</p><p><b>Tips</b>: Du bör alltid försöka rapportera CPM-användningen för föregående månad mellan den 1 och 5 i följande månad.</p><p>Du kan rapportera CPM-användning så sent som den 5:e i den nya kalendermånaden, men det rekommenderas inte. Om CPM-användningen rapporteras före den 5:e varje månad får Audience Manager tid att kontrollera och bearbeta data.</p> </td>
  </tr> 
 </tbody> 
</table>

<br>

## Kostnadsfördelning för CPM-dataflöden {#cost-attribution}

I [!UICONTROL Audience Marketplace] Du måste rapportera intrycksbelopp varje månad för varje segment. Vi rekommenderar rapportering [!DNL CPM] användning på segmentnivå, så att kostnadsattribuering sker automatiskt.

<!-- marketplace_cpm_billing.xml -->

### Faktureringssammanfattning {#billing-summary}

Du måste skicka in [!DNL CPM] mängden datautnyttjande mellan den 1 och 5 i varje kalendermånad. Om du vill göra det på rätt sätt rekommenderar vi att du [Rapportera CPM-användning på segmentnivå](#segment-level-report).

>[!TIP]
>När du rapporterar [!DNL CPM] på segmentnivå fylls rapportavsnittet på dataflödesnivå automatiskt i med motsvarande användningsbelopp.

Borde du behöva [!UICONTROL Report CPM Usage at Data Feed Level]måste du separat sammanställa alla avtryck som levererats för varje flöde under den föregående kalendermånaden och rapportera dem enligt den faktureringsallokering som beskrivs i den här artikeln.

Efter att du rapporterat [!DNL CPM] nummer för föregående kalendermånad, [!DNL Adobe] kommer att göra följande:

* Skapa en faktura och fakturera dig baserat på [!DNL CPM] Frekvens för varje prenumererad datafeed.
* Betala avgifter för leverantörer (säljare) baserat på dina rapporterade [!DNL CPM] använd.

>[!IMPORTANT]
>
>Som köpare måste alla rapporterade summor för intryck vara sanna och korrekta. Om du inte rapporterar summor för det intryck du har gjort senast den 5:e dagen i varje månad måste du inkludera summor för den ej rapporterade månaden i följande månad.

<br>

## Tilldela Impressions på matningsnivå baserat på regler för kvalificering av trait {#assign-impressions}

The [!UICONTROL Activation] kan du använda egenskaper i motsvarande dataflöde för att skapa segment i [Segment Builder](../../../features/segments/segment-builder.md) och mappa dessa segment till ett mål. De booleska operatorerna [!UICONTROL AND], [!UICONTROL OR]och [!UICONTROL NOT] gör att du kan ange villkoren för egenskaper och segmentkvalifikationer.

När du [Rapportera CPM-användning på dataflödesnivå](#feed-level-report)måste du fördela visningar proportionellt för varje datafeed enligt [!DNL Boolean] operatorer som används i reglerna för kvalificering av egenskaper. I följande tabell visas hur du allokerar avbildningar efter boolesk regel eller trait-typ.

>[!TIP]
>[Rapportera CPM-användning på segmentnivå](#segment-level-report) att automatiskt låta Audience Manager rapportera dataflödesnivån.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regelkvalificeringslogik eller regeltyp </th> 
   <th colname="col2" class="entry"> Faktureringsdistribution </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OCH</span> </p> </td> 
   <td colname="col2"> <p>Använd 100 % av det levererade intrycket på alla leverantörsegenskaper i ett regelbaserat segment som använder en boolesk <span class="wintitle"> OCH</span> villkor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ELLER</span> </p> </td> 
   <td colname="col2"> <p>Använd viktad fördelning av de levererade intryckssummorna på alla leverantörsegenskaper i ett regelbaserat segment som använder ett booleskt OR-villkor. Viktad allokering beräknas med följande formel:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> INTE</span> </p> </td> 
   <td colname="col2"> <p>Använd 100 % av det levererade intrycket på alla leverantörsegenskaper i ett regelbaserat segment som använder en boolesk <span class="wintitle"> NOT</span> villkor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algoritmiska segment </p> </td> 
   <td colname="col2"> <p>Använd 100 % av de totala intrycken på alla leverantörsflöden i ett segment som innehåller algoritmiska egenskaper. </p> </td> 
  </tr>
 </tbody>
</table>

<br>

## Faktureringsexempel {#billing-examples}

Exemplen nedan är avsedda att illustrera hur [!DNL CPM] allokering av användning görs på dataflödesnivå.

>[!IMPORTANT]
>Vi rekommenderar att du [Rapportera CPM-användning på segmentnivå](#segment-level-report) i stället, för att denna process ska göras automatiskt.

Låt oss titta på följande scenario:

![faktureringsexempel](assets/billing-examples.png)

<br>

### Fall 1: Segment med och kvalificeringsregler

Det här segmentet innehåller tre egenskaper från separata dataleverantörer. Eftersom godkännande av segment baseras på en [!UICONTROL AND] måste besökarna inse egenskaperna hos alla tre flödena för att kvalificera sig för segmentet.

![](assets/billing-segment-and.png)

Med [!UICONTROL AND] måste du tilldela 100 % av de visningar som tas emot under månaden till alla tre dataleverantörerna. I [!UICONTROL Audience Marketplace > Payables] ger du varje leverantör 1 000 000 utskrifter.

Det här exemplet gäller segment som använder [!DNL Boolean] [!UICONTROL NOT] operatorer eller för segment som innehåller algoritmiska egenskaper.

<br>

### Fall 2: Segment med eller kvalificeringsregler

Det här segmentet innehåller tre egenskaper från separata dataleverantörer. Eftersom godkännande av segment baseras på en [!UICONTROL OR] måste besökarna uppnå minst en av de tre egenskaperna för att kvalificera sig för segmentet.

Vi kan inte avgöra vilken egenskap som är ansvarig för ett intryck eftersom kvalificeringen baseras på en [!UICONTROL OR] villkor. Detta resulterar i att [!UICONTROL Audience Marketplace > Payables] kan du kreditera varje leverantör med en viktad fördelning av det totala intrycket, baserat på antalet medarbetare.

![faktureringssegment-eller](assets/billing-segment-or.png)

<br>

### Fall 3: Segment med modellering och aktivering - användningsfall

I det här exemplet beskrivs attribuering baserat på två användningsfall för datafeed - modellering och aktivering. I det här exemplet tittar vi på två dataleverantörer, med följande information:

![datafeed](assets/feed-use-cases.png)

I tabellen nedan innehåller segment X två egenskaper, T1 och T2, med segmentregeln T1 ELLER T2, där:

* T1 är en egenskap från datafeed A,
* T2 är en algoritmisk egenskap som bygger på egenskaper från datafeed A och datafeed B från tredje part.

Segmentet mappas till ett mål och 1 000 000 visningar anges för det här segmentet på en månad, med [Rapportering på segmentnivå](#segment-level-report).

Av dessa 1 000 000 visningar:

* T1 utgör 40 % av segmentpopulationen, vilket innebär 400 000 visningar för feed A.
* T2 utgör 60 % av segmentpopulationen, vilket motsvarar 600 000 visningar för feed A och feed B.

På dataflödesnivå är det sätt som avbildningarna fördelas på:

* Data Feed A får 600 000 visningar från trait T2 (som bygger på egenskaper från Data Feed A och Data Feed B, så båda får intrycken) och 400 000 visningar från trait T1 (som är ett drag från Data Feed A), totalt 1 000 000 visningar.
* Data Feed B får 600 000 visningar från trait T2 (se förklaringen ovan) och 0 avtryck från trait T1.

Den snabba uppdelningen per datafeed och användningsfall är följande:

![nedbrytning av foder](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>För modelleringsanvändning bör du bara rapportera CPM-användning när du aktiverar. Om du bara kör en modell, men inte aktiverar den, behövs ingen användningsrapportering.

<br>

## Fakturering och Impression-allokering för statiska avgiftsdatafeeds {#billing-flat-fee}

Med ett dataflöde med fast avgift debiteras ett fast belopp varje månad, oavsett när prenumerationen börjar eller hur många visningar du använder. Avgifterna fördelas inte på partiell månadsanvändning eller delintervall. Precis som med CPM-fakturering kommer Adobe att generera en faktura och fakturera dig med den månatliga, fasta avgiften för dina prenumererade dataflöden.

Anta till exempel att du bestämde dig för att aktivera vissa egenskaper i ett flöde mitt i månaden. Du faktureras fortfarande till den fullständiga månadskostnaden oavsett när du påbörjade prenumerationen eller aktiverade specifika egenskaper.
