---
description: I den här artikeln beskrivs de jämförelseoperatorer som används av Trait Builder.
seo-description: I den här artikeln beskrivs de jämförelseoperatorer som används av Trait Builder.
seo-title: Arbeta med jämförelseoperatorer i Trait Builder
solution: Audience Manager
title: Arbeta med jämförelseoperatorer i Trait Builder
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---


# Arbeta med jämförelseoperatorer i Trait Builder {#working-with-comparison-operators-in-trait-builder}

I den här artikeln beskrivs de jämförelseoperatorer som används av [!UICONTROL Trait Builder].

## Syfte med jämförelseoperatorer

<!-- c_tb_comparison_operators.xml -->

Jämförelseoperatorer (eller relationsoperatorer) används för att jämföra, testa eller utvärdera förhållandet mellan olika värden. I [!UICONTROL Trait Builder]och med jämförelseoperatorerna kan du testa relationen mellan olika nyckelvärdepar när du bygger signalregler. Du kan till exempel skapa en signalregel som definierar en målgrupp för dyra kameramarkare. I det här fallet kan du skapa ett nyckelvärdepar för kamera/pris och kvalificera en användare om de har letat efter en kamera med ett pris som är lika med eller större än ett angivet värde.

## Fördelar med jämförelseoperatorer

Jämförelseoperatorer är användbara när du behöver utvärdera och skapa egenskaper baserat på flera värden. Om man tittar på priserna på varor och tjänster kan detta illustreras. Ditt företag kanske till exempel vill identifiera besökare baserat på priserna på de produkter de visar. Det kan dock vara administrativt ineffektivt att definiera enskilda segment baserat på specifika värden. Jämförelseoperatorer hjälper till att övervinna detta hinder genom att etablera segmenteringsutlösare baserat på priströsklar eller intervall.

## Jämförelseoperatorer

Du kan skapa regler med följande jämförelseoperatorer:

| Operator | Definition |
|---|---|
| **==** | Lika med |
| **!=** | Inte lika med |
| **>** | Större än |
| **&lt;** | Mindre än |
| **=>** | Större än/lika med |
| **&lt;=** | Mindre än/lika med |

## Namngivna operatorer

Du kan skapa regler med följande namngivna operatorer:

| Operator | Utvärderar till [!DNL True] När |
|---|---|
| **[!UICONTROL Contains]** | Värdet i ett nyckelvärdepar *innehåller* tecken som anges av den här operatorn. |
| **[!UICONTROL Matcheswords]** | Värdet i ett nyckelvärdepar *matchar* mönstret som anges av den här operatorn. |
| **[!UICONTROL Startswith]** | Värdet i ett nyckelvärdepar *börjar med* tecken som anges av den här operatorn. |
| **[!UICONTROL Endswith]** | Värdet i ett nyckelvärdepar *avslutas med* de tecken som anges av operatorn. |
| **[!UICONTROL Matchesregex]** | Värdet i ett nyckelvärdepar *matchar* mönstret som anges av ett reguljärt uttryck. [Läs mer](../../features/traits/trait-builder-regex.md) om hur du använder reguljära uttryck i [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Booleska uttryck i Trait och Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [Booleska uttryck i TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Åtgärdsordning i TraitBuilder-uttryck](../../features/traits/trait-operator-precedence.md)
>* [Exempeluttryck med booleska operatorer och jämförelseoperatorer](../../features/traits/trait-expression-samples.md)

