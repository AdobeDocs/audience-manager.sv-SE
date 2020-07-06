---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-title: Vanliga frågor om Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

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

 

**Varför klassificeras inte vissa av mina registrerade besökare?**

För närvarande fungerar målgruppsklassificering bara i realtid, med undantag för autentiserade användare som definierats som en del av [!UICONTROL Profile Merge Rules].

Fullt stöd för registrerade data kommer att läggas till i en framtida uppdatering.

 

**När kan jag se de första resultaten från min modell?**

Resultat från [!UICONTROL Predictive Audiences]-modeller är tillgängliga inom 24 timmar efter att modellen har skapats, om modellen fungerar som den ska.

Om modellen inte ger några resultat inom 24 timmar kan du kontakta din Adobe-representant.

 

**Varför producerar min modell inga resultat eller varför visas varningsstatus?**

[!UICONTROL Predictive Audiences]-modeller kanske inte ger resultat på grund av en rad orsaker:

1. Inga av de traits/segment som valts för personan har tillräckligt många användarprofiler. Vi rekommenderar att du väljer traits eller segment så att varje persona har minst några hundra användarprofiler.
1. Inga av de traits/segment som valts för personan har tillräckligt med data i användarprofilerna (inte tillräckligt med traits att analysera).
1. Målgruppens traits/segment har inga aktiva eller registrerade användare under de senaste 30 dagarna.
1. De målgruppsanvändare som varit aktiva eller registrerade under de senaste 30 dagarna har inte tillräckligt med data i sina användarprofiler (inte tillräckligt med traits att analysera).

För att få relevanta resultat utvärderar [!UICONTROL Predictive Audiences]-algoritmen traits och segment baserade på användaraktivitet i realtid som identifieras av DCS. Om du väljer nya bas-traits och segment som ännu inte har tillräckligt många användare kan det ta några dagar innan algoritmen kan klassificera målgruppen.

Följ de föreslagna riktlinjerna i [Urvalskriterier för personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) och [Urvalskriterier för målgrupp](../features/algorithmic-models/predictive-audiences.md#selection-audience) för att få optimala resultat.

 

**Varför visas felstatus för min modell?**

Modellen kunde inte köras. Kontakta i så fall din Adobe-representant.

 

**Hur ändrar jag regeln för profilsammanslagning för ett Predictive Audiences-segment?**

Duplicera [!UICONTROL Predictive Audiences]-segmentet och ändra [!UICONTROL Profile Merge Rule] för det duplicerade segmentet.

 

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