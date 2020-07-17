---
description: Med mappegenskaper kan du automatiskt samla egenskaper som finns i samma mapp och alla underordnade mappar till ett målsegment.
keywords: segment size estimator;sse
seo-description: Med mappegenskaper kan du automatiskt samla egenskaper som finns i samma mapp och alla underordnade mappar till ett målsegment.
seo-title: Mappegenskaper om
solution: Audience Manager
title: Mappegenskaper om
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---


# Mapp-traits: Om {#folder-traits-about}

[!UICONTROL Folder traits] gör att du automatiskt kan samla egenskaper som finns i samma mapp och alla underordnade mappar i ett målsegment.

## Fördelar med att använda mappegenskaper {#benefits}

En [!UICONTROL folder trait] innehåller alla egenskaper i en överordnad mapp och dess associerade underordnade mappar. Detta gör att du automatiskt kan segmentera och rikta in användarna på olika mappnivåer. Anta att du har en mappstruktur som den här:

`*` Elektronik (överordnad)

    `*` Bärbara datorer (underordnade)

        `*` Varumärken (indirekt underordnade)

[!UICONTROL Folder traits] kvalificera alla användare i dessa mappar i en automatiskt skapad mapp [!DNL Electronics][!UICONTROL Folder Trait] (baserat på namnet på den överordnade mappen). Och den här processen upprepas när du går nedåt i filstrukturen. I det här fallet fångar mappegenskaper alla användare i mapparna för bärbara datorer och varumärken i en automatiskt skapad bärbar dator [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] kan markeras i segmentuttryck. Att markera en mapp [!UICONTROL folder trait] motsvarar att markera alla egenskaper i den mappen och dess undermappar med en [!UICONTROL OR] gruppering.

![](assets/folder-traits-compare-border.jpg)

## Mappfack - Realisering - aktuell och ofta {#folder-traits-realization}

Frekvensen för en mappegenskap är summan av realisationer av egenskaperna i mappen och dess underordnade mappar. Bilden nedan visar egenskaper A, B och C, som finns i mappen Automomobile. Tänk på att alla egenskaper har följande realiteter:

* Trait A: 5
* Fack B: 1
* Fack C: 1

I det här fallet [!DNL Automobile Folder Trait] har vi 7 realiseringar.

![](assets/folder_traits_rollup_border.png)

## Mappspårningsrapportering {#folder-traits-reporting}

[!UICONTROL Folder traits] hämta alla användare från egenskaperna i mappstrukturen nedanför dem. Om du flyttar ett spår från en mapp till en annan, sprids ändringen till våra [datainsamlingsservrar](../../reference/system-components/components-data-collection.md) precis som en förändring av spårningsregler. Rapporteringsuppdateringarna i nästa rapporteringskörning för att återspegla den här ändringen över rapporteringsdatumintervallen (1, 7, 14, 30, 60, 90). De gamla rapporteringsnumren från de föregående dagarna ändras inte.

## RBAC-behörigheter (Role-Based Access Controls) {#role-based-access-controls}

För företag som använder [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) kan dina användare med rätt [!UICONTROL RBAC] behörighet ändra datakällan som är kopplad till [!UICONTROL folder trait]. En användare måste tillhöra en grupp med något av följande:

* `READ` och `WRITE` gruppbehörigheter till en anpassad datakälla.
* `VIEW_ALL_TRAITS` och `EDIT_ALL_TRAITS` jokerbehörighet för trait-datakällor.

Lär dig hur du tilldelar [!UICONTROL RBAC] behörigheter i vår [administrationsdokumentation](../../features/administration/administration-overview.md#create-group).

## Begränsningar och andra överväganden {#limits}

| Objekt | Beskrivning |
|---|---|
| Trait-typ | [!UICONTROL Onboarded traits] och [!UICONTROL algorithmic traits] bidrar med högst 1 realisering till en [!UICONTROL folder trait]frekvens. |
| Flytta egenskaper mellan mappar | Om du flyttar ett drag från en mapp till en annan diskvalificeras det attributet från det första mappfältet och kvalificerar det för det andra [!UICONTROL folder trait]. Det innebär att om du tar bort eller flyttar ett drag från mappen, kommer användarna i traits population att segmenteras från segmenten med hjälp av mappegenskapen som ett segmentuttryck. <br> När du mappar Adobe Analytics-segment eller rapportsviter till din Experience Cloud-organisation skapar Audience Manager automatiskt nya, motsvarande, skrivskyddade segment och egenskaper. Du kan inte redigera eller ändra lagringsplatsen för dessa egenskaper från Audience Manager. Alla ändringar du gör i Adobe Analytics-segmenten eller i rapporteringssviterna återspeglas i Audience Manager. |
| Systemvariabler | [!UICONTROL Folder traits] kan inte realiseras i händelseanrop med hjälp av `d_sid` parametern. |
| Rapporter | [!UICONTROL Folder traits] är egenskaper för autoberäkning och visas inte i **[!UICONTROL Overlap Reports]**. |