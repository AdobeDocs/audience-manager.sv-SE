---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-title: Översikt över Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 1be20c2412a272e6374b8b84e6a5c1628da18497
workflow-type: tm+mt
source-wordcount: '1530'
ht-degree: 7%

---


# [!UICONTROL Predictive Audiences] Översikt {#predictive-audiences}

[!UICONTROL Predictive Audiences] hjälper er att klassificera en okänd publik i distinkta personligheter, i realtid, med avancerad datavetenskap.

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

I marknadsföringssammanhang är en persona ett målgruppssegment som definieras av besökare, användare eller potentiella köpare som delar en viss uppsättning traits som demografi, surfvanor, shoppinghistorik osv.

[!UICONTROL Predictive Audiences]-modeller tar detta koncept ett steg längre genom att använda Audience Managers maskininlärningsfunktioner för att klassificera okända målgrupper i distinkta personas. Audience Manager hjälper er att uppnå detta genom att beräkna köpbenägenheten hos en okänd förstapartsmålgrupp i förhållande till en känd uppsättning förstapartsmålgrupper.

När du skapar en [!UICONTROL Predictive Audiences] modell är det första steget att välja de baslinjeegenskaper eller segment som du vill att målgruppen ska klassificeras efter. Dessa egenskaper eller segment kommer att definiera er personlighet.

Under utvärderingsfasen skapar modellen ett nytt [!UICONTROL Predictive Audiences] segment för varje drag eller segment som du har definierat som baslinje. Nästa gång Audience Manager ser en besökare från målgruppen som inte är klassificerad som en person (som inte var kvalificerad för någon av dina grundläggande egenskaper eller segment), avgör [!UICONTROL Predictive Audiences] modellen vilka av de prediktiva segment som besökaren ska tillhöra och lägger till besökaren i det segmentet.

Du kan identifiera de prediktiva segment som skapas av modellen på [!UICONTROL Segments] sidan. Varje [!UICONTROL Predictive Audiences] modell har en egen mapp under [!UICONTROL Predictive Audiences] mappen, och du kan se varje modells segment genom att klicka på modellmappen.

![prediktiv målgrupp-segment](assets/predictive-audiences-segments.png)

## Användningsexempel {#use-cases}

För att du bättre ska förstå hur och när du kan använda [!UICONTROL Predictive Audiences]finns det några exempel på hur Audience Manager-kunder kan lösa det med den här funktionen.

### Användningsfall 1

Som marknadsförare i ett e-handelsföretag vill jag klassificera alla mina webb- och mobilbesökare i olika kategorier för varumärkestillhörighet, så att jag kan personalisera deras användarupplevelse.

### Användningsfall nr 2

Som marknadsförare i ett medieföretag vill jag klassificera mina oautentiserade webb- och mobilbesökare efter favoritgenrer, så att jag kan föreslå dem personaliserat innehåll i alla kanaler.

### Användningsfall nr 3

Som marknadsförare för ett flygbolag vill jag se till att jag klassificerar min publik utifrån deras intresse för resmål, så att jag kan annonsera för dem i realtid, inom ett kort omdirigeringsfönster.

### Användningsfall nr 4

Som annonsörer vill jag klassificera min förstapartspublik i realtid, så att jag snabbt kan reagera på trender.

### Användningsfall nr 5

Som marknadsförare vill jag förutsäga vilken kundresa som besökarna på min webbplats befinner sig i, till exempel upptäckt, engagemang, köp eller lojalitet, så att jag kan inrikta mig på dem därefter.

### Användningsfall nr 6

Som medieföretag vill jag kategorisera min publik så att jag kan sälja min annonsutrymme till premiumpriser samtidigt som jag erbjuder våra besökare relevanta annonser.

## Så här fungerar [!UICONTROL Predictive Audiences] modeller {#how-predictive-audiences-models-work}

När du skapar en [!UICONTROL Predictive Audiences] modell går du igenom tre steg:

1. Först väljer du minst två egenskaper eller två segment som definierar dina profiler.
1. Sedan väljer du ett varumärke eller segment som definierar målgruppen som du vill klassificera.
1. Slutligen väljer du ett namn för modellen, en datakälla som lagrar de prediktiva segmenten och en [!UICONTROL Profile Merge Rule] för modellen.

### Urvalskriterier för personer {#selection-personas}

Du kan välja vilken som helst av dina egna egenskaper eller segment för att definiera dina profiler. För bästa resultat finns det dock en uppsättning rekommenderade bästa metoder:

* Välj dina personliga egenskaper eller segment så att varje person har minst ett fåtal hundra [enhets-ID](../../reference/ids-in-aam.md).
* Om dina egenskaper baseras på [enhets-ID](../../reference/ids-in-aam.md)kan du kapsla in dem i segment med [profilkopplingsregler](../profile-merge-rules/merge-rules-overview.md) som använder [enhets-ID](../../reference/ids-in-aam.md), till exempel [!UICONTROL Device Graph]. Detta garanterar att det finns tillräckligt många [enhets-ID](../../reference/ids-in-aam.md) som algoritmen kan lära sig av.
* Vi rekommenderar att du väljer egenskaper eller enkla segment för dina profiler, som består av 1 till 3 egenskaper.
* Välj baslinjetrafik eller segment med minimal överlappning.
* Se till att ni fångar in detaljrikedom i alla era digitala resurser.

### Urvalskriterier för Target-målgrupp {#selection-audience}

På samma sätt som för en personlig markering bör du välja målgrupp [!UICONTROL trait] eller [!UICONTROL segment] som definierar målgruppen på ett sådant sätt att den har realtidsanvändare med många uppsättningar [!UICONTROL traits]för klassificering i rätt profil.

När du väljer målgrupp analyserar du ditt användningsfall och avgör vilka typer av ID du vill klassificera: [!UICONTROL device IDs] eller [!UICONTROL cross-device IDs]. Det [!UICONTROL Profile Merge Rule] som du väljer när du skapar modellen definierar de data som ska användas för att placera varje användare i prediktiva [!UICONTROL segments].

Vi rekommenderar att du väljer en [!UICONTROL Profile Merge Rule] som har samma konfiguration som målgruppen [!UICONTROL Profile Merge Rule]eller en som innehåller profiltypen (enhetsprofil eller autentiserad profil) för målgruppen.

### [!UICONTROL Predictive Audiences] Modellutbildningsfas {#model-training}

Innan algoritmen kan klassificera er förstapartsmålgrupp i rätt profiler måste den utbilda sig på era data.

För varje personlighet som du definierar analyserar algoritmen sin respektive målgrupp och utvärderar eventuell realtids- och/eller varumärkesaktivitet för användarna de senaste 30 dagarna.
Det här steget utförs en gång var 24:e timme för att ta hänsyn till förändringar hos er förstapartsmålgrupp.

### [!UICONTROL Predictive Audiences] Modellklassificeringsfas {#model-classification}

När en besökare som är en del av målgruppen visas i realtid utvärderar modellen om besökaren är en del av den definierade personligheten. För varje besökare som inte tillhör någon av personerna tilldelar modellen ett personligt kvalificeringsmoment.

När du utvärderar förstapartsmålgrupper och tilldelar poäng används standardvärdet som **[!UICONTROL Profile Merge Rule]** definierats i ditt konto. Slutligen klassificeras besökaren i den personlighet för vilken de fick högsta poäng.

![prediktiv-audiences-graph](assets/predictive-audiences-graph.png)

## Överväganden och begränsningar {#considerations}

>[!IMPORTANT]
> Läs igenom detta avsnitt noggrant innan du går vidare till implementeringsfasen.

Tänk på följande när du konfigurerar dina [!UICONTROL Predictive Audiences] modeller:

* Du kan skapa upp till 10 [!UICONTROL Predictive Audiences]-modeller.
* För varje modell kan du välja upp till 50 basegenskaper/segment.
* Data från andra och tredje part stöds för närvarande inte i [!UICONTROL Predictive Audiences].
* Målgruppsklassificering görs endast för förstapartsmålgrupper i realtid. Integrerad klassificering av förstahandsanvändare kan stödjas i en framtida uppdatering.
   >[!IMPORTANT]
   > För närvarande kan prediktiva segment bara aktiveras i realtidsdestinationer. Värdet [!UICONTROL Total Segment Population] och [!UICONTROL Addressable Audience] värdet för dina prediktiva segment visas som 0, och [grupputgående dataöverföringar](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) stöds inte för [!UICONTROL Predictive Audiences]. Detta beteende ändras i en framtida uppdatering.
* [!UICONTROL Predictive Audiences] utför målgruppsklassificering baserat på era egenskaper hos första part, från alla era egna datakällor.
* Segmentutvärdering för [!UICONTROL Predictive Audiences] använder **[!UICONTROL Profile Merge Rule]** det du väljer när du skapar en modell. Mer information om [!UICONTROL Profile Merge Rules] finns i den dedikerade [dokumentationen](../profile-merge-rules/merge-rules-overview.md).
* Vissa egenskaper och segment stöds inte som baslinjer eller målgrupper. [!UICONTROL Predictive Audiences] modeller kan inte sparas när du väljer något av följande som baslinjer eller målgrupper:
   * Prediktiva egenskaper och segment som skapats med prediktiva egenskaper.
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) egenskaper eller segment,
   * Algoritmiska egenskaper.
   * Andra och tredje parts egenskaper.

## [!UICONTROL Data Export Controls] {#dec}

Prediktiva segment som skapas av [!UICONTROL Predictive Audiences] modeller ärver [dataexportkontrollerna](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) från följande datakällor:

1. Den datakälla från första part som du väljer när du skapar modellen.
1. Målgruppens första datakällor. Det gäller särskilt dataexportkontrollerna för [!UICONTROL traits] eller [!UICONTROL segments] som utgör målgruppen.
1. The [Data Export Controls](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) of the [!UICONTROL Profile Merge Rule] that you selected for the model.

Den nya prediktiva funktionen [!UICONTROL traits] och [!UICONTROL segments] den kommer att ha samma integritetsbegränsningar som kombinationen av förstahandsdatakällor som beskrivs ovan.

Fastigheter som har ytterligare begränsningar som inte ingår i [!UICONTROL Predictive Audiences] segmentets integritetsbegränsningar exkluderas från utbildningsfasen och kommer inte att påverka modellen.

## [!UICONTROL Profile Merge Rules] {#pmr}

Alla prediktiva segment tilldelas den [!UICONTROL Profile Merge Rule] som du valde när du skapade modellen. Det [!UICONTROL Profile Merge Rule] du väljer är viktigt av följande skäl:

* Den definierar vilka enheter och/eller autentiserade profiler som ska beaktas när modellen analyserar inflytelsen [!UICONTROL traits]när en användare klassificeras som prediktiv [!UICONTROL segment].
* Det styr vilka [!UICONTROL trait] typer (enhetsnivå eller enhetsövergripande nivå) som ska användas under modellutbildningssteget och visas som inflytelserika [!UICONTROL traits]. Prediktiv [!UICONTROL segments] är delar av målgruppen.
   * Om målgruppen är ett segment rekommenderar vi att du väljer samma [!UICONTROL Profile Merge Rule] för modellen som den som tilldelats målgruppen, eller en [!UICONTROL Profile Merge Rule] som innehåller målpublikens profiltyp.
   * Om målgruppen är en målgrupp [!UICONTROL trait]rekommenderar vi att du väljer en [!UICONTROL Profile Merge Rule] som har åtkomst till samma typ av data som målgruppens trait (antingen enhetsprofildata eller profildata för olika enheter).

Om du väljer en [!UICONTROL Profile Merge Rule] som använder både enhetsdata och data mellan olika enheter maximeras antalet [!UICONTROL traits] som kan användas för modellutbildning och användarklassificering i förutsägbarheten [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Vilka egenskaper och segment du väljer för personifiering och målgruppsklassificering omfattas av [rollbaserade åtkomstkontroller](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)för Audience Manager.

Audience Manager-användare kan bara välja egenskaper eller segment för personer och målgrupper som de har [behörighet att visa](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
