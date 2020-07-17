---
description: Beskriver de algoritmiska modeller som finns i Audience Manager.
keywords: algo models how works predictive audiences
seo-description: Beskriver de algoritmiska modeller som finns i Audience Manager.
seo-title: Översikt över algoritmiska modeller
solution: Audience Manager
title: Översikt över algoritmiska modeller
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 15%

---


# Översikt över algoritmiska modeller

## Vad är algoritmisk modellering?{#what-algo-modeling}

Algoritmisk modellering i Audience Manager avser användningen av datavetenskap för att antingen utöka era befintliga målgrupper eller klassificera dem som personaliserade.

Detta görs med hjälp av två typer av algoritmer: [!UICONTROL Look-Alike Modeling] och [!UICONTROL Predictive Audiences].

## Look-alike-modellering{#lam}

[!UICONTROL Look-Alike Modeling] hjälper er att identifiera nya, unika målgrupper genom automatiserad dataanalys. Processen startar när du väljer ett trait- eller segment, ett tidsintervall samt datakällor från första och tredje part. Dina val innehåller indata för den algoritmiska modellen. När analysprocessen körs letar programmet efter berättigade användare baserat på delade egenskaper från den valda populationen.

När du är klar är dessa data tillgängliga i [Trait Builder](../../features/traits/about-trait-builder.md) där du kan använda dem för att skapa egenskaper baserat på [precision och räckvidd](../../features/traits/trait-accuracy-reach.md). Dessutom kan du skapa segment som kombinerar algoritmiska egenskaper med regelbaserade egenskaper och lägga till andra kvalificeringskrav med booleska uttryck och jämförelseoperatorer.

[!UICONTROL Look-Alike Modeling] ger dig ett dynamiskt sätt att extrahera värde från alla tillgängliga trait-data.

Mer information [!UICONTROL Look-Alike Modeling]finns i [Understanding Look-Alike Modeling](understanding-models.md).

## Predictive Audiences{#predictive-audiences}

[!UICONTROL Predictive Audiences] hjälper er att klassificera en okänd publik i distinkta personligheter, i realtid, med avancerad datavetenskap.

I marknadsföringssammanhang är en persona ett målgruppssegment som definieras av besökare, användare eller potentiella köpare som delar en viss uppsättning traits som demografi, surfvanor, shoppinghistorik osv.

[!UICONTROL Predictive Audiences] modeller tar detta koncept ett steg längre genom att använda Audience Manager maskininlärningsfunktioner för att automatiskt klassificera okända målgrupper i distinkta personligheter. Audience Manager uppnår detta genom att beräkna hur känslig din okända publik är för en uppsättning kända målgrupper.

Mer information [!UICONTROL Predictive Audiences]finns i [Predictive Audiences Overview](predictive-audiences.md).
