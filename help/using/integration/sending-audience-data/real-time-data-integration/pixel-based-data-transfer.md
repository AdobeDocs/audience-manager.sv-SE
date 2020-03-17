---
description: Enkla pixlar (som kan användas för att kvalificera användare för egenskaper) utför dataöverföringar i realtid. Med Audience Manager-gränssnittet kan kunderna själva skapa valfritt antal pixlar. Pixelsträngar består av enkla ID:n eller nyckelvärdepar.
seo-description: Enkla pixlar (som kan användas för att kvalificera användare för egenskaper) utför dataöverföringar i realtid. Med Audience Manager-gränssnittet kan kunderna själva skapa valfritt antal pixlar. Pixelsträngar består av enkla ID:n eller nyckelvärdepar.
seo-title: Pixelbaserade dataöverföringar
solution: Audience Manager
title: Pixelbaserade dataöverföringar
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixelbaserade dataöverföringar {#pixel-based-data-transfers}

Enkla pixlar (som kan användas för att kvalificera användare för egenskaper) utför dataöverföringar i realtid. Med Audience Manager-gränssnittet kan kunderna själva skapa valfritt antal pixlar. Pixelsträngar består av enkla ID:n eller nyckelvärdepar.

<!-- c_rt_inbound_pixel_transfers.xml -->

Om du vill aktivera inkommande dataöverföringar gör leverantören och klienten följande:

1. Bestäm vilka egenskaper du vill att leverantören eller partnern ska tända.
1. Hämta pixeln för trait. Håll markören över **[!UICONTROL Actions]** kolumnen på skärmen med listan över egenskaper och klicka på symbolen för den önskade egenskapen **[!UICONTROL Get trait URL]** .
1. Ange [!DNL URL] till leverantören eller partnern.

## Exempel

Detta grundläggande händelseanrop skickar trait ID 1234 till [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Du kan serialisera trait-ID:n i ett händelseanrop för att minska `HTTP` trafiken från sidan. Lägg till ytterligare trait-ID:n i URL-strängen så som visas i följande exempel:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
