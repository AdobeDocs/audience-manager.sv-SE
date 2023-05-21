---
description: Kalkylbladen för att skapa och uppdatera accepterar ett traitRule-huvud som gör att du kan tillämpa flera regler i en enda åtgärd. Följ de här instruktionerna för att göra gruppregelförfrågningar.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Skapa eller uppdatera trait-regler och segmentregler
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 8%

---

# Skapa eller uppdatera trait-regler och segmentregler{#create-or-update-trait-rules-and-segment-rules}

Kalkylbladen för att skapa och uppdatera accepterar ett traitRule-huvud som gör att du kan tillämpa flera regler i en enda åtgärd. Följ de här instruktionerna för att göra gruppregelförfrågningar.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som har tilldelats i [!DNL Audience Manager] Gränssnittet respekteras i [!UICONTROL Bulk Management Tools].

## Arbeta med varumärkesregler {#trait-rules}

I kalkylbladet returneras och accepteras regler som består av booleska uttryck, jämförelseoperatorer och reguljära uttryck. Du kan skapa regler med trait eller segment builder i [!DNL Audience Manager] och kopiera dem till ditt kalkylblad. Eller om du känner till regelsyntaxen kan du skriva uttryck direkt i kalkylbladen.

## Exempel på regelverktyg {#rule-builder-example}

Låt oss titta på ett exempel som visar hur man använder [!UICONTROL Segment Builder] om du vill skapa en regel som du kan använda på kalkylbladet. Det här är dock inte en uppsättning stegvisa instruktioner för dessa verktyg. Istället ska vi börja med en enkel regel som redan har skapats. Instruktioner om hur du använder regelbyggaren finns i [Segment Builder](../../features/segments/segment-builder.md) och [Trait Builder](../../features/traits/about-trait-builder.md).

Med det visuella regelverktyget har vi skapat en segmentregel med tre egenskaper och en boolesk [!UICONTROL AND] -operator.

![](assets/visualrule.png)

Klicka **[!UICONTROL Code View]** om du vill hämta textversionen av den här regeln.

>[!TIP]
>
>Klicka **[!UICONTROL Validate Expression]** för att kontrollera regellogiken. Detta förhindrar att du överför en ogiltig regel.

![](assets/coderule.png)

Klistra in regeln i [!UICONTROL Bulk Management Tools] kalkylblad och implementera dina ändringar för att uppdatera segmentreglerna i grupp.

![](assets/segmentrule.png)

## Skapa egna regler {#create-rules}

Du kan skriva egna regler utanför [!UICONTROL Rule Builder]. Innan du börjar bör du läsa dokumentationen som innehåller funktioner som operatorer, uttryck och obligatoriska variabler. Vi rekommenderar att du går igenom följande:

* [Arbeta med jämförelseoperatorer i Trait Builder](../../features/traits/trait-comparison-operators.md)
* [Operationsordning](../../features/traits/trait-operator-precedence.md)
* [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md)
* [Exempeluttryck med booleska operatorer och jämförelseoperatorer](../../features/traits/trait-expression-samples.md)
