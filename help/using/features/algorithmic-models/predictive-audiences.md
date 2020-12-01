---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-title: Översikt över Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 3c39ef38d2833d5d706641f70649251d79b2ee6f
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 8%

---


# [!UICONTROL Predictive Audiences] Översikt {#predictive-audiences}

[!UICONTROL Predictive Audiences] hjälper er att klassificera en okänd publik i distinkta personligheter, i realtid, med avancerad datavetenskap.

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

I marknadsföringssammanhang är en persona ett målgruppssegment som definieras av besökare, användare eller potentiella köpare som delar en viss uppsättning traits som demografi, surfvanor, shoppinghistorik osv.

[!UICONTROL Predictive Audiences]-modeller tar detta koncept ett steg längre genom att använda Audience Managers maskininlärningsfunktioner för att klassificera okända målgrupper i distinkta personas. Audience Manager hjälper er att uppnå detta genom att beräkna köpbenägenheten hos en okänd förstapartsmålgrupp i förhållande till en känd uppsättning förstapartsmålgrupper.

När du skapar en [!UICONTROL Predictive Audiences]-modell är det första steget att välja de baslinjeegenskaper eller segment som du vill att målgruppen ska klassificeras efter. Dessa egenskaper eller segment kommer att definiera er personlighet.

Under utvärderingsfasen skapar modellen ett nytt [!UICONTROL Predictive Audiences]-segment för varje egenskap eller segment som du har definierat som baslinje. Nästa gång Audience Manager ser en besökare från målgruppen som inte är klassificerad för en persona (som inte var kvalificerad för någon av dina grundläggande egenskaper eller segment), avgör [!UICONTROL Predictive Audiences]-modellen vilka av de prediktiva segment som besökaren ska tillhöra och lägger till besökaren i det segmentet.

Du kan identifiera de prediktiva segment som skapas av modellen på sidan [!UICONTROL Segments]. Varje [!UICONTROL Predictive Audiences]-modell har en egen mapp under mappen [!UICONTROL Predictive Audiences], och du kan se varje modells segment genom att klicka på modellmappen.

![prediktiv målgrupp-segment](assets/predictive-audiences-segments.png)

## Använd fall {#use-cases}

För att du bättre ska förstå hur och när du kan använda [!UICONTROL Predictive Audiences] finns det några användningsområden som Audience Manager-kunder kan lösa med den här funktionen.

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

## Hur [!UICONTROL Predictive Audiences]-modeller fungerar {#how-predictive-audiences-models-work}

När du skapar en [!UICONTROL Predictive Audiences]-modell går du igenom tre steg:

1. Först väljer du minst två egenskaper eller två segment som definierar dina profiler.
1. Sedan väljer du ett varumärke eller segment som definierar målgruppen som du vill klassificera.
1. Slutligen väljer du ett namn för modellen, en datakälla som lagrar de prediktiva segmenten och en [!UICONTROL Profile Merge Rule] för modellen.

### Urvalskriterier för persona {#selection-personas}

Du kan välja vilken som helst av dina egna egenskaper eller segment för att definiera dina profiler. För bästa resultat finns det dock en uppsättning rekommenderade bästa metoder:

* Välj persona egenskaper eller segment så att varje persona har minst ett fåtal hundra [enhets-ID](../../reference/ids-in-aam.md).
* Om dina egenskaper baseras på [enhets-ID](../../reference/ids-in-aam.md) kan du omsluta dem i segment med [profilkopplingsregler](../profile-merge-rules/merge-rules-overview.md) som använder [enhets-ID](../../reference/ids-in-aam.md), till exempel [!UICONTROL Device Graph]. Detta garanterar att det finns tillräckligt med [enhets-ID](../../reference/ids-in-aam.md) som algoritmen kan lära sig av.
* Vi rekommenderar att du väljer egenskaper eller enkla segment för dina profiler, som består av 1 till 3 egenskaper.
* Välj baslinjetrafik eller segment med minimal överlappning.
* Se till att ni fångar in detaljrikedom i alla era digitala resurser.

### Urvalskriterier för målpublik {#selection-audience}

Beroende på ditt användningssätt, om du vill klassificera användare i realtid, i grupp eller både och, väljer du en målpublik ([!UICONTROL trait] eller [!UICONTROL segment]) som har en betydande population i realtid och/eller totalt. Ungefär som när du väljer en egen markering rekommenderar vi att målgruppen [!UICONTROL trait] eller [!UICONTROL segment] har användare med innehållsrika profiler (innehållsrika uppsättningar [!UICONTROL traits]).

När du väljer målgrupp analyserar du ditt användningsfall och avgör vilka typer av ID du vill klassificera: [!UICONTROL device IDs] eller [!UICONTROL cross-device IDs]. Det [!UICONTROL Profile Merge Rule] som du väljer när du skapar modellen definierar de data som ska användas för att placera varje användare i prediktiva [!UICONTROL segments].

Vi rekommenderar att du väljer en [!UICONTROL Profile Merge Rule] som har samma konfiguration som målgruppen [!UICONTROL Profile Merge Rule], eller en som innehåller profiltypen (enhetsprofil eller autentiserad profil) för målgruppen.

### [!UICONTROL Predictive Audiences] Modellutbildningsfas  {#model-training}

Innan algoritmen kan klassificera er förstapartsmålgrupp i rätt profiler måste den utbilda sig på era data.

För varje personlighet som du definierar analyserar algoritmen sin respektive målgrupp och utvärderar eventuell realtids- och/eller varumärkesaktivitet för användarna de senaste 30 dagarna.
Det här steget utförs en gång var 24:e timme för att ta hänsyn till förändringar hos er förstapartsmålgrupp.

### [!UICONTROL Predictive Audiences] Modellklassificeringsfas  {#model-classification}

För att klassificera målgrupper i realtid och i batch kontrollerar modellen först om en användare tillhör målgruppen. Om användaren kvalificerar sig för målgruppen och inte tillhör någon av personerna tilldelas de ett personligt kvalifikationspoäng av modellen.

När du utvärderar förstapartsmålgrupper och tilldelar poäng används standardvärdet **[!UICONTROL Profile Merge Rule]** som definierats i ditt konto. Slutligen klassificeras besökaren i den personlighet för vilken de fick högsta poäng.

![prediktiv-audiences-graph](assets/predictive-audiences-graph.png)

## Överväganden och begränsningar {#considerations}

>[!IMPORTANT]
> Läs igenom detta avsnitt noggrant innan du går vidare till implementeringsfasen.

Tänk på följande när du konfigurerar dina [!UICONTROL Predictive Audiences]-modeller:

* Du kan skapa upp till 10 [!UICONTROL Predictive Audiences]-modeller.
* För varje modell kan du välja upp till 50 basegenskaper/segment.
* Data från andra och tredje part stöds för närvarande inte i [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] utför målgruppsklassificering baserat på era egenskaper hos första part, från alla era egna datakällor.
* Vid segmentutvärderingen för [!UICONTROL Predictive Audiences] används **[!UICONTROL Profile Merge Rule]** som du väljer när du skapar en modell. Mer information om [!UICONTROL Profile Merge Rules] finns i den dedikerade [dokumentationen](../profile-merge-rules/merge-rules-overview.md).
* Vissa egenskaper och segment stöds inte som baslinjer eller målgrupper. [!UICONTROL Predictive Audiences] modeller kan inte sparas när du väljer något av följande som baslinjer eller målgrupper:
   * Prediktiva egenskaper och segment som skapats med prediktiva egenskaper.
   * [Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Platformtraits eller segments.
   * Algoritmiska egenskaper.
   * Andra och tredje parts egenskaper.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] kan inte användas i  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Prediktiva segment som skapats av [!UICONTROL Predictive Audiences]-modeller ärver [dataexportkontroller](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) från följande datakällor från första part:

1. Den datakälla från första part som du väljer när du skapar modellen.
1. Målgruppens första datakällor. Det gäller särskilt dataexportkontrollerna för [!UICONTROL traits] eller [!UICONTROL segments] som utgör målgruppen.
1. [Dataexportkontroller](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) för [!UICONTROL Profile Merge Rule] som du har valt för modellen.

Det nya prediktiva [!UICONTROL traits] och [!UICONTROL segments] har samma sekretessbegränsningar som den union av förstapartsdatakällor som beskrivs ovan.

Fastigheter som har ytterligare begränsningar som inte ingår i [!UICONTROL Predictive Audiences]-segmentets integritetsbegränsningar exkluderas från utbildningsfasen och kommer inte att påverka modellen.

## [!UICONTROL Profile Merge Rules] {#pmr}

Alla prediktiva segment tilldelas [!UICONTROL Profile Merge Rule] som du valde när du skapade modellen. Det [!UICONTROL Profile Merge Rule] du väljer är viktigt av följande skäl:

* Den definierar vilka enheter och/eller autentiserade profiler som ska beaktas när modellen analyserar den inflytelserika [!UICONTROL traits], när en användare klassificeras som prediktiv [!UICONTROL segment].
* Det styr vilka [!UICONTROL trait] typer (enhetsnivå eller enhetsnivå) som ska användas under modellutbildningssteget och visas som inflytelserika [!UICONTROL traits]. Prediktiva [!UICONTROL segments] är delmängder av målgruppen.
   * Om målgruppen är ett segment rekommenderar vi att du väljer samma [!UICONTROL Profile Merge Rule] för modellen som den som tilldelats målgruppen, eller en [!UICONTROL Profile Merge Rule] som innehåller målpublikens profiltyp.
   * Om målgruppen är en [!UICONTROL trait] rekommenderar vi att du väljer en [!UICONTROL Profile Merge Rule] som har åtkomst till samma typ av data som målmålgruppens trait (antingen enhetsprofildata eller profildata mellan olika enheter).
* [!UICONTROL Profile Merge Rules] att använda  [!UICONTROL Current Authenticated Profiles] och- [!UICONTROL No Device Profile] alternativen stöds endast för målgruppsklassificering i realtid. Mer information finns i [Alternativ för profilkopplingsregler definierade](../profile-merge-rules/merge-rule-definitions.md).

Om du väljer en [!UICONTROL Profile Merge Rule] som använder både enhetsdata och enhetsdata maximeras antalet [!UICONTROL traits] som kan användas för modellutbildning och användarklassificering i prediktiva [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

De egenskaper och segment som du väljer för profiler och målgruppsklassificering lyder under Audience Manager [rollbaserade åtkomstkontroller](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager-användare kan bara välja egenskaper eller segment för personer och målgrupper, som de har [behörighet att visa](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
