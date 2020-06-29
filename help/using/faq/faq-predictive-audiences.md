---
description: Med prediktiva målgrupper kan ni klassificera okända målgrupper i distinkta personligheter i realtid med datavetenskap.
seo-description: Med prediktiva målgrupper kan ni klassificera okända målgrupper i distinkta personligheter i realtid med datavetenskap.
seo-title: Vanliga frågor om prediktiva målgrupper
solution: Audience Manager
title: Audience Manager prediktiva målgrupper
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---


# Vanliga frågor om prediktiva målgrupper

Frågor och svar om [!UICONTROL Predictive Audiences].

 

**När ska jag använda[!UICONTROL Predictive Audiences]istället för[!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] och [!UICONTROL Look-alike modeling] kan användas på olika sätt. De viktigaste skillnaderna mellan de två algoritmerna är följande:

1. [!UICONTROL Look-alike modeling] tar en liten publik som indata och utökar den. [!UICONTROL Predictive Audiences] tar en stor publik som indata och delar in den i mindre distinkta målgrupper, som definieras av era personligheter.
1. Antalet bassegment är olika för varje algoritm. [!UICONTROL Predictive Audiences] kräver minst två baslinjer, medan en baslinje [!UICONTROL Look-alike modeling] används som mest.
1. [!UICONTROL Predictive Audiences] utför segmentutvärdering i realtid, men [!UICONTROL Look-alike modeling] inte.

Beroende på ditt sätt att arbeta bör du bestämma vilken modell som är mer relevant för dig.

Man kan tänka sig att bygga en [!UICONTROL Predictive Audiences] modell med ett antal baslinjer som motsvarar att bygga samma antal lookalike-modeller, endast utan realtidsutvärderingen, och med en mycket hög sannolikhet att besökare som tillhör flera olika personligheter istället för en enda distinkt persona.

 

**Hur många profiler/modeller får jag skapa?**

Du kan skapa upp till 10 [!UICONTROL Predictive Audiences] modeller. För varje modell kan du definiera upp till 50 baslinjetrafik eller segment.

 

**Hur skapar jag nya segment från ett[!UICONTROL Predictive Audiences]segment?**

Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** och klicka på **[!UICONTROL Predictive Audiences]** mappen. Hitta det önskade segmentet, duplicera det och redigera det efter behov.

 

**Varför klassificeras några av mina ombord-besökare inte?**

För närvarande fungerar målgruppsklassificering bara för realtidskvalifikationer, med undantag för autentiserade användare som definierats som en del av [!UICONTROL Profile Merge Rules].

Fullt stöd för inbyggda data kommer att läggas till i en framtida uppdatering.

 

**När kan jag se de första resultaten från min modell?**

[!UICONTROL Predictive Audiences] modellresultaten är tillgängliga inom 24 timmar efter att modellen har skapats, om modellen fungerar som den ska.

Om modellen inte ger några resultat inom 24 timmar kan du kontakta din Adobe-representant.

 

**Varför producerar min modell inga resultat eller visar varningsstatusen?**

[!UICONTROL Predictive Audiences] modeller kan inte ge resultat på grund av en rad orsaker:

1. Ingen av de valda egenskaperna/segmenten har tillräckligt många användarprofiler. Vi rekommenderar att du väljer egenskaper eller segment så att varje person har minst några hundra användarprofiler.
1. Ingen av de valda egenskaperna/segmenten har tillräckligt med data i sina användarprofiler (inte tillräckligt med egenskaper för att analysera).
1. Målgruppens trait/segment hade inga aktiva eller engagerade användare under de senaste 30 dagarna.
1. De målgruppsanvändare som var aktiva eller introducerade under de senaste 30 dagarna har inte tillräckligt med data i sina användarprofiler (inte tillräckligt med egenskaper för att analysera).

För att få relevanta resultat utvärderar algoritmen [!UICONTROL Predictive Audiences] trait- och segment-realisationer baserat på användaraktivitet i realtid som ses av DCS. Om du väljer nya basegenskaper och segment som ännu inte har tillräckligt många användare kan det ta några dagar innan algoritmen kan klassificera målgruppen.

För att få bästa möjliga resultat bör du följa de föreslagna riktlinjerna från [urvalskriterier för personer](../features/algorithmic-models/predictive-audiences.md#selection-personas) och [urvalskriterier för Target-målgrupp](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Varför visas felstatusen i min modell?**

Modellen kunde inte köras. Kontakta i så fall din Adobe-representant.

 

**Hur ändrar jag profilkopplingsregeln för ett segment för prediktiva målgrupper?**

Duplicera [!UICONTROL Predictive Audiences] segmentet och ändra [!UICONTROL Profile Merge Rule] för det duplicerade segmentet.

 

**Kan en användare från målgruppen som inte är en del av något persona trait/segment inte klassificeras?**

Ja, om användaren inte har några egenskaper i profilen. I så fall får användaren matchningspoängen 0 för alla persona traits/segment, och kommer därför inte att klassificeras i något av de prediktiva segmenten.

 

**Kan en användare som klassificerats i ett av de prediktiva segmenten omklassificeras till ett annat[!UICONTROL Predictive Audiences]segment?**

Ja. Eftersom algoritmen är utbildad dagligen tillämpas ändringarna för var och en av personerna i fråga om poängsättning för egenskaper. Om en användare som är en del av ett [!UICONTROL Predictive Audiences] segment är aktiv kan ändringarna i deras egen poäng ändra klassificeringen baserat på den senaste 30-dagarsaktiviteten.

 

**Kan jag se vilka egenskaper som ligger till grund för målgruppsklassificeringen?**

Ja, du kan se alla inflytelserika egenskaper för alla baslinjer på modellrapporteringssidan. Se [Influentiella egenskaper](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Vad händer med modellen om jag redigerar någon av dess baslinjetrafik eller segment?**

Modellen utvärderar egenskaperna eller segmenten en en gång om dagen. Du bör se den uppdaterade klassificeringen dagen efter uppdateringen.

 

**Kan jag välja de datakällor som modellen ska lära sig av?**

Nej, val av datakällor stöds inte. Algoritmen lär sig av alla era egenskaper hos den första parten. [!UICONTROL Predictive Audiences]