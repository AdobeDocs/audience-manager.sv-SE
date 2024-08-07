---
description: Det här är speciella egenskaper som används av adresserbara målgrupper. Active Audience and Data Source Synced Traits (Aktiv publik och Synced Traits) finns i Audience Data > Traits > Audience Traits (Målgrupper).
seo-description: These are special traits used by Addressable Audiences. Active Audience and Data Source Synced Traits are located in Audience Data > Traits > Audience Traits.
seo-title: Active Audience Traits and Data Source Synced Traits
solution: Audience Manager
title: Aktiva målgrupper och Source Synced Traits (datakunskaper)
uuid: b4f145ab-f343-4d71-86d1-5d03f7b03809
feature: Traits
exl-id: 8fa4ea24-1beb-40cb-bdec-540a3f7c2573
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# Aktiva målgrupper och Source Synced Traits (datakunskaper) {#active-audience-traits-and-data-source-synced-traits}

Det här är specialegenskaper som används av [!UICONTROL Addressable Audiences]. [!UICONTROL Active Audience] och [!UICONTROL Data Source Synced Traits] finns i [!UICONTROL Audience Data > Traits > Audience Traits].

>[!NOTE]
>
>Åtkomst kräver administratörsbehörighet.

## Aktiva målgruppsegenskaper {#active-audience-traits}

En [!UICONTROL Active Audience]-egenskap innehåller alla enheter som hanteras i ditt [!DNL Audience Manager]-konto. Du kan använda en [!UICONTROL Active Audience Trait] som andra egenskaper när du skapar eller redigerar segment. Dessutom kräver [adresserbara målgrupper](../../features/addressable-audiences.md) det här felet för att generera överlappningsdata. Alla konton har egenskapen [!UICONTROL Active Audience] som standard. Det går inte att ta bort den här egenskapen.

## Synkroniserade dataegenskaper för Source {#data-source-synced-traits}

[!UICONTROL Data Source Synced Traits] visas i mappen [!UICONTROL Audience Traits] när du [skapar eller redigerar en datakälla](../../features/manage-datasources.md#create-data-source) och tillämpar någon av dessa inställningar:

![](assets/datasource_synced.png)

[!UICONTROL Data Source Synced Traits] spårar alla användare som är associerade med en datakälla. Du kan använda en [!UICONTROL Data Source Synched Trait] som andra egenskaper när du skapar eller redigerar segment. När du skapar en [!UICONTROL Data Source Synced Trait] matchar trait-namnet det namn som används av datakällan. Redigera datakällan om du vill ändra namnet på egenskapen. Dessa egenskaper kan inte tas bort.

>[!TIP]
>
>[!UICONTROL Data Source Synced Traits] är användbart vid felsökning. Klicka på ett trait-namn om du vill kontrollera måtten på sidan trait summary. Om den valda egenskapen returnerar data, indikerar det att ID-synkroniseringsprocessen är korrekt konfigurerad och data skickas till [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [Adresserbara målgrupper](../../features/addressable-audiences.md)
