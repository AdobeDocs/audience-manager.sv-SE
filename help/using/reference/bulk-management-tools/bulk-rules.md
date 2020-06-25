---
description: Kalkylbladen för att skapa och uppdatera accepterar ett traitRule-huvud som gör att du kan tillämpa flera regler i en enda åtgärd. Följ de här instruktionerna för att göra gruppregelförfrågningar.
seo-description: Kalkylbladen för att skapa och uppdatera accepterar ett traitRule-huvud som gör att du kan tillämpa flera regler i en enda åtgärd. Följ de här instruktionerna för att göra gruppregelförfrågningar.
seo-title: Skapa eller uppdatera dragregler och segmentregler
solution: Audience Manager
title: Skapa eller uppdatera dragregler och segmentregler
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# Skapa eller uppdatera dragregler och segmentregler{#create-or-update-trait-rules-and-segment-rules}

Kalkylbladen för att skapa och uppdatera accepterar ett traitRule-huvud som gör att du kan tillämpa flera regler i en enda åtgärd. Följ de här instruktionerna för att göra gruppregelförfrågningar.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

## Arbeta med varumärkesregler {#trait-rules}

I kalkylbladet returneras och accepteras regler som består av booleska uttryck, jämförelseoperatorer och reguljära uttryck. Du kan skapa regler med trait eller segment builder i [!DNL Audience Manager] och kopiera dem till kalkylbladet. Eller om du känner till regelsyntaxen kan du skriva uttryck direkt i kalkylbladen.

## Exempel på regelverktyg {#rule-builder-example}

Låt oss titta på ett exempel som visar hur du kan använda [!UICONTROL Segment Builder] för att skapa en regel som du kan använda i arbetsbladet. Det här är dock inte en uppsättning stegvisa instruktioner för dessa verktyg. Istället ska vi börja med en enkel regel som redan har skapats. Instruktioner om hur du använder regelbyggare finns i [Segment Builder](../../features/segments/segment-builder.md) och [Trait Builder](../../features/traits/about-trait-builder.md).

Med det visuella regelverktyget har vi skapat en segmentregel med tre egenskaper och en boolesk [!UICONTROL AND] operator.

![](assets/visualrule.png)

Klicka **[!UICONTROL Code View]** för att hämta textversionen av den här regeln.

>[!TIP]
>
>Klicka **[!UICONTROL Validate Expression]** för att kontrollera regellogiken. Detta förhindrar att du överför en ogiltig regel.

![](assets/coderule.png)

Klistra in regeln i [!UICONTROL Bulk Management Tools] kalkylbladet och implementera ändringarna för att uppdatera segmentreglerna samtidigt.

![](assets/segmentrule.png)

## Skapa egna regler {#create-rules}

Du kan skriva egna regler utanför [!UICONTROL Rule Builder]. Innan du börjar bör du läsa dokumentationen som innehåller funktioner som operatorer, uttryck och obligatoriska variabler. Vi rekommenderar att du går igenom följande:

* [Arbeta med jämförelseoperatorer i Trait Builder](../../features/traits/trait-comparison-operators.md)
* [Operationsordning](../../features/traits/trait-operator-precedence.md)
* [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md)
* [Exempeluttryck med booleska operatorer och jämförelseoperatorer](../../features/traits/trait-expression-samples.md)

