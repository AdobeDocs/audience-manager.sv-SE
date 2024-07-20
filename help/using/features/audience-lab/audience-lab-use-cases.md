---
description: Med Audience Lab kan du använda flera användningsfall genom att använda baslinjesegment för att skapa testgrupper. Du kan dela in testgrupper i flera ömsesidigt uteslutande testsegment, mappa dessa till olika destinationer och sedan avgöra vilka av segmenten som är mest effektiva vid konvertering.
seo-description: Audience Lab enables several use cases by allowing you to use baseline segments for creating test groups. You can divide test groups into several mutually exclusive test segments, map these to different destinations and then determine which of the segments are most effective in driving conversions.
seo-title: Audience Lab Use Cases
solution: Audience Manager
title: Användningsexempel för Audience Lab
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
exl-id: b68f48bd-0d5d-4b72-84f3-a6f3acea6c49
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Användningsexempel för Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] aktiverar flera användningsfall genom att du kan använda baslinjesegment för att skapa testgrupper. Du kan dela in testgrupper i flera ömsesidigt uteslutande testsegment, mappa dessa till olika destinationer och sedan avgöra vilka av segmenten som är mest effektiva vid konvertering.

## Jämför modeller i Audience Lab {#compare-models}

Du kan använda flera olika typer och källor för modeller i [!DNL Audience Manager]. [!UICONTROL Audience Lab] erbjuder ett enkelt sätt att jämföra dina kunders konverteringsgrader i alla dina aktiva modeller.

<!-- audience-lab-compare-models.xml -->

I det här fallet jämför du olika modeller. Du kan antingen använda modeller som har skapats via ett internt datalager och importera dem i [!DNL Audience Manager] som [Onboardtraits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) eller använda funktionen [Algoritmiska modeller](../../features/algorithmic-models/understanding-models.md) i [!DNL Audience Manager].

1. Skapa två modeller, antingen i [modellbyggaren](../../features/algorithmic-models/create-model.md) eller via en extern plattform.
1. Skapa [algoritmiska egenskaper](../../features/traits/create-algorithmic-traits.md) från den algoritmiska modellen eller importera dina egna modeller som anpassade egenskaper.
1. Skapa segment som utesluter varandra så att användarna i båda modellerna inte överlappar varandra:

   * Skapa ett *Modell 1-segment* och ett *Modell 2-segment*.
   * Ha segmentregeln för *modell 1 segment* som modell 1 trait [!DNL AND NOT] modell 2 trait och vice versa för *modell 2 segment*.

1. [Skapa två segmenttestgrupper](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) i [!UICONTROL Audience Lab], en med *Model 1 Segment* som baslinje, den andra med *Model 2 Segment* som baslinje.

   * Använd samma variabler för båda testgrupperna: samma mål, kreativa egenskaper och konverteringsegenskaper.
   * Se till att testsegmenten har liknande antal användare (1,6 miljoner och 1,8 miljoner är bra, 1,6 miljoner och 16 miljoner är inte det).
   * Reservera ett kontrollsegment i varje testsegmentets testgrupp. På så sätt kan du avsätta en liten del av varje segment och inte explicit rikta in dem på testet.

1. Granska resultaten:

   * [Audience Lab-rapportvyn](../../features/audience-lab/audience-lab-reporting-view.md) visar antalet konverteringar som varje modell kör. För konverteringsbaserade kampanjer kommer det testsegment som genererar flest konverteringar att beteckna den modell som fungerar bäst.
   * Eftersom du har kontrollsegment kan du även utvärdera hur modellen fungerade jämfört med&quot;standardmålinriktning&quot;. Du testar inte bara en modell jämfört med en annan, utan testar frågan om &quot;Har den här modellen blivit bättre än normala rutiner?&quot;

## Testa kreativa på olika destinationer {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Använd [!UICONTROL Audience Lab] för att mäta antalet konverteringar en kreatör kör mellan olika mål. I det här exemplet kan du även mäta konverteringarna av den kreativa bilden mot naturligt förekommande konverteringar.

1. [Skapa en segmenttestgrupp](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) och välj det segment som du vill testa den kreativa mot som baslinjesegment.
1. Dela baslinjesegmentet i testsegment och kontrollsegment.
1. Mappa testsegmenten till de olika destinationer som du vill testa.
1. Kontrollsegmentet kan behållas och inte mappas till någon destination. Kontrollsegmentet ska inte vara avsett av testets kreatör för att ange en resultatbaslinje för naturligt förekommande konverteringar.
1. Ange ett startdatum och ett slutdatum för testet.
1. Ställ in segmentet och det kreativa i målgrupperna.
1. [Audience Lab-rapportvyn](../../features/audience-lab/audience-lab-reporting-view.md) visar hur många konverteringar den kreativa har över målgrupperna.
1. Eftersom du har skapat ett kontrollsegment kan du även utvärdera hur den kreativa funktionen gjorde mot naturligt förekommande konverteringar. Du testar frågan:&quot;Genererade den här kreativiteten en högre konverteringsgrad än vanligt?&quot;
