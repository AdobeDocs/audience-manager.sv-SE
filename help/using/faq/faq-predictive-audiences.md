---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Vanliga frågor om Predictive Audiences
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 59%

---

# Vanliga frågor om Predictive Audiences

Vanliga frågor och svar om [!UICONTROL Predictive Audiences].

 

**När ska jag använda [!UICONTROL Predictive Audiences] i stället för [!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] och [!UICONTROL Look-alike modeling] kan användas på olika sätt. De viktigaste skillnaderna mellan de två algoritmerna är följande:

1. [!UICONTROL Look-alike modeling] tar en liten målgrupp som indata och bygger vidare på den. [!UICONTROL Predictive Audiences] tar en stor målgrupp som indata och delar in den i mindre distinkta målgrupper som definieras av era personas.
1. Antalet bassegment är olika för varje algoritm. [!UICONTROL Predictive Audiences] kräver minst två baslinjer, medan [!UICONTROL Look-alike modeling] använder högst en baslinje.
1. [!UICONTROL Predictive Audiences] utvärderar segment i realtid, [!UICONTROL Look-alike modeling] gör det inte.

Beroende på ert användningsområde bör ni bestämma vilken modell som är mest relevant.

Du kan tänka dig att en [!UICONTROL Predictive Audiences]-modell med ett antal baslinjer är ungefär som samma antal lookalike-modeller utan utvärdering i realtid och med en mycket hög sannolikhet att besökare tillhör flera olika personas i stället för en enda.

 

**Hur många personas/modeller kan jag skapa?**

Du kan skapa upp till 10 [!UICONTROL Predictive Audiences]-modeller. För varje modell kan du definiera upp till 50 baslinje-traits eller segment.

 

**Hur skapar jag nya segment från ett [!UICONTROL Predictive Audiences]-segment?**

Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** och klicka på **[!UICONTROL Predictive Audiences]**-mappen. Hitta det önskade segmentet, kopiera det och redigera det efter behov.

 

**När kan jag se de första resultaten från min modell?**

Resultat från [!UICONTROL Predictive Audiences]-modeller är tillgängliga inom 24 timmar efter att modellen har skapats, om modellen fungerar som den ska.

Om modellen inte ger några resultat inom 24 timmar kan du kontakta din Adobe-representant.

 

**Varför producerar min modell inga resultat eller varför visas varningsstatus?**

[!UICONTROL Predictive Audiences]-modeller kanske inte ger resultat på grund av en rad orsaker:

1. Ingen av de markerade personerna [!UICONTROL traits] / [!UICONTROL segments] har tillräckligt många användarprofiler. Vi rekommenderar att du väljer [!UICONTROL traits] eller [!UICONTROL segments] så att varje person har minst några hundra användarprofiler.
1. Ingen av de markerade personerna [!UICONTROL traits] / [!UICONTROL segments] har tillräckligt med data i sina användarprofiler (det finns inte tillräckligt med egenskaper för att analysera).
1. Målgruppens trait/segment har inga aktiva eller onboardade användare.
1. De målgruppsanvändare som varit aktiva eller registrerade under de senaste 30 dagarna har inte tillräckligt med data i sina användarprofiler (inte tillräckligt med traits att analysera).
1. Målgruppssegmentet använder en annan [!UICONTROL Profile Merge Rule] än den som du valde för modellen.
1. Datakällan för målpublikens egenskaper kanske inte inkluderas i [!UICONTROL Profile Merge Rule] som du valde för modellen.

Följ de föreslagna riktlinjerna i [Urvalskriterier för personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) och [Urvalskriterier för målgrupp](../features/algorithmic-models/predictive-audiences.md#selection-audience) för att få optimala resultat.

 

**Varför visar min modell [!UICONTROL Error]-status?**

Modellen kunde inte köras. Kontakta i så fall din [!DNL Adobe]-representant.

 

**Hur ändrar jag [!UICONTROL Profile Merge Rule] för en [!UICONTROL Predictive Audiences] [!UICONTROL segment]?**

Skapa en ny modell genom att välja samma personer och målgrupp som din tidigare modell. Tilldela en annan [!UICONTROL Profile Merge Rule] när en modell skapas.

>[!WARNING]
> Du kan också använda [Segment Builder](../features/segments/segment-builder.md) för att manuellt skapa en [!UICONTROL segment] med en befintlig prediktiv [!UICONTROL trait] och tilldela den ett [!UICONTROL Profile Merge Rule] som du väljer.
> 
> Vi rekommenderar dock inte den här metoden eftersom prediktiv [!UICONTROL traits] automatiskt ärver [!UICONTROL Profile Merge Rule] för modellen som de tillhör och de byggs från inflytelserik [!UICONTROL traits] som uppfyller modellens [!UICONTROL Profile Merge Rule].

 

**Vad [!UICONTROL Profile Merge Rule] ska jag välja?**

När du väljer [!UICONTROL Profile Merge Rule] för din modell bör du noggrant analysera ditt användningsfall.

Anta att målgruppen [!UICONTROL segment] använder en [!UICONTROL Profile Merge Rule] baserad på autentiserade profiler + [!DNL Device Graph] profiler och att du väljer samma [!UICONTROL Profile Merge Rule] för prediktiva [!UICONTROL segments]. I det här fallet används både enhetsnivån och enhetsövergripande [!UICONTROL traits] för att utbilda modellen och användarens placering i en prediktiv [!UICONTROL segment].

Om du väljer en [!UICONTROL Profile Merge Rule] som enbart baseras på enhetsprofiler kommer ingen av dina enheter [!UICONTROL traits] att bli inflytelserik och kommer inte att bidra till att användarna placeras i ett prediktivt [!UICONTROL segment]. Detta kan påverka modellens noggrannhet och räckvidd negativt.

Analysera ditt användningsfall noggrant och bestäm vilka [!UICONTROL trait] typer du vill att modellen ska lära sig av och vilken typ av data du vill att modellen ska använda för klassificering.

**Går det att klassificera en användare från målgruppen som inte är en del av något persona-trait/segment?**

Nej, användaren måste ha några traits i sin profil. Om inte får användaren matchningspoängen 0 för alla persona traits/segment och kommer därför inte att klassificeras i något av de prediktiva segmenten.

 

**Kan en användare som klassificerats i ett av de prediktiva segmenten omklassificeras till ett annat [!UICONTROL Predictive Audiences]-segment?**

Ja. Eftersom algoritmen tränas dagligen tillämpas ändringarna i varje persona när det gäller poängsättning för traits. Om en användare som är en del av ett [!UICONTROL Predictive Audiences]-segment är aktiv kan ändringar i deras trait-poäng ändra klassificeringen baserat på de senaste 30 dagarnas aktiviteter.

 

**Kan jag se vilka traits som används för målgruppsklassificering?**

Ja, du kan se alla viktiga traits för alla baslinjer på modellrapporteringssidan. Se [Viktiga traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Kan jag ändra TTL-tiden (time to live) för prediktiva egenskaper?**

TTL för det prediktiva beteendet är inställt på 0 (livstid) och kan inte ändras. [!UICONTROL Predictive Audiences] kan bara dela upp användare från prediktiva segment när de kvalificerar sig för antingen bassegmentet eller omklassificeras till ett annat prediktivt segment.

Vid behov kan du kringgå den här funktionen genom att skapa ett nytt segment som innehåller både ett prediktivt drag och ett aktivitetsdrag med en angiven TTL.

 


**Vad händer med modellen om jag redigerar ett baslinje-trait eller segment?**

Modellen utvärderar traits eller segmenten en gång om dagen. Du bör se den uppdaterade klassificeringen dagen efter uppdateringen.

 

**Kan jag välja de datakällor som modellen ska använda för inlärning?**

Nej, val av datakällor stöds inte. [!UICONTROL Predictive Audiences]-algoritmen lär sig av alla era förstaparts-traits.
