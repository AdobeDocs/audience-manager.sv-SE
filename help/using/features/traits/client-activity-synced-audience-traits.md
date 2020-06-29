---
description: Det här är speciella egenskaper som används av adresserbara målgrupper. Synkroniserade egenskaper för aktiv publik och datakälla finns i Målgruppsdata > Traits > Audience Traits.
seo-description: Det här är speciella egenskaper som används av adresserbara målgrupper. Synkroniserade egenskaper för aktiv publik och datakälla finns i Målgruppsdata > Traits > Audience Traits.
seo-title: Synkroniserade egenskaper för aktiv målgrupp och datakälla
solution: Audience Manager
title: Synkroniserade egenskaper för aktiv målgrupp och datakälla
uuid: b4f145ab-f343-4d71-86d1-5d03f7b03809
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---


# Synkroniserade egenskaper för aktiv målgrupp och datakälla {#active-audience-traits-and-data-source-synced-traits}

Det här är speciella egenskaper som används av [!UICONTROL Addressable Audiences]. [!UICONTROL Active Audience] och [!UICONTROL Data Source Synced Traits] finns i [!UICONTROL Audience Data > Traits > Audience Traits].

>[!NOTE]
>
>Åtkomst kräver administratörsbehörighet.

## Aktiva målgruppsegenskaper {#active-audience-traits}

En [!UICONTROL Active Audience] egenskap innehåller alla enheter som hanteras i ditt [!DNL Audience Manager] konto. Du kan använda en [!UICONTROL Active Audience Trait] liknande egenskap när du skapar eller redigerar segment. Dessutom kräver [adresserbara målgrupper](../../features/addressable-audiences.md) det här värdet för att generera överlappningsdata. Alla konton har som standard en [!UICONTROL Active Audience] egenskap. Det går inte att ta bort den här egenskapen.

## Synkroniserade egenskaper för datakälla {#data-source-synced-traits}

[!UICONTROL Data Source Synced Traits] visas i [!UICONTROL Audience Traits] mappen när du [skapar eller redigerar en datakälla](../../features/manage-datasources.md#create-data-source) och tillämpar någon av dessa inställningar:

![](assets/datasource_synced.png)

[!UICONTROL Data Source Synced Traits] spåra alla användare som är associerade med en datakälla. Du kan använda en [!UICONTROL Data Source Synched Trait] liknande egenskap när du skapar eller redigerar segment. När du skapar en [!UICONTROL Data Source Synced Trait]sträng matchar trait-namnet det namn som används av datakällan. Redigera datakällan om du vill ändra namnet på egenskapen. Dessa egenskaper kan inte tas bort.

>[!TIP]
>
>[!UICONTROL Data Source Synced Traits] är användbara vid felsökning. Klicka på ett trait-namn om du vill kontrollera måtten på sidan trait summary. Om den valda egenskapen returnerar data, indikerar det att ID-synkroniseringsprocessen är korrekt konfigurerad och data skickas till [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [Adresserbara målgrupper](../../features/addressable-audiences.md)

