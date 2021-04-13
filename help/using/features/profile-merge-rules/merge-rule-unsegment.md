---
description: Osegmentering beskriver processer som diskvalificerar och tar bort enhetsprofiler från segment. Din möjlighet att ta bort en enhetsprofil från ett segment beror på vilket enhetsalternativ som används för att skapa en profilkopplingsregel.
seo-description: Osegmentering beskriver processer som diskvalificerar och tar bort enhetsprofiler från segment. Din möjlighet att ta bort en enhetsprofil från ett segment beror på vilket enhetsalternativ som används för att skapa en profilkopplingsregel.
seo-title: Regler för profilsammanslagning och avsegmenteringsprocesser för enheter
solution: Audience Manager
title: Regler för profilsammanslagning och avsegmenteringsprocesser för enheter
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Sammanfoga profil
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# Regler för profilsammanslagning och avsegmenteringsprocesser för enheter {#profile-merge-rules-and-device-un-segmentation-processes}

Osegmentering beskriver processer som diskvalificerar och tar bort enhetsprofiler från segment. Din möjlighet att ta bort en enhetsprofil från ett segment beror på vilket enhetsalternativ som används för att skapa en [!UICONTROL Profile Merge Rule].

## Tillgängliga enhetsalternativ {#device-options}

Som påminnelse är [!UICONTROL Device Options] tillgängligt i [!UICONTROL Profile Merge Rules Setup]-avsnittet när du skapar eller redigerar en [!UICONTROL Profile Merge Rule].

## Aktuellt enhetsprofilsalternativ och Osegmentering av enhet {#current-device-profile-options}

**[!UICONTROL Device Profile]** är standardalternativet för enhetsprofiler för en  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] kan ta bort en enhetsprofil från ett segment när du  [!UICONTROL Profile Merge Rule] använder  **[!UICONTROL Device Profile]** alternativet. Under dessa förhållanden sker avsegmentering när:

* Enhetsprofilen har varit inaktiv i 120 dagar. En veckovis datarensningsprocess tar bort inaktiva enhetsprofiler från era segment.
* Enheten är inte längre berättigad till ett segment eftersom uppdateringar eller ändringar av enhetsprofilen diskvalificerar det. Det här inträffar när villkoren för godkännande av segment ändras, eller när du tillämpar en [!DNL AND NOT]-operator på en segmentregel, eller anger [villkor för senaste och frekvens](../segments/recency-and-frequency.md) som använder inställningarna mindre än/lika med. Användningsexempel beskrivs i [dokumentationen för inaktivering av direktenheter](instant-cross-device-suppression.md).

![endast enhet](assets/device-only.png)

## Inget enhetsalternativ och ingen enhetssegmentering {#no-device-option}

[!DNL Audience Manager] kan ta bort ett enhets-ID från ett segment när du  [!UICONTROL Profile Merge Rule] använder  **[!UICONTROL Current Authenticated Profiles]** +- **[!UICONTROL No Device Profile]** alternativet. Under dessa förhållanden sker avsegmentering när enhets-ID inte längre kvalificerar för ett segment eftersom uppdateringar eller ändringar av enhetsprofilen diskvalificerar det. Det här inträffar när villkoren för godkännande av segment ändras, eller när du tillämpar en [!UICONTROL AND NOT]-operator på en segmentregel, eller anger [villkor för senaste och frekvens](../segments/recency-and-frequency.md) som använder inställningarna mindre än/lika med. Användningsexempel beskrivs i [dokumentationen för inaktivering av direktenheter](instant-cross-device-suppression.md).

![](assets/current-no-device.png)

## Alternativ för enhetsdiagram och osegmentering av enheter {#device-graph-options-unsegmentation}

[!DNL Audience Manager] kan ta bort flera enhetsprofiler från ett segment när du  [!UICONTROL Profile Merge Rule] använder ett enhetsdiagramalternativ. Osegmentering inträffar när den sammanfogade profilen för enheten från enhetsdiagrammet inte längre kvalificerar sig för segmentet eftersom uppdateringar eller ändringar av den sammanfogade profilen diskvalificerar det från segmentet. Det här inträffar när villkoren för godkännande av segment ändras, eller när du tillämpar en [!UICONTROL AND NOT]-operator på en segmentregel, eller anger [villkor för senaste och frekvens](../segments/recency-and-frequency.md) som använder inställningarna mindre än/lika med. Användningsexempel beskrivs i [dokumentationen för inaktivering av direktenheter](instant-cross-device-suppression.md).

>[!NOTE]
>
>**100-enhetsgräns för utvärdering och diskvalificering** av segment.
>Audience Manager sammanfogar upp till 100 enheter när segment utvärderas med en profilsammanfogningsregel som använder ett enhetsdiagram. Audience Manager utvärderar den aktuella enheten och upp till 99 enheter som är länkade till den aktuella enheten med en [autentiserad profil](../../reference/visitor-authentication-states.md) (enhets-ID). Om signalen för att dela upp segment skickas tas den aktuella enheten och ytterligare enheter bort från segmentet i målet.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Vanliga frågor om regler för profilsammanslagning och enhetsdiagram](../../faq/faq-profile-merge.md)
>* [Omgående enhetsövergripande undertryckning](instant-cross-device-suppression.md)

