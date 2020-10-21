---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-title: Vanliga frågor om Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 64%

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

1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough user profiles. We recommend choosing your [!UICONTROL traits] or [!UICONTROL segments] so that each persona has at least a few hundred user profiles.
1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough data in their user profiles (not enough traits to analyze).
1. Målgruppens trait/segment har inga aktiva eller onboardade användare.
1. De målgruppsanvändare som varit aktiva eller registrerade under de senaste 30 dagarna har inte tillräckligt med data i sina användarprofiler (inte tillräckligt med traits att analysera).
1. Målgruppssegmentet använder en annan [!UICONTROL Profile Merge Rule] än den som du valde för modellen.
1. Datakällan för målpublikens egenskaper kanske inte inkluderas i den [!UICONTROL Profile Merge Rule] som du valde för modellen.

Följ de föreslagna riktlinjerna i [Urvalskriterier för personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) och [Urvalskriterier för målgrupp](../features/algorithmic-models/predictive-audiences.md#selection-audience) för att få optimala resultat.

 

**Varför visar min modell [!UICONTROL Error] status?**

Modellen kunde inte köras. In such cases, please reach out to your [!DNL Adobe] representative.

 

**Hur kan jag byta plats [!UICONTROL Profile Merge Rule] för en [!UICONTROL Predictive Audiences][!UICONTROL segment]?**

Skapa en ny modell genom att välja samma personer och målgrupp som din tidigare modell. Tilldela en annan modell när en modell skapas [!UICONTROL Profile Merge Rule].

>[!WARNING]
> Du kan också använda [Segment Builder](../features/segments/segment-builder.md) för att manuellt skapa en [!UICONTROL segment] med en befintlig prediktiv [!UICONTROL trait] och tilldela den ett [!UICONTROL Profile Merge Rule] alternativ.
> 
> Vi rekommenderar dock inte den här metoden, eftersom prediktiv [!UICONTROL traits] automatiskt ärver [!UICONTROL Profile Merge Rule] av modellen som de tillhör och de byggs utifrån inflytelserik [!UICONTROL traits] som uppfyller [!UICONTROL Profile Merge Rule] modellens krav.

 

**Vad [!UICONTROL Profile Merge Rule] ska jag välja?**

När du väljer [!UICONTROL Profile Merge Rule] en modell ska du noggrant analysera hur den används.

Anta att målgruppen [!UICONTROL segment] använder en [!UICONTROL Profile Merge Rule] baserad profil + [!DNL Device Graph] profiler och att ni väljer samma [!UICONTROL Profile Merge Rule] för prediktiva [!UICONTROL segments]profiler. I det här fallet [!UICONTROL traits] kommer både enhetsnivå och enhetsnivå att användas för att utbilda modellen och användarens placering i en prediktiv [!UICONTROL segment].

Om du väljer en enhet som endast är [!UICONTROL Profile Merge Rule] baserad på enhetsprofiler [!UICONTROL traits] blir ingen av dina enheter inflytelserik och bidrar inte till att användarna placeras i ett prediktivt perspektiv [!UICONTROL segment]. Detta kan påverka modellens noggrannhet och räckvidd negativt.

Analysera användningsexemplen noggrant och bestäm vilka [!UICONTROL trait] typer du vill att modellen ska lära sig av och vilken typ av data du vill att modellen ska använda för klassificering.

**Går det att klassificera en användare från målgruppen som inte är en del av något persona-trait/segment?**

Nej, användaren måste ha några traits i sin profil. Om inte får användaren matchningspoängen 0 för alla persona traits/segment och kommer därför inte att klassificeras i något av de prediktiva segmenten.

 

**Kan en användare som klassificerats i ett av de prediktiva segmenten omklassificeras till ett annat [!UICONTROL Predictive Audiences]-segment?**

Ja. Eftersom algoritmen tränas dagligen tillämpas ändringarna i varje persona när det gäller poängsättning för traits. Om en användare som är en del av ett [!UICONTROL Predictive Audiences]-segment är aktiv kan ändringar i deras trait-poäng ändra klassificeringen baserat på de senaste 30 dagarnas aktiviteter.

 

**Kan jag se vilka traits som används för målgruppsklassificering?**

Ja, du kan se alla viktiga traits för alla baslinjer på modellrapporteringssidan. Se [Viktiga traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Vad händer med modellen om jag redigerar ett baslinje-trait eller segment?**

Modellen utvärderar traits eller segmenten en gång om dagen. Du bör se den uppdaterade klassificeringen dagen efter uppdateringen.

 

**Kan jag välja de datakällor som modellen ska använda för inlärning?**

Nej, val av datakällor stöds inte. [!UICONTROL Predictive Audiences]-algoritmen lär sig av alla era förstaparts-traits.