---
description: Använd visningsprogrammet för besökarprofiler för att visa det aktuella läget för en användarprofil för den aktuella webbläsaren, inklusive dess egenskaper och segment. För varje trait kan du visa dess SID, namn, information om hur besökaregenskaper realiserades (första eller tredje part), realiseringstidpunkten och frekvensen för realiseringar. För varje segment kan du visa dess SID, namn och datum för segmentmedlemskapet. Du kan även visa besökarprofilen för ett annat Audience Manager profil-ID (UUID). Visningsprogrammet för besökarprofiler är användbart i felsökningssyfte.
keywords: positionsparameter
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: Visningsprogram för besökarprofiler
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Visningsprogram för besökarprofiler {#visitor-profile-viewer}

Använd [!UICONTROL Visitor Profile Viewer] för att visa det aktuella läget för en användarprofil för den aktuella webbläsaren, inklusive dess egenskaper och segment. För varje egenskap kan du visa dess [!UICONTROL SID], namn, information om hur besökaregenskaper realiserades (första eller tredje part), realiseringsdatum och realiseringstid. För varje segment kan du visa dess [!UICONTROL SID], namn och datum för segmentmedlemskap. Du kan även visa besökarprofilen för ett annat Audience Manager-profil-ID ([!UICONTROL UUID]). [!UICONTROL Visitor Profile Viewer] är användbart i felsökningssyfte.

>[!NOTE]
>
>* Åtkomst kräver [!UICONTROL Administrator] behörigheter.
>* Det tar 24 timmar innan information om realiserade segment och anpassade egenskaper visas i användargränssnittet.

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Klicka på **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *(Valfritt)* Klicka på trait-namnet om du vill visa den egenskapen i [!UICONTROL Trait Builder].

   Mer information finns i [Traits](../features/traits/trait-details-page.md).

1. *(Valfritt)* Klicka på segmentnamnet för att visa segmentet i [!UICONTROL Segment Builder].

   Mer information finns i [Segment](../features/segments/segments-purpose.md).

1. *(Villkorligt)* Ange ett annat Audience Manager-profil-ID i rutan **[!UICONTROL UUID]** och klicka sedan på **[!UICONTROL Refresh]** för att visa egenskaperna och segmenten för den användaren.
