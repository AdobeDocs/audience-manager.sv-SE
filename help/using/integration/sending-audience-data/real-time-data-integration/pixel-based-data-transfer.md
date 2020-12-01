---
description: Enkla pixlar (som kan användas för att kvalificera användare för egenskaper) utför dataöverföringar i realtid. Med Audience Manager kan kunderna själva skapa valfritt antal pixlar. Pixelsträngar består av enkla ID:n eller nyckelvärdepar.
seo-description: Enkla pixlar (som kan användas för att kvalificera användare för egenskaper) utför dataöverföringar i realtid. Med Audience Manager kan kunderna själva skapa valfritt antal pixlar. Pixelsträngar består av enkla ID:n eller nyckelvärdepar.
seo-title: Pixelbaserade dataöverföringar
solution: Audience Manager
title: Pixelbaserade dataöverföringar
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 4%

---


# Pixelbaserade dataöverföringar {#pixel-based-data-transfers}

Enkla pixlar (som kan användas för att kvalificera användare för egenskaper) utför dataöverföringar i realtid. Med Audience Manager kan kunderna själva skapa valfritt antal pixlar. Pixelsträngar består av enkla ID:n eller nyckelvärdepar.

<!-- c_rt_inbound_pixel_transfers.xml -->

Om du vill aktivera inkommande dataöverföringar gör leverantören och klienten följande:

1. Bestäm vilka egenskaper du vill att leverantören eller partnern ska tända.
1. Hämta pixeln för trait. Håll markören över kolumnen **[!UICONTROL Actions]** på skärmen med listan över egenskaper och klicka på symbolen **[!UICONTROL Get trait URL]** för den önskade egenskapen.
1. Ange [!DNL URL] till leverantören eller partnern.

## Exempel

Detta grundläggande händelseanrop skickar trait ID 1234 till [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Du kan serialisera trait-ID:n i ett händelseanrop för att minska `HTTP`-trafiken från sidan. Lägg till ytterligare trait-ID:n i URL-strängen så som visas i följande exempel:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
