---
description: Med Segment Builder kan du skapa regler för ett segment med hjälp av en kodredigerare. Klicka på fliken Segmentuttryck (kodvyn) på panelen Traits för att komma åt den här funktionen.
seo-description: Med Segment Builder kan du skapa regler för ett segment med hjälp av en kodredigerare. Klicka på fliken Segmentuttryck (kodvyn) på panelen Traits för att komma åt den här funktionen.
seo-title: Kodsyntax som används i segmentuttrycksredigeraren
solution: Audience Manager
title: Kodsyntax som används i segmentuttrycksredigeraren
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Kodsyntax som används i segmentuttrycksredigeraren {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] Med kan du skapa trait-regler för ett segment med hjälp av en kodredigerare. Klicka på **[!UICONTROL Segment Expressions (Code View)]** fliken på [!UICONTROL Traits] panelen för att komma åt den här funktionen.

## Syntax för Expression Builder-kod

Du kan lägga till trait-regler till ett segment med kod i stället för att använda dra och släpp-funktioner. Ersätt kursiverade element i exemplet med ett faktiskt uttryck eller värde vid kodning. Baskoden har följande syntax:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Som standard används [!DNL Boolean] [!UICONTROL OR] villkor för flera egenskaper *inom* ett uttryck.

### Förena segment med booleska operatorer

Om du vill skapa grupper av segment omsluter du frekvensfunktionen inom parentes och anger relationen *mellan* varje uttryck med en [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR]och [!UICONTROL NOT]).

### Parametrar

>[!NOTE]
>
>Alla parametrar är obligatoriska om inget annat anges.

| Namn eller variabel | Beskrivning |
|---|---|
| `FREQUENCY` | En litteral som måste föregå uttrycket. |
| ` [`&lt;`traitID`>`T]` | En array med trait-ID:n följt av bokstaven `T`. Avgränsa flera egenskaper med kommatecken. Exempel, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Valfritt)* Anger regler för senaste intervall för egenskaper i segmentet. Bokstaven `D` anger senaste i dagar. |
| ` <Frequency Operator><Numeric Value>` | Anger frekvensregler för egenskaper i segmentet. |

### Tillåtna operatorer för senaste och frekvens

Ange [intervall för senaste och frekvens](../../features/segments/recency-and-frequency.md) med en jämförelseoperator och ett heltal. [!UICONTROL Segment Builder] använder standarduttryck som &lt; (mindre än), > (större än), == (lika med) osv. Typerna av tillåtna operatorer varierar dock när du anger senaste eller frekvens. Tabellen nedan visar de tillåtna operatorerna för senaste/frekvens.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Senaste operatorer </th> 
   <th colname="col2" class="entry"> Frekvensoperatorer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (större än/lika med) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (mindre än/lika med) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (större än/lika med) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (mindre än/lika med) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (lika med) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Nyhet och frekvens](../../features/segments/recency-and-frequency.md)
>* [Booleska uttryck i Trait och Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [Arbeta med jämförelseoperatorer i TraitBuilder](../../features/traits/trait-comparison-operators.md)
>* [Åtgärdsordning i TraitBuilder-uttryck](../../features/traits/trait-operator-precedence.md)

