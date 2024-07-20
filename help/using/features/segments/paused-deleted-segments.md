---
description: Beskriver effekterna för segmenterade användare, data och mål när du pausar eller tar bort ett aktivt segment med hjälp av Segment Builder.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Pausade och borttagna segment
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Pausade och borttagna segment {#paused-and-deleted-segments}

Beskriver effekterna för segmenterade användare, data och mål när du pausar eller tar bort ett aktivt segment med [!UICONTROL Segment Builder].

## Åtkomst till kontrollerna Pausa och Ta bort

Håll pekaren över ett segmentnamn i segmentlistan för att visa ikonerna **[!UICONTROL pause]** och **[!UICONTROL delete]** (i kolumnen [!UICONTROL Actions]). Dessa funktioner påverkar segment enligt beskrivningen nedan.

## Pausad segmentfunktion

Ett pausat (inaktiverat) segment:

* Sluta segmentera nya, kvalificerade användare.
* Bevarar en användares segmenteringsstatus/medlemskap (tar inte bort en användare från segmentet).
* Bevaras i segmentlistan och kan återaktiveras.
* Skickar inte data till associerade mål.
* Returnerar data i tillgängliga rapporter (fram till inaktiveringsdatumet).

## Borttagen segmentfunktion

Ett borttaget segment:

* Sluta segmentera nya, kvalificerade användare.
* Tar bort kvalificerade användare från segmentmedlemskap.
* Är borttagen från segmentlistan.
* Det går inte att ångra borttagningen.
* Skickar inte data till associerade mål.
* Returnerar inte data i tillgängliga rapporter.

>[!NOTE]
>
>Du kan också pausa och ta bort segment med en [!DNL API]-metod. Mer information finns i [REST API:er](../../api/rest-api-main/rest-api-main.md).
