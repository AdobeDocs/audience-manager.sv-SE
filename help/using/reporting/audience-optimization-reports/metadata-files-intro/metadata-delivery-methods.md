---
description: Skicka eller uppdatera metadatafiler genom att skicka dem till en särskild Amazon S3-katalog för ditt Audience Manager-konto. I det här avsnittet finns information om leverans-/katalogsökvägar, bearbetningstider och uppdateringar.
seo-description: Skicka eller uppdatera metadatafiler genom att skicka dem till en särskild Amazon S3-katalog för ditt Audience Manager-konto. I det här avsnittet finns information om leverans-/katalogsökvägar, bearbetningstider och uppdateringar.
seo-title: Leveransmetoder för metadatafiler
solution: Audience Manager
title: Leveransmetoder för metadatafiler
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 62147fc719a59d2b2c7b444bce853334b03816c6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---


# Leveransmetoder för metadatafiler{#delivery-methods-for-metadata-files}

Skicka eller uppdatera metadatafiler genom att skicka dem till en särskild [!DNL Amazon S3] katalog för ditt Audience Manager-konto. I det här avsnittet finns information om leverans-/katalogsökvägar, bearbetningstider och uppdateringar.

>[!IMPORTANT]
>
> Kontakta Audience Manager-konsulten eller kundtjänst för att komma igång och konfigurera en [!DNL Amazon S3] katalog för dina metadatafiler.

## Leveranssökvägssyntax och exempel {#syntax}

Data lagras i separata namnutrymmen för varje kund i en [!DNL Amazon S3] katalog. Filsökvägen följer den syntax som visas nedan. Obs! Vinkelparenteser `<>` anger en variabelplatshållare. De andra elementen är konstanter och ändras inte.

**Syntax:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Exempel:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

I följande tabell definieras vart och ett av dessa element i en filleveranssökväg.


| Filparameter | Beskrivning |
---------|----------|
| `.../log_ingestion/` | Detta är början på kataloglagringssökvägen. Du får den fullständiga sökvägen när allt är klart. |
| `pid=<AAM ID>` | Detta nyckelvärdepar innehåller ditt kund-ID för Audience Manager. |
| `dpid=<d_src>` | Detta nyckelvärdepar innehåller det datakälla-ID som skickades vid ett händelseanrop. Datakällans ID är det värde som kopplar allt innehåll i filen till de data som den hör till. </br> Exempel: du har en kreatör med ID 123 och namnet&quot;Advertiser Creative A&quot;. Som ett händelseanrop skickas bara ID:t du behöver inkludera&quot;Advertiser Creative A&quot; i metadatafilen. Kampanjen och den kreativa delen tillhör en datakälla. Datakällans ID är det som knyter samman dessa och gör att vi kan koppla filinnehåll till ett ID som skickas vid ett händelseanrop. Se [hur ID:n för händelsesamtal avgör filnamn, innehåll och leveransvägar](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Det här är filnamnet. Se [Namnkonventioner för metadatafiler](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Filbehandlingstider och uppdateringar {#processing-times}

Metadatafiler bearbetas fyra gånger om dagen med regelbundna intervall.

Om du vill uppdatera dina metadataposter skickar du bara en fil som innehåller ny information. Du behöver inte skicka fullständiga uppdateringar varje gång.
