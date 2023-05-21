---
description: När du skapar eller redigerar ett segment i Segment Builder med Trait Recommendations får du rekommendationer om ytterligare egenskaper som du kan inkludera, som liknar egenskaperna i segmentregeln. Lägg till de rekommenderade egenskaperna i ert segment för att öka er målgrupp.
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait-rekommendationer
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 4%

---

# Trait-rekommendationer

Få rekommendationer i realtid när ni bygger era segment utifrån era egna egenskaper och [!UICONTROL Audience Marketplace] dataflöden.

## Videodemonstration

Börja med att titta på [!UICONTROL Trait Recommendations] nedan och läs vidare för mer information. Videodemonstrationen visar hur du kan arbeta med rekommendationer från dina egna egenskaper, liksom rekommendationer från anpassade leverantörer [!UICONTROL Audience Marketplace] dataflöden som *du redan prenumererar på*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

I nästa video visas arbetsflödet för [!UICONTROL Marketplace Recommendations]som visar hur du lägger till egenskaper i dina segment, baserat på rekommendationer från dataflöden i [!UICONTROL Audience Marketplace]. Dessa rekommendationer baseras på dataflöden som *du prenumererar inte på*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Översikt

[!UICONTROL Trait Recommendations], med [!DNL Adobe Sensei], för datavetenskap in i dina vardagliga arbetsflöden i Audience Manager.
Med [!UICONTROL Trait Recommendations]när du skapar eller redigerar ett segment i [Segment Builder](segment-builder.md)får du rekommendationer om vilka egenskaper du kan inkludera som liknar egenskaperna i segmentregeln.

Audience Manager visar dina rekommendationer från båda dina egna egenskaper i **[!UICONTROL Recommendations]** och från **[!UICONTROL Audience Marketplace]**, i **[!UICONTROL Recommendations from Marketplace]** -avsnitt.

Lägg till de rekommenderade egenskaperna i ert segment för att öka er målgrupp.

![Trait Recommendations Overview](assets/trait-recommendations-overview-full.png)

**I korthet:**

* Audience Manager visar egenskaper för första part i [!UICONTROL Recommendations] -avsnitt. Marketplace-rekommendationer från offentliga och privata feeds som du inte prenumererar på visas i [!UICONTROL Recommendations from Marketplace] -avsnitt. Klicka på feed-namnet för att gå till [!UICONTROL Audience Marketplace] och prenumerera.
* Audience Manager visar högst femtio egenskaper som liknar den i segmentregeln.
* Du kan filtrera bort de datakällor som du inte vill se några rekommendationer från.
* Vid beräkning av likheter beaktar Audience Manager [UUID](../../reference/ids-in-aam.md) som är berättigade till tävlingsbidrag under de senaste 30 dagarna.
* Om felmeddelandet&quot;Inga liknande egenskaper hittades. Trait(s) kan vara för nytt.&quot;, vilket innebär att det inte har förekommit någon aktivitet för den egenskapen under de senaste 30 dagarna, eller att Audience Manager ännu inte har uppdaterat rekommendationerna för den egenskapen. Försök igen om 24 timmar.

## Användningsexempel

Med [!UICONTROL Trait Recommendations]kan du förbättra dina arbetsflöden beroende på hur du använder Audience Manager:

* Som marknadsförare kan ni snabbt hitta målgrupper som är intresserade av kompletterande produkter med hjälp av liknande egenskaper, så att ni kan öka er räckvidd.
* Om du använder Audience Manager som utgivare, med [!UICONTROL Trait Recommendations]kan ni förstå målgruppernas beteende och bygga upp bättre segment för annonsförsäljning eller kundvärvning.
* Som en [!UICONTROL Audience Marketplace] datainköpare vill jag identifiera relevanta tredjepartsdata utan att behöva bläddra igenom ett stort antal feeds.
* Som en [!UICONTROL Audience Marketplace] Jag vill rekommendera relevanta data till köpare så att jag kan dra nytta av optimala och relevanta prenumerationer.

## Skillnader mellan Trait Recommendations och algoritmiska modeller

### Algoritmiska modeller

[!UICONTROL Algorithmic Models] inte bara hittar de mest inflytelserika egenskaperna, utan även poängsätter användare baserat på dessa egenskaper och tilldelar varje användare en individuell poäng. Sedan skapar du algoritmiska traits som riktar sig till användarna. Med precision och räckvidd i [!UICONTROL Trait Builder]kan du ange vilka användare bland alla som har de inflytelserika egenskaper som du vill ha som mål.

[!UICONTROL Algorithmic Models] gör att du kan välja användare på olika noggrannhetsnivåer och testa i [!UICONTROL Audience Lab] vilken grupp av användare som blir bättre på att konvertera. Se det detaljerade användningsexemplet i [Jämför modeller i Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

I [!UICONTROL Algorithmic Models]körs modellen var 8:e dag och uppdaterar de användare som är kvalificerade för algoritmiska egenskaper.

### Trait-rekommendationer

[!UICONTROL Trait Recommendations] är ett snabbt sätt att få insikter om andra egenskaper som liknar de du använder i ett segment.

Du bör använda [!UICONTROL Trait Recommendations] när:

* Ni behöver snabba insikter när ni skapar segment
* Ni använder segmenten för korta kampanjer eller när ni snabbt vill exkludera målgrupper som konverterar
* Ni försöker maximera räckvidden.

## Arbetsflöde

När du skapar eller redigerar ett segment i [Segment Builder](segment-builder.md)kan du utforska egenskaper som liknar egenskaperna i segmentregeln. The [Segment Builder](segment-builder.md) arbetsflödet är mycket likt för nya och befintliga segment:

### Nya segment

1. Gå till **Målgruppsdata > Segment** och klicka **Lägg till ny**.
1. I **Traits** lägger du till minst en egenskap i segmentregeln.
1. Du kan se rekommenderade egenskaper och [!UICONTROL Audience Marketplace] anpassa rekommendationer från feeds som du prenumererar på i **[!UICONTROL Recommendations]** -avsnitt. The **[!UICONTROL Recommendations from Marketplace]** I visas hur du hanterar rekommendationer från feeds som du inte prenumererar på. Alla dessa rekommendationer liknar de egenskaper som du har lagt till i segmentregeln. Rulla ned för att se alla rekommenderade egenskaper.
1. (Valfritt) Om du vill utesluta rekommenderade egenskaper från vissa datakällor klickar du på **X** -symbol för de datakällor som du vill utesluta.

   >[!NOTE]
   >
   >De utelämnade datakällorna visas alldeles ovanför listan med rekommenderade egenskaper. Klicka **X** i den grå rutan för att ta bort undantagen och se resultaten från respektive datakällor igen.
1. Klicka på knappen **+** symbol.

>[!IMPORTANT]
>
>Vid tillägg [!UICONTROL Marketplace] egenskaper för ett segment, används egenskaperna bara för segmentberäkning tills du prenumererar på motsvarande datafeed. Fällor som kommer från dataflöden som du inte prenumererar på markeras med en kundvagnsikon i listan. Klicka på namnet på trait för att gå till datafeedsidan och prenumerera på den.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>Du kan bara spara ett segment med egenskaper från tredje part efter att du har prenumererat på motsvarande dataflöden.

### Befintliga segment

1. Gå till **[!UICONTROL Audience Data]>[!UICONTROL Segments]** markerar du det segment som du vill redigera och klickar på ![Redigera](assets/edit-button.png).
1. Bläddra nedåt till [!UICONTROL Traits] nedrullningsbar listruta.
1. Rekommenderade egenskaper som liknar de egenskaper som redan finns i segmentregeln visas. Rulla ned för att se alla rekommenderade egenskaper.
1. (Valfritt) Om du vill utesluta rekommenderade egenskaper från vissa datakällor klickar du på **X** -symbol för de datakällor som du vill utesluta.

   >[!NOTE]
   >
   >De utelämnade datakällorna visas alldeles ovanför listan med rekommenderade egenskaper. Klicka **X** i den grå rutan för att ta bort undantagen och se resultaten från respektive datakällor igen.
1. Klicka på knappen **+** symbol.

När du skapar eller redigerar ett segment och lägger till ett drag i segmentregeln, visas maximalt femtio rekommenderade egenskaper, liknande den som du har lagt till. Om segmentregeln innehåller mer än ett drag, använder Audience Manager en runda rader-metod för att visa den bästa matchningen för varje egenskap, den näst bästa matchningen för varje egenskap och så vidare, för de största femtio egenskaperna per population, i segmentregeln.

![Tre baslinjer](assets/three-base-traits.png)

Om det till exempel finns tre egenskaper i segmentregeln, som visas nedan, är de rekommenderade egenskaperna:

1. Bästa matchning för trait 3 (egenskapen med den största befolkningen).
1. Best match for trait 1;
1. Best match for trait 2;
1. Andra bästa matchningen för trait 3;
1. Den näst bästa matchningen för trait 1 och så vidare tills du når femtio traits.

Om du vill få rekommendationer för en viss egenskap kan du klicka på egenskaperna i segmentregeln (1) eller i vyn med rekommenderade egenskaper (2).

![base-traits-example](assets/three-base-traits-numbered.png)

När du klickar på ett spår från första part öppnas ett popup-fönster, vilket visas i bilden nedan. Om de rekommenderade egenskaperna inte är en del av segmentet kan du lägga till dem i segmentet genom att trycka på **+**.

![tillägg till segment](assets/add_to_segments.png)

>[!TIP]
>
>Undantagna datakällor från huvudsidan beaktas när rekommendationer genereras i popup-fönstret för trait-information. Om du exkluderar datakällor i den här vyn gäller undantagen för huvudsidan.

>[!NOTE]
>
>Rekommenderade egenskaper kan vara egna egenskaper eller egenskaper hos tredje part från dataflöden som du prenumererar på i [!UICONTROL Audience Marketplace].

## Så här fungerar det

Audience Manager beräknar de [Jaccard-likhet](https://en.wikipedia.org/wiki/Jaccard_index) mellan målegenskapen och alla andra egenskaper som ditt konto har tillgång till, inklusive data från tredje part. Audience Manager visar sedan upp till femtio egenskaper med den största likheten.

## Spåra likhetsresultat {#trait-similarity-score}

Audience Manager beräknar [!UICONTROL Trait Similarity Score] mellan två egenskaper genom att beräkna skärningspunkten och kombinera dem i antal [!UICONTROL UUID]s och sedan dividera de två. För de två egenskaperna A och B ser beräkningen ut så här:

![jaccard-likhet](assets/jaccard_similarity.png)

Se även de två exemplen nedan.

### Exempel 1 - Likhetspunkt med låg tram

Med två egenskaper som A och B, låt oss säga att var och en av egenskaperna har en befolkning på 1 000 000 [!UICONTROL UUID]s, 25 000 [!UICONTROL UUID]som uppfyller båda kraven.
Om du använder formeln ovan resulterar detta i: 25 000 / 1 975 000 = 0,012. Det här är en låg [!UICONTROL Trait Similarity Score]De två egenskaperna skiljer sig mycket åt.

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### Exempel 2 - Likhetspunkt för spår

Om samma egenskaper A och B hade 400 000 [!UICONTROL UUID]som uppfyller villkoren för båda egenskaperna, [!UICONTROL Trait Similarity Score] är mycket högre: 400 000 / 1 600 000 = 0,25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### Så här tolkar du likhetspoängen för spår

Använd tabellen nedan som en grov stödlinje för att anpassa likheter. Den här guiden baseras på de likhetspoäng som observerats för en majoritet av egenskaperna.

| [!UICONTROL Trait Similarity Score] | Signifikans |
|---------|----------|
| 0.1 och senare | Hög likhet mellan egenskaper |
| 0.03 - 0.1 | Medelstor likhet mellan egenskaper |
| 0.01 - 0.03 | Låg likhet mellan egenskaper |
| 0 - 0.01 | Mycket låg likhet mellan egenskaper |

## Rollbaserad åtkomstkontroll (RBAC)

För företag som använder [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) måste du ha behörighet att skapa och redigera segment för att kunna se rekommenderade egenskaper. Det är bara de anpassade rekommendationer du ser från datakällor som du har åtkomst till via [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Lägg till [!UICONTROL Marketplace Recommendations] till ett segment måste användarna först prenumerera på motsvarande dataflöden. Endast användare med administratörsbehörighet kan prenumerera på [!UICONTROL Audience Marketplace] dataflöden.

Läs mer om [!UICONTROL RBAC] kontroller [här](../administration/administration-overview.md).

## Begränsningar

* I Audience Manager visas för närvarande inte mappegenskaper som rekommenderade egenskaper. Läs mer om mappegenskaper [här](../traits/manage-folder-traits.md).
* När Trait Recommendations visas beaktas inte Audience Manager [!DNL Boolean] operatorer ([!DNL AND], [!DNL OR], [!DNL NOT]) i segmentregler.
