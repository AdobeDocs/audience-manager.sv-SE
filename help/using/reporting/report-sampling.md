---
description: En sammanfattning av den provtagningsmetod som används för vissa rapporter, felfrekvenser vid provtagning och en lista över rapporter som returnerar information baserat på provdata.
seo-description: En sammanfattning av den provtagningsmetod som används för vissa rapporter, felfrekvenser vid provtagning och en lista över rapporter som returnerar information baserat på provdata.
seo-title: Datainsamling och felfrekvens i valda rapporter för Audience Manager
solution: Audience Manager
title: Datainsamling och felfrekvens i valda rapporter för Audience Manager
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 33d844578c5cd620f9d4c33ec931ae0778aabb07
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 7%

---


# Datainsamling och felfrekvens i valda rapporter för Audience Manager{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

En sammanfattning av den provtagningsmetod som används för vissa rapporter, felfrekvenser vid provtagning och en lista över rapporter som returnerar information baserat på provdata.

## Samplingsförhållande för data {#data-sampling-ratio}

I vissa [!DNL Audience Manager] rapporter visas resultat som baseras på en uppsättning av den totala mängden tillgängliga data. Samplade data-förhållandet är 1:54. För rapporter där exempeldata används innebär detta att resultaten baseras på 1 post av varje uppsättning med 54 poster.

Dessa rapporter använder statistiska provdata eftersom de behöver en enorm mängd datorkraft för att generera resultat. Sampling hjälper till att hitta en balans mellan minskade datorkrav, bibehållna systemprestanda och ge korrekta resultat.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Felfrekvens {#error-rates}

Fel kan uppstå i rapporter som genererar överlappande data. Ett fel definieras som procentandelen poster som:

* Bör inte ha inkluderats i en rapport men har ändå lagts till.
* Bör ha tagits med i en rapport men utelämnats.

Observera att våra tester och modeller visar att felfrekvensen *minskar* i en omvänd proportion till antalet poster i datauppsättningen. Datauppsättningar med många poster genererar färre fel än uppsättningar med ett litet antal poster. Låt oss titta på detta påstående mer kvantitativt. Som framgår av följande tabell kommer 95 % av rapportresultaten att ligga under en viss felfrekvens för ett visst antal poster.

| Antal poster | Felfrekvens |
|--- |--- |
| 500 - 1,000 | 95 % har en felfrekvens på 42 %. |
| 1,000 - 1,500 | 95 % har en felfrekvens på 34 %. |
| 10,000 - 50,000 | 95 % har en felfrekvens på 14 %. |
| 50,000 | 95 % har en felfrekvens på 6 %. |
| 100,000 | 95 % har en felfrekvens på 4 %. |
| 500 000 (eller fler) | 95 % har en felfrekvens på 2 %. |

## Använda metoden för Minhash-provtagning {#minhash}

Baserat på metoden för [Minhash](https://en.wikipedia.org/wiki/MinHash) -provtagning använder Audience Manager en ny metod för att beräkna trait- och segment-uppskattare ovanpå en enpermutation-hash-skiss. Den här nya metoden ger en lägre varians än standarduppskattaren för Jaccard-likhetsberäkning. Se avsnittet nedan för de rapporter som använder denna metod.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Rapporter som använder provdata {#reports-using-sampled-data}

De [!DNL Audience Manager] rapporter som använder statistiska provdata och metoden för Minhash-provtagning omfattar följande:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Statistisk sampling | Provtagningsmetod för minhash |
|--- |--- |
| [Adresserbara målgruppsdata](../features/addressable-audiences.md) (data på kund- och segmentnivå). | [Överlappningsrapporter](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait och segment-to-segment) |
| Måttet [för totala enheter](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) för en [!UICONTROL Profile Merge Rule]. | [Trait-rekommendationer](/help/using/features/segments/trait-recommendations.md) |
| [Datan Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) använder exempeldata på [!UICONTROL Search] fliken och alla [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
