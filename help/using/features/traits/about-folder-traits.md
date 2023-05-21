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
source-wordcount: '522'
ht-degree: 1%

---

# Mapp-traits: Om {#folder-traits-about}

[!UICONTROL Folder traits] gör att du automatiskt kan samla egenskaper som finns i samma mapp och alla underordnade mappar i ett målsegment.

## Fördelar med att använda mappegenskaper {#benefits}

A [!UICONTROL folder trait] innehåller alla egenskaper i en överordnad mapp och tillhörande underordnade mappar. Detta gör att du automatiskt kan segmentera och rikta in användarna på olika mappnivåer. Anta att du har en mappstruktur som den här:

`*` Elektronik (överordnad)

    `*` Bärbara datorer (underordnade)

        `*` Varumärken (indirekt underordnade)

[!UICONTROL Folder traits] kvalificera alla användare i dessa mappar i en automatiskt skapad [!DNL Electronics] [!UICONTROL Folder Trait] (baserat på namnet på den överordnade mappen). Och den här processen upprepas när du går nedåt i filstrukturen. I det här fallet fångar mappegenskaper alla användare i mapparna för bärbara datorer och varumärken i en automatiskt skapad bärbar dator [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] kan markeras i segmentuttryck. Markera en [!UICONTROL folder trait] motsvarar att markera alla egenskaper i den mappen och dess undermappar med en [!UICONTROL OR] gruppering.

![](assets/folder-traits-compare-border.jpg)

## Mappfack - Realisering - aktuell och ofta {#folder-traits-realization}

Frekvensen för en mappegenskap är summan av realisationer av egenskaperna i mappen och dess underordnade mappar. Bilden nedan visar egenskaper A, B och C, som finns i mappen Automomobile. Tänk på att alla egenskaper har följande realiteter:

* Trait A: 5
* Fack B: 1
* Fack C: 1

I det här fallet [!DNL Automobile Folder Trait] har 7 realisationer.

![](assets/folder_traits_rollup_border.png)

## Mappspårningsrapportering {#folder-traits-reporting}

[!UICONTROL Folder traits] hämta alla användare från egenskaperna i mappstrukturen nedanför dem. Om du flyttar ett spår från en mapp till en annan, sprids ändringen till [datainsamlingsservrar](../../reference/system-components/components-data-collection.md) precis som en förändring av reglerna. Rapporteringsuppdateringarna i nästa rapporteringskörning för att återspegla den här ändringen över rapporteringsdatumintervallen (1, 7, 14, 30, 60, 90). De gamla rapporteringsnumren från de föregående dagarna ändras inte.

## RBAC-behörigheter (Role-Based Access Controls) {#role-based-access-controls}

För företag som använder [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), dina användare med [!UICONTROL RBAC] behörigheter kan ändra datakällan som är kopplad till [!UICONTROL folder trait]. En användare måste tillhöra en grupp med något av följande:

* `READ` och `WRITE` gruppbehörigheter till en anpassad datakälla.
* `VIEW_ALL_TRAITS` och `EDIT_ALL_TRAITS` behörigheter för jokertecken för trait-datakällor.

Lär dig tilldela [!UICONTROL RBAC] behörigheter i [dokumentation](../../features/administration/administration-overview.md#create-group).

## Begränsningar och andra överväganden {#limits}

| Objekt | Beskrivning |
|---|---|
| Trait-typ | [!UICONTROL Onboarded traits] och [!UICONTROL algorithmic traits] bidrar till högst 1 realisering av [!UICONTROL folder trait]Hur ofta. |
| Flytta egenskaper mellan mappar | Om du flyttar ett spår från en mapp till en annan diskvalificeras det från det första mappfältet och kvalificerar det för det andra [!UICONTROL folder trait]. Det innebär att om du tar bort eller flyttar ett drag från mappen, kommer användarna i traits population att segmenteras från segmenten med hjälp av mappegenskapen som ett segmentuttryck. <br> När du mappar Adobe Analytics-segment eller rapportsviter till din Experience Cloud-organisation skapar Audience Manager automatiskt nya, motsvarande, skrivskyddade segment och egenskaper. Du kan inte redigera eller ändra lagringsplatsen för dessa egenskaper från Audience Manager. Alla ändringar du gör i dina mappade Adobe Analytics-segment eller rapportsviter visas i Audience Manager. |
| Systemvariabler | [!UICONTROL Folder traits] kan inte realiseras i händelseanrop med `d_sid` parameter. |
| Rapporter | [!UICONTROL Folder traits] är autokalkylerade egenskaper och visas inte i **[!UICONTROL Overlap Reports]**. |
