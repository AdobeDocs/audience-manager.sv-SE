---
description: Kalkylbladen för att skapa och uppdatera accepterar ett traitRule-huvud som gör att du kan tillämpa flera regler i en enda åtgärd. Följ de här instruktionerna för att göra gruppregelförfrågningar.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Skapa eller uppdatera dragregler och segmentregler
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Skapa eller uppdatera dragregler och segmentregler{#create-or-update-trait-rules-and-segment-rules}

Kalkylbladen för att skapa och uppdatera accepterar ett traitRule-huvud som gör att du kan tillämpa flera regler i en enda åtgärd. Följ de här instruktionerna för att göra gruppregelförfrågningar.

>[!IMPORTANT]
>
>Masshanteringsverktygen är inte ett officiellt Adobe-erbjudande som stöds. Felsökning och support via kundtjänst hanteras från fall till fall.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i användargränssnittet för [!DNL Audience Manager] respekteras i [!UICONTROL Bulk Management Tools].

## Arbeta med varumärkesregler {#trait-rules}

I kalkylbladet returneras och accepteras regler som består av booleska uttryck, jämförelseoperatorer och reguljära uttryck. Du kan skapa regler med trait eller segment builder i [!DNL Audience Manager] och kopiera dem till ditt kalkylblad. Eller om du känner till regelsyntaxen kan du skriva uttryck direkt i kalkylbladen.

## Exempel på regelverktyg {#rule-builder-example}

Låt oss ta en titt på ett exempel som visar hur du kan använda [!UICONTROL Segment Builder] för att skapa en regel som du kan använda i arbetsbladet. Det här är dock inte en uppsättning stegvisa instruktioner för dessa verktyg. Istället ska vi börja med en enkel regel som redan har skapats. Instruktioner om hur du använder regelbyggare finns i [Segment Builder](../../features/segments/segment-builder.md) och [Trait Builder](../../features/traits/about-trait-builder.md).

Med det visuella regelverktyget har vi skapat en segmentregel med 3 egenskaper och en boolesk [!UICONTROL AND]-operator.

![](assets/visualrule.png)

Klicka på **[!UICONTROL Code View]** för att hämta textversionen av den här regeln.

>[!TIP]
>
>Klicka på **[!UICONTROL Validate Expression]** för att kontrollera regellogiken. Detta förhindrar att du överför en ogiltig regel.

![](assets/coderule.png)

Klistra in regeln i kalkylbladet [!UICONTROL Bulk Management Tools] och implementera ändringarna för att uppdatera segmentreglerna samtidigt.

![](assets/segmentrule.png)

## Skapa egna regler {#create-rules}

Du kan skriva egna regler utanför [!UICONTROL Rule Builder]. Innan du börjar bör du läsa dokumentationen som beskriver t.ex. operatorer, uttryck och obligatoriska variabler. Vi rekommenderar att du går igenom följande:

* [Arbeta med jämförelseoperatorer i Trait Builder](../../features/traits/trait-comparison-operators.md)
* [Åtgärdsordning](../../features/traits/trait-operator-precedence.md)
* [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md)
* [Exempeluttryck med booleska operatorer och jämförelseoperatorer](../../features/traits/trait-expression-samples.md)
