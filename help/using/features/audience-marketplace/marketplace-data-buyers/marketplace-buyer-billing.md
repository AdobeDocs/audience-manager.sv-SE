---
description: Inköpare av datauppgifter från Audience Marketplace går med på att rapportera alla annonsvisningar som gjorts med hjälp av egenskaper som ingår i dataflödet och som prissatts på basis av en kostnad per tusen annonsvisningar (CPM). CPM-användningen ska användas den 5:e dagen i varje kalendermånad och inkluderar data för föregående månad. Avgiftsbelagda abonnenter behöver inte rapportera användningen.
seo-description: Inköpare av datauppgifter från Audience Marketplace går med på att rapportera alla annonsvisningar som gjorts med hjälp av egenskaper som ingår i dataflödet och som prissatts på basis av en kostnad per tusen annonsvisningar (CPM). CPM-användningen ska användas den 5:e dagen i varje kalendermånad och inkluderar data för föregående månad. Avgiftsbelagda abonnenter behöver inte rapportera användningen.
seo-title: Fakturering för köpare av dataflöden
solution: Audience Manager
title: Fakturering för köpare av dataflöden
keywords: Segment-level Reporting, segment-level, segment level
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: dac08e9a31cb80b048013d95b7a617e4fb68e2fe
workflow-type: tm+mt
source-wordcount: '2027'
ht-degree: 1%

---


# Fakturering för köpare av dataflöden {#billing-for-data-feed-buyers}

Inköpare av datauppgifter från Audience Marketplace går med på att rapportera alla annonsvisningar som betjänas med hjälp av egenskaper som ingår i dataflödet och som prissätts på tusen annonsvisningar ([!DNL CPM]). [!DNL CPM] ska användas den 5:e dagen i varje kalendermånad och innehåller data för föregående månad. Avgiftsbelagda abonnenter behöver inte rapportera användningen.

<br> 

## Rapportera CPM-användning {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] Datainköparna går med på att rapportera alla annonsvisningar som levereras med hjälp av egenskaper som ingår i dataflödet och som prissätts till ett pris per tusen annonsvisningar ([!DNL CPM]). [!DNL CPM] ska användas den 5 dagen i varje kalendermånad och innehåller data för föregående månad. Avgiftsbelagda abonnenter behöver inte rapportera användningen.

[!UICONTROL Audience Marketplace] har två sätt att rapportera [!DNL CPM] användning:

* **Rapportering** på segmentnivå: det här är den rekommenderade [!DNL CPM] användningsrapporteringsmetoden. När du rapporterar [!DNL CPM] användning på segmentnivå fylls rapportavsnittet på dataflödesnivå automatiskt i med motsvarande användningsbelopp, baserat på de algoritmer som beskrivs i [Kostnadsattribuering för CPM-datafeeds](#cost-attribution).
* **Rapportering** på dataflödesnivå: Den här metoden kräver att du rapporterar [!DNL CPM] användningen för varje datafeed individuellt, baserat på de algoritmer som beskrivs i [Kostnadsattribuering för CPM-datafeeds](#cost-attribution). Den här metoden är dock mer krävande och felbenägen än rapportering på segmentnivå.

<br> 

## Rapportera CPM-användning på segmentnivå {#segment-level-report}

På fliken [!UICONTROL Segment Usage] kan du rapportera användning på segmentnivå och visa de segment som grupperats efter de mål som de är mappade till.

När du har rapporterat [!DNL CPM] användning på segmentnivå tilldelas motsvarande dataflöden automatiskt rätt användning, baserat på [!UICONTROL Audience Marketplace] kostnadsattribuering för CPM-datafeeds [](#cost-attribution).

Så här rapporterar du [!DNL CPM] användning på segmentnivå:

1. Gå till **[!UICONTROL Audience Marketplace > Payables]**.
1. Klicka på **[!UICONTROL Segment Usage]** fliken.
1. Fyll i användningen för era segment. Du kan använda [!UICONTROL Search] rutan för att filtrera segmenten om du bara behöver rapportera användningen för vissa av dem.
1. Klicka på **[!UICONTROL Edit Segments Usage]**.
1. Ange [!DNL CPM] användningsmängden i [!UICONTROL Usage] kolumnen.
1. Klicka **[!UICONTROL Save]** när du är klar och granska bekräftelsedialogrutan.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. Klicka på **[!UICONTROL Confirm]**.

Se även vår videodemonstration av hur du kan rapportera användning på segmentnivå:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## Rapportera CPM-användning på dataflödesnivå {#feed-level-report}

Rapportering på dataflödesnivå är en mer tidsödande process med risk för fel, eftersom du måste beräkna [!DNL CPM] användningen individuellt för varje datafeed. Vi rekommenderar att du [rapporterar CPM-användning på segmentnivå](#segment-level-report) i stället.

Så här rapporterar du [!DNL CPM] användning på segmentnivå:

1. Gå till **[!UICONTROL Audience Marketplace > Payables]**.
2. Klicka på **[!UICONTROL Feed Usage]** fliken.
3. Använd [!UICONTROL Search] rutan för att filtrera dataflödena och identifiera de som du behöver rapportera användningen för.
4. Klicka på **[!UICONTROL Edit Feeds Usage]**.
5. Beräkna [!DNL CPM] användningen för varje datafeed baserat på [kostnadsattribuering för CPM-dataflöden](#cost-attribution)och ange den i [!UICONTROL Usage] kolumnen.
6. Klicka **[!UICONTROL Save]** när du är klar och granska bekräftelsedialogrutan.

   ![bekräfta-feed-användning](assets/confirm-feed-usage.png)

7. Klicka på **[!UICONTROL Confirm]**.

<br> 

## Massrapportering

Om du vill minska antalet fel och förluster när du rapporterar [!DNL CPM] användningen kan du använda alternativet för massrapportering för att hämta en [!DNL CSV] fil som innehåller dataflödena och datasegmenten, fylla i användningen och överföra den tillbaka till [!DNL Audience Manager]. Du kan använda massrapportering för att rapportera både feed- och segmentanvändning.

Så här uppdaterar du [!DNL CPM] satsanvändning:

1. Gå till **[!UICONTROL Audience Marketplace > Payables]**.
1. Välj **[!UICONTROL Feed Usage]** fliken eller **[!UICONTROL Segment Usage]** fliken, beroende på vilken typ av rapportering du vill uppdatera.
1. Klicka på **[!UICONTROL Edit Feeds Usage]** eller **[!UICONTROL Edit Segments Usage]**.
1. Klicka **[!UICONTROL download the current usage]** för att kontrollera att du använder en giltig CSV-fil.
1. Öppna filen på datorn och fyll i användningsrapporten.
1. Klicka **[!UICONTROL Choose a CSV file]** för att överföra den uppdaterade användningsrapporten.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] validerar filen så snart du överför den och frågar om den upptäcker några fel i filen.

<br> 

### Valideringsfel för massrapportering

| Felmeddelande | Beskrivning | Korrigera |
| ------------- | -------------| -----|
| Ogiltiga indata | [!DNL Audience Manager] upptäckte en ändring i [!DNL CSV] filschemat, t.ex. saknade kolumner eller ändringar i kolumnrubriker. | Undvik att ändra tabellstrukturen. |
| Hittades inte | Det [!UICONTROL Segment Level Reporting]gick inte [!DNL Audience Manager] att identifiera kombinationen [!UICONTROL Segment ID] och [!UICONTROL Destination ID] . Det [!UICONTROL Feed Level Reporting]gick [!DNL Audience Manager] till exempel inte att identifiera kombinationen [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]och [!UICONTROL Use Case] . | Du kan till [!UICONTROL Segment Level Reporting]exempel kontrollera giltigheten för [!UICONTROL Segment ID] och [!UICONTROL Destination ID] kombinationen. Kontrollera till [!UICONTROL Feed Level Reporting]exempel giltigheten för [!UICONTROL Data Provider Name], [!UICONTROL Feed Name]och [!UICONTROL Use Case] kombinationen. |
| Dubblettposter hittades | [!DNL Audience Manager] har identifierat dubblettposter med olika visningsvärden. | Granska rapporten och se till att du inte rapporterar olika användningsvärden för samma datafeed eller segment. |
| Värden som inte stöds | [!DNL Audience Manager] icke-numeriska värden har identifierats i [!DNL Audience Manager] kolumnen. | Granska rapporten och se till att du bara anger numeriska värden i [!DNL Audience Manager] kolumnen. |
| Sidhuvuden för obligatoriska fält saknas | [!DNL Audience Manager] saknade tabellrubriker har identifierats för obligatoriska fält. De obligatoriska [!UICONTROL Segment Level Reporting]fälten är: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. De obligatoriska [!UICONTROL Feed Level Reporting]fälten är: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Granska rapporten och kontrollera att tabellrubrikerna inte har ändrats. |

>[!NOTE]
>Att ta bort rader från [!DNL CSV] användningsrapporten påverkar inte den befintliga användningsrapporten. [!DNL Audience Manager] bearbetar bara de fält som ingår i rapporten.

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
   <p> Rapportera det totala antalet visningar, utan decimaler. Audience Manager beräknar automatiskt CPM-värdet baserat på det totala antal som du rapporterar.</p><p>Om du behöver rapportera 1 234 567 visningar ska du rapportera exakt så. Du behöver inte dividera det totala antalet visningar med 1 000 för att beräkna CPM.</p><p>De egenskaper som används för att optimera webb- eller appinnehåll (innehållsoptimering) med verktyg som Adobe Target eller ett analysmål bidrar inte till användningssummorna för CPM-planer. Dataleverantörerna kompenseras normalt för optimering av innehåll med hjälp av rabattplaner.</p><p>Mer information finns i <a href="#cost-attribution">Kostnadsattribuering för CPM-datafeeds</a> . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Använd månadsvis rapportering</b> </p> </td> 
   <td colname="col2"> <p>Rapportsystemet stängs efter den 5:e varje månad. Om du inte rapporterar CPM-användningen innan dess måste du lägga till beloppet i rapporten för nästa månad. Exempel: du använder 1 000 visningar i oktober, missar rapportdeadline i oktober och använder 1 000 visningar i november. I så fall rapporterar du det totala antalet oktober och november (2000) i december mellan den 1 och 5.</p><p><b>Tips</b>: Du bör alltid försöka rapportera CPM-användningen för föregående månad mellan den 1 och 5 i följande månad.</p><p>Du kan rapportera CPM-användning så sent som den 5 i den nya kalendermånaden, men detta rekommenderas inte. Om CPM-användningen rapporteras före den 5:e varje månad får Audience Manager tid att kontrollera och bearbeta data.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## Kostnadsattribuering för CPM-datafeeds {#cost-attribution}

I [!UICONTROL Audience Marketplace] det måste ni rapportera själv hur mycket det blir varje månad, för vart och ett av era segment. Vi rekommenderar att du rapporterar [!DNL CPM] användning på segmentnivå så att kostnadsattribuering sker automatiskt.

<!-- marketplace_cpm_billing.xml -->

### Faktureringssammanfattning {#billing-summary}

Du måste skicka in visningsbelopp för [!DNL CPM] dataflöden mellan den 1 och 5 i varje kalendermånad. Om du vill göra det på rätt sätt rekommenderar vi att du [rapporterar CPM-användning på segmentnivå](#segment-level-report).

>[!TIP]
>När du rapporterar [!DNL CPM] användning på segmentnivå fylls rapportavsnittet automatiskt i med motsvarande användningsbelopp.

Om du behöver [!UICONTROL Report CPM Usage at Data Feed Level]det måste du sammanställa alla avtryck som levererats för varje flöde under den föregående kalendermånaden separat och rapportera dem enligt den faktureringsallokering som beskrivs i den här artikeln.

När du har rapporterat [!DNL CPM] numret för föregående kalendermånad [!DNL Adobe] gör du följande:

* Skapa en faktura och fakturera dig baserat på [!DNL CPM] taxan för varje abonnerad datafeed.
* Betala avgifter för leverantörer (säljare) baserat på din rapporterade [!DNL CPM] användning.

>[!IMPORTANT]
>
>Som köpare måste alla rapporterade summor för intryck vara sanna och korrekta. Om du inte rapporterar summor för det intryck du har gjort senast den 5:e dagen i varje månad måste du inkludera summor för den ej rapporterade månaden i följande månad.

<br> 

## Tilldela Impressions på matningsnivå baserat på regler för kvalificering av trait {#assign-impressions}

Med [!UICONTROL Activation] användningsexemplet kan du använda egenskaper i motsvarande datafeed för att skapa segment i [Segment Builder](../../../features/segments/segment-builder.md) och mappa dessa segment till ett mål. De booleska operatorerna [!UICONTROL AND]och [!UICONTROL OR][!UICONTROL NOT] gör att du kan ange villkoren för egenskaperna och segmenten.

När du [rapporterar CPM-användning på dataflödesnivå](#feed-level-report)måste du tilldela visningar proportionellt för varje datafeed, enligt de [!DNL Boolean] operatorer som används i reglerna för behörighet. I följande tabell visas hur du allokerar avbildningar efter boolesk regel eller trait-typ.

>[!TIP]
>
> [Rapportera CPM-användning på segmentnivå](#segment-level-report) om du vill att dataflödesrapporteringen ska utföras automatiskt av Audience Manager.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Logik eller typ för regelkvalificering </th> 
   <th colname="col2" class="entry"> Faktureringsdistribution </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OCH</span> </p> </td> 
   <td colname="col2"> <p>Använd 100 % av det levererade intrycket på alla leverantörsegenskaper i ett regelbaserat segment som använder ett booleskt <span class="wintitle"> AND</span> -villkor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ELLER</span> </p> </td> 
   <td colname="col2"> <p>Använd viktad fördelning av de levererade intryckssummorna på alla leverantörsegenskaper i ett regelbaserat segment som använder ett booleskt OR-villkor. Viktad allokering beräknas med följande formel:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Använd 100 % av det levererade intrycket på alla leverantörsegenskaper i ett regelbaserat segment som använder ett booleskt <span class="wintitle"> NOT</span> -villkor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algoritmiska segment </p> </td> 
   <td colname="col2"> <p>Använd 100 % av de totala intrycken på alla leverantörsflöden i ett segment som innehåller algoritmiska egenskaper. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## Faktureringsexempel {#billing-examples}

Exemplen nedan är avsedda att illustrera hur [!DNL CPM] användarallokering görs på dataflödesnivå.

>[!IMPORTANT]
>Vi rekommenderar att du [rapporterar CPM-användning på segmentnivå](#segment-level-report) i stället, så att processen utförs automatiskt.

Låt oss titta på följande scenario:

![faktureringsexempel](assets/billing-examples.png)

<br> 

### Fall 1: Segment med och kvalificeringsregler

Det här segmentet innehåller tre egenskaper från separata dataleverantörer. Eftersom kvalificeringen av segment baseras på ett [!UICONTROL AND] villkor måste besökarna inse egenskaperna hos alla tre flödena för att kvalificera sig för segmentet.

![](assets/billing-segment-and.png)

Med ett [!UICONTROL AND] villkor måste du tilldela alla tre dataleverantörerna 100 % av de visningar som tas emot under månaden. I det här [!UICONTROL Audience Marketplace > Payables] avsnittet krediterar du varje leverantör med 1 000 000 exponeringar.

Det här exemplet gäller segment som använder [!DNL Boolean] [!UICONTROL NOT] operatorer eller för segment som innehåller algoritmiska egenskaper.

<br> 

### Fall 2: Segment med eller kvalificeringsregler

Det här segmentet innehåller tre egenskaper från separata dataleverantörer. Eftersom kvalificeringen av segment baseras på ett [!UICONTROL OR] villkor måste besökarna uppnå minst en av de tre egenskaperna för att kvalificera sig för segmentet.

Vi kan inte avgöra vilken egenskap som är ansvarig för ett intryck eftersom kvalificeringen baseras på ett [!UICONTROL OR] villkor. I det här avsnittet krediterar du därför varje leverantör med en viktad fördelning av de totala avdragen baserat på den totala intäktspopulationen. [!UICONTROL Audience Marketplace > Payables]

![faktureringssegment-eller](assets/billing-segment-or.png)

<br> 

### Fall 3: Segment med modellering och aktivering - användningsfall

I det här exemplet beskrivs attribuering baserat på två användningsfall för datafeed - modellering och aktivering. I det här exemplet tittar vi på två dataleverantörer, med följande information:

![datafeed](assets/feed-use-cases.png)

I tabellen nedan innehåller segment X två egenskaper, T1 och T2, med segmentregeln T1 ELLER T2, där:

* T1 är en egenskap från datafeed A,
* T2 är en algoritmisk egenskap som bygger på egenskaper från datafeed A och datafeed B från tredje part.

Segmentet mappas till en destination och 1 000 000 visningar anges för det här segmentet under en månad med hjälp av rapportering [på](#segment-level-report)segmentnivå.

Av dessa 1 000 000 visningar:

* T1 utgör 40 % av segmentpopulationen, vilket innebär 400 000 visningar för feed A.
* T2 utgör 60 % av segmentpopulationen, vilket motsvarar 600 000 visningar för feed A och feed B.

På dataflödesnivå är det sätt som avbildningarna fördelas på:

* Data Feed A får 600 000 visningar från trait T2 (som bygger på egenskaper från Data Feed A och Data Feed B, så båda får intrycken) och 400 000 visningar från trait T1 (som är ett drag från Data Feed A), totalt 1 000 000 visningar.
* Datafeed B får 600 000 visningar från trait T2 (se förklaringen ovan) och 0 avtryck från trait T1.

Den snabba uppdelningen per datafeed och användningsfall är följande:

![nedbrytning av foder](assets/feed-breakdown-alt.png)

<br> 

## Fakturering och Impression-allokering för statiska avgiftsdatafeeds {#billing-flat-fee}

Med ett dataflöde med fast avgift debiteras ett fast belopp varje månad, oavsett när prenumerationen börjar eller hur många visningar du använder. Avgifterna fördelas inte på partiell månadsanvändning eller delintervall. Precis som med CPM-fakturering kommer Adobe att generera en faktura och fakturera dig med den månatliga, fasta avgiften för dina prenumererade dataflöden.

Anta till exempel att du bestämde dig för att aktivera vissa egenskaper i ett flöde mitt i månaden. Du faktureras fortfarande till den fullständiga månadskostnaden oavsett när du påbörjade prenumerationen eller aktiverade specifika egenskaper.