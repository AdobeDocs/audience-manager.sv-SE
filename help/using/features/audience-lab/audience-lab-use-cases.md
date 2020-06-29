---
description: Med Audience Lab kan du använda flera användningsfall genom att använda baslinjesegment för att skapa testgrupper. Du kan dela in testgrupper i flera ömsesidigt uteslutande testsegment, mappa dessa till olika destinationer och sedan avgöra vilka av segmenten som är mest effektiva vid konvertering.
seo-description: Med Audience Lab kan du använda flera användningsfall genom att använda baslinjesegment för att skapa testgrupper. Du kan dela in testgrupper i flera ömsesidigt uteslutande testsegment, mappa dessa till olika destinationer och sedan avgöra vilka av segmenten som är mest effektiva vid konvertering.
seo-title: Användningsexempel för Audience Lab
solution: Audience Manager
title: Användningsexempel för Audience Lab
topic: DIL API
uuid: 727bec8a-df9a-40cc-b8a7-e1980d146a84
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---


# Användningsexempel för Audience Lab {#audience-lab-use-cases}

[!UICONTROL Audience Lab] I kan du använda flera användningsfall genom att använda baslinjesegment för att skapa testgrupper. Du kan dela in testgrupper i flera ömsesidigt uteslutande testsegment, mappa dessa till olika destinationer och sedan avgöra vilka av segmenten som är mest effektiva vid konvertering.

## Jämför modeller i Audience Lab {#compare-models}

Du kan använda flera olika typer och källor av modeller i [!DNL Audience Manager]. [!UICONTROL Audience Lab] erbjuder ett enkelt sätt att jämföra kundernas konverteringsgrader i alla era aktiva modeller.

<!-- audience-lab-compare-models.xml -->

I det här fallet jämför du olika modeller. Du kan antingen använda modeller som har skapats via en intern data warehouse och importera dem i [!DNL Audience Manager] form av [onboarding-traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) eller använda funktionen [Algoritmiska modeller](../../features/algorithmic-models/understanding-models.md) i [!DNL Audience Manager].

1. Skapa två modeller, antingen i [Model Builder](../../features/algorithmic-models/create-model.md)eller via en extern plattform.
1. Skapa [algoritmiska egenskaper](../../features/traits/create-algorithmic-traits.md) utifrån den algoritmiska modellen eller importera dina egna modeller som anpassade egenskaper.
1. Skapa segment som utesluter varandra så att användarna i båda modellerna inte överlappar varandra:

   * Skapa ett *modell 1-segment* och ett *modell 2-segment*.
   * Låt segmentregeln för *modell 1-segment* vara modell 1- [!DNL AND NOT] trait modell 2 och vice versa för *modell 2-segment*.

1. [Skapa två segmenttestgrupper](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) i [!UICONTROL Audience Lab], den ena med *modell 1-segment* som baslinje och den andra med *modell 2-segment* som baslinje.

   * Använd samma variabler för båda testgrupperna: samma mål, kreativa egenskaper, konverteringsegenskaper.
   * Se till att testsegmenten har liknande antal användare (1,6 miljoner och 1,8 miljoner är bra, 1,6 miljoner och 16 miljoner är inte det).
   * Reservera ett kontrollsegment i varje testsegmentets testgrupp. På så sätt kan du avsätta en liten del av varje segment och inte explicit rikta in dem på testet.

1. Granska resultaten:

   * I rapportvyn [i](../../features/audience-lab/audience-lab-reporting-view.md) Audience Lab visas antalet konverteringar som varje modell genererar. För konverteringsbaserade kampanjer kommer det testsegment som genererar flest konverteringar att beteckna den modell som fungerar bäst.
   * Eftersom du har kontrollsegment kan du även utvärdera hur modellen fungerade jämfört med&quot;standardmålinriktning&quot;. Du testar inte bara en modell jämfört med en annan, utan testar frågan om &quot;Har den här modellen blivit bättre än normala rutiner?&quot;

## Testa kreativa på olika destinationer {#testing-creatives}

<!-- audience-lab-creatives-across-destinations.xml -->

Använd [!UICONTROL Audience Lab] för att mäta antalet konverteringar en kreatör kör mellan olika destinationer. I det här exemplet kan du även mäta konverteringarna av den kreativa bilden mot naturligt förekommande konverteringar.

1. [Skapa en segmenttestgrupp](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)och välj det segment som du vill testa den kreativa mot som baslinjesegment.
1. Dela baslinjesegmentet i testsegment och kontrollsegment.
1. Mappa testsegmenten till de olika destinationer som du vill testa.
1. Kontrollsegmentet kan behållas och inte mappas till någon destination. Kontrollsegmentet ska inte vara avsett av testets kreatör för att ange en resultatbaslinje för naturligt förekommande konverteringar.
1. Ange ett startdatum och ett slutdatum för testet.
1. Ställ in segmentet och det kreativa i målgrupperna.
1. I [Audience Lab-rapportvyn](../../features/audience-lab/audience-lab-reporting-view.md) visas antalet konverteringar som den kreativa har på sig.
1. Eftersom du har skapat ett kontrollsegment kan du även utvärdera hur den kreativa funktionen gjorde mot naturligt förekommande konverteringar. Du testar frågan: &quot;Genererade den här kreativiteten en högre konverteringsgrad än vanligt?&quot;
