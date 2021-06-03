---
description: Look-Alike Modeling hjälper er att identifiera nya, unika målgrupper genom automatiserad dataanalys. I den här artikeln finns svar på de vanligaste frågorna.
seo-description: Look-Alike Modeling hjälper er att identifiera nya, unika målgrupper genom automatiserad dataanalys. I den här artikeln finns svar på de vanligaste frågorna.
seo-title: Vanliga frågor om lookalike-modellering
solution: Audience Manager
title: Vanliga frågor om lookalike-modellering
feature: Algoritmiska modeller
source-git-commit: cf9368d4690b61066646054543cc60d390eea021
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Vanliga frågor om lookalike-modellering

## Översikt {#overview}

I den här artikeln finns svar på de vanligaste frågorna om [!UICONTROL Look-Alike Modeling].

## Frågor {#questions}

**Varför får jag ett platt  [!UICONTROL Accuracy & Reach] diagram?**

Ett platt [!UICONTROL Accuracy & Reach]-diagram innebär att nästan alla användare fick samma poäng av modellen. Detta kan inträffa när du inkluderar besökaregenskaper på platsen i de datakällor som du körde modellen på. Du undviker detta genom att ta bort det generiska attributet från modellindata när du skapar modellen med hjälp av fältet [!UICONTROL Exclusions].

 

**Varför har några av mina största inflytelserika egenskaper mycket små målgrupper?**

Algoritmen väljer egenskaper som är mycket korrelerade med baslinjetrafiken. Om en viss egenskap till exempel till 100 % överlappar den ursprungliga egenskapen kommer den att ha en mycket hög vikt, även om antalet användare i den egenskapen är litet.

 

**Varför har min modell inte körts/körts om?**

Modeller som har gett resultat kommer att fortsätta att köras endast om du har skapat minst en aktiv algoritmisk egenskap och mappat den till ett aktivt segment och ett mål.

 

**Varför gav min modell inga resultat?**

Detta orsakas vanligtvis av att det inte finns någon signifikant skillnad i egenskaper mellan den ursprungliga populationen och populationen i de valda datakällorna.

 

**Finns det någon rekommendation för baslinjestöd eller segmentstorlek?**

Ett fåtal tusen användare bör vara tillräckligt för att köra modellen på, eftersom det finns en betydande trait-överlappning mellan baslinjepopulationen och populationen i de valda datakällorna. [!UICONTROL Look-Alike Modeling] ger exaktare resultat, ju större baslinjen är.

 

**Vilka datakällor från tredje part ska jag välja för min modell?**

Använd datakällor som åtminstone delvis överlappar ditt baslinjefärg/baslinjesegment, men som samtidigt tar med fler användare. Du bör också ta hänsyn till kostnaden för varje datafeed. Kostnads- och prissättningsmodeller varierar mellan olika dataleverantörer i [!UICONTROL Audience Marketplace].

 

**Kostar det att använda data från tredje part för modellering?**

Det beror på prismodellen för vald datafeed. Vissa flöden gör det möjligt att modellera utan kostnad, medan andra tar ut en avgift. Mer information finns i [Fakturering för köpare av dataflöden](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md).

 

**Hur många modeller/egenskaper får jag skapa?**

För närvarande kan du skapa upp till 20 algoritmiska modeller och 50 algoritmiska egenskaper.

 

**Vilken uppdateringsfrekvens har modellutbildningen och den algoritmiska trait-populationen?**

Modellen utväxlas en gång var 8:e dag, tillsammans med en uppdatering av populationen av algoritmiska egenskaper.