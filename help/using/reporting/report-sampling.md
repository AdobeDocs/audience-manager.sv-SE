---
description: En sammanfattning av den provtagningsmetod som används för vissa rapporter, felfrekvenser vid provtagning och en lista över rapporter som returnerar information baserat på provdata.
seo-description: En sammanfattning av den provtagningsmetod som används för vissa rapporter, felfrekvenser vid provtagning och en lista över rapporter som returnerar information baserat på provdata.
seo-title: Datainsamling och felfrekvens i valda rapporter för Audience Manager
solution: Audience Manager
title: Datainsamling och felfrekvens i valda rapporter för Audience Manager
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Datainsamling och felfrekvens i valda rapporter för Audience Manager{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

En sammanfattning av den provtagningsmetod som används för vissa rapporter, felfrekvenser vid provtagning och en lista över rapporter som returnerar information baserat på provdata.

## Samplingsfrekvens för data och minimikrav {#data-sampling-ratio}

I vissa [!DNL Audience Manager] rapporter visas resultat som baseras på en uppsättning av den totala mängden tillgängliga data. Samplade data-förhållandet är 1:54. För rapporter där exempeldata används innebär detta att resultaten baseras på 1 post av varje uppsättning med 54 poster.

Dessa rapporter använder exempeldata eftersom de behöver en enorm mängd datorkraft för att generera resultat. Sampling hjälper till att hitta en balans mellan minskade datorkrav, bibehållna systemprestanda och ge korrekta resultat.

Rapporter som använder sampling utesluter egenskaper och segment när de inte uppfyller minimikraven för unika besökare. Dessa minimikrav är följande:

* Traits: 28 000 [unika](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) intäktsgenereringar under en 14-dagarsperiod.
* Segment: 70 000 användare i realtid under en 14-dagarsperiod.

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

## Rapporter som använder provdata {#reports-using-sampled-data}

De [!DNL Audience Manager] rapporter där exempeldata används är bland annat:

* [Överlappningsrapporter](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait och segment-to-segment).
* [Adresserbara](../features/addressable-audiences.md) målgruppsdata (data på kund- och segmentnivå).
* Måttet [för totala enheter](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) för en [!UICONTROL Profile Merge Rule].
