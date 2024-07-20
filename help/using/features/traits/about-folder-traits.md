---
description: Med mappegenskaper kan du automatiskt samla egenskaper som finns i samma mapp och alla underordnade mappar till ett målsegment.
keywords: segmentstorleksskattare;segment
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Mappegenskaper om
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Mappegenskaper: Om {#folder-traits-about}

Med [!UICONTROL Folder traits] kan du automatiskt samla egenskaper som finns i samma mapp och alla underordnade mappar till ett målsegment.

## Fördelar med att använda mappegenskaper {#benefits}

En [!UICONTROL folder trait] innehåller alla egenskaper i en överordnad mapp och dess associerade underordnade mappar. Detta gör att du automatiskt kan segmentera och rikta in användarna på olika mappnivåer. Anta att du har en mappstruktur som den här:

`*` Elektronik (överordnad)

    `*` bärbara datorer (underordnad)

        `*` varumärken (indirekt underordnad)

[!UICONTROL Folder traits] kvalificerar alla användare i dessa mappar i en automatiskt skapad [!DNL Electronics] [!UICONTROL Folder Trait] (baserat på namnet på den överordnade mappen). Och den här processen upprepas när du går nedåt i filstrukturen. I det här fallet fångar mappegenskaper alla användare i mapparna för bärbara datorer och varumärken i automatiskt skapade bärbara datorer [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] kan markeras i segmentuttryck. Att välja en [!UICONTROL folder trait] motsvarar att markera alla egenskaper i den mappen och dess undermappar med en [!UICONTROL OR]-gruppering.

![](assets/folder-traits-compare-border.jpg)

## Mappfack - Realisering - aktuell och ofta {#folder-traits-realization}

Frekvensen för en mappegenskap är summan av realisationer av egenskaperna i mappen och dess underordnade mappar. Bilden nedan visar egenskaper A, B och C, som finns i mappen Automomobile. Tänk på att alla egenskaper har följande realiteter:

* Trait A: 5
* Fack B: 1
* Fack C: 1

I det här fallet har [!DNL Automobile Folder Trait] 7 realiseringar.

![](assets/folder_traits_rollup_border.png)

## Mappspårningsrapportering {#folder-traits-reporting}

[!UICONTROL Folder traits] fångar alla användare från egenskaperna i mappstrukturen nedanför dem. Om du flyttar ett spår från en mapp till en annan, sprids ändringen till våra [datainsamlingsservrar](../../reference/system-components/components-data-collection.md) precis som en ändring av en trait-regel. Rapporteringsuppdateringarna i nästa rapporteringskörning för att återspegla den här ändringen över rapporteringsdatumintervallen (1, 7, 14, 30, 60, 90). De gamla rapporteringsnumren från de föregående dagarna ändras inte.

## RBAC-behörigheter (Role-Based Access Controls) {#role-based-access-controls}

För företag som använder [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) kan dina användare med rätt [!UICONTROL RBAC]-behörighet ändra datakällan som är kopplad till [!UICONTROL folder trait]. En användare måste tillhöra en grupp med något av följande:

* `READ` och `WRITE` gruppbehörigheter till en anpassad datakälla.
* `VIEW_ALL_TRAITS` och `EDIT_ALL_TRAITS` jokerbehörighet för anpassade datakällor.

Lär dig hur du tilldelar [!UICONTROL RBAC] behörigheter i [administrationsdokumentationen](../../features/administration/administration-overview.md#create-group).

## Begränsningar och andra överväganden {#limits}

| Objekt | Beskrivning |
|---|---|
| Trait-typ | [!UICONTROL Onboarded traits] och [!UICONTROL algorithmic traits] bidrar med högst 1 realisering till frekvensen för en [!UICONTROL folder trait]. |
| Flytta egenskaper mellan mappar | Om du flyttar ett drag från en mapp till en annan diskvalificeras det attributet från det första mappfältet och kvalificerar det för det andra [!UICONTROL folder trait]. Det innebär att om du tar bort eller flyttar ett drag från mappen, kommer användarna i traits population att segmenteras från segmenten med hjälp av mappegenskapen som ett segmentuttryck. <br> När du mappar Adobe Analytics-segment eller rapportsviter till din Experience Cloud-organisation skapar Audience Manager automatiskt nya, motsvarande, skrivskyddade segment och egenskaper. Du kan inte redigera eller ändra lagringsplatsen för dessa egenskaper från Audience Manager. Alla ändringar du gör i dina mappade Adobe Analytics-segment eller rapportsviter visas i Audience Manager. |
| Systemvariabler | [!UICONTROL Folder traits] kan inte realiseras i händelseanrop med parametern `d_sid`. |
| Rapportering | [!UICONTROL Folder traits] är automatiskt beräknade egenskaper och visas inte i **[!UICONTROL Overlap Reports]**. |
