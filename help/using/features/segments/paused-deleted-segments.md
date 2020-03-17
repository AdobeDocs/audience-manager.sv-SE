---
description: Beskriver effekterna för segmenterade användare, data och mål när du pausar eller tar bort ett aktivt segment med hjälp av Segment Builder.
seo-description: Beskriver effekterna för segmenterade användare, data och mål när du pausar eller tar bort ett aktivt segment med hjälp av Segment Builder.
seo-title: Pausade och borttagna segment
solution: Audience Manager
title: Pausade och borttagna segment
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Pausade och borttagna segment {#paused-and-deleted-segments}

Beskriver effekterna för segmenterade användare, data och mål när du pausar eller tar bort ett aktivt segment med [!UICONTROL Segment Builder].

## Åtkomst till kontrollerna Pausa och Ta bort

Håll pekaren över ett segmentnamn i segmentlistan för att visa **[!UICONTROL pause]** - och **[!UICONTROL delete]** ikonerna (i [!UICONTROL Actions] kolumnen). Dessa funktioner påverkar segment enligt beskrivningen nedan.

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
* Kan inte tas bort.
* Skickar inte data till associerade mål.
* Returnerar inte data i tillgängliga rapporter.

>[!NOTE]
>
>Du kan också pausa och ta bort segment med en [!DNL API] metod. Mer information finns i [REST API](../../api/rest-api-main/rest-api-main.md).