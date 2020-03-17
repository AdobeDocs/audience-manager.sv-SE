---
description: Osegmentering beskriver processer som diskvalificerar och tar bort enhetsprofiler från segment. Din möjlighet att ta bort en enhetsprofil från ett segment beror på vilket enhetsalternativ som används för att skapa en profilkopplingsregel.
seo-description: Osegmentering beskriver processer som diskvalificerar och tar bort enhetsprofiler från segment. Din möjlighet att ta bort en enhetsprofil från ett segment beror på vilket enhetsalternativ som används för att skapa en profilkopplingsregel.
seo-title: Regler för profilsammanslagning och icke-segmenteringsprocesser för enheter
solution: Audience Manager
title: Regler för profilsammanslagning och icke-segmenteringsprocesser för enheter
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Regler för profilsammanslagning och icke-segmenteringsprocesser för enheter {#profile-merge-rules-and-device-un-segmentation-processes}

Osegmentering beskriver processer som diskvalificerar och tar bort enhetsprofiler från segment. Din möjlighet att ta bort en enhetsprofil från ett segment beror på vilket enhetsalternativ som används för att skapa en [!UICONTROL Profile Merge Rule].

## Tillgängliga enhetsalternativ {#device-options}

Som en påminnelse [!UICONTROL Device Options] är de tillgängliga i avsnittet [!UICONTROL Profile Merge Rules Setup] när du skapar eller redigerar ett [!UICONTROL Profile Merge Rule].

## Aktuellt alternativ för enhetsprofil och osegmentering av enhet {#current-device-profile-options}

**[!UICONTROL Device Profile]** är standardalternativet för enhetsprofiler för en [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] kan ta bort en enhetsprofil från ett segment när du [!UICONTROL Profile Merge Rule] använder **[!UICONTROL Device Profile]** alternativet. Under dessa förhållanden sker avsegmentering när:

* Enhetsprofilen har varit inaktiv i 120 dagar. En veckovis datarensningsprocess tar bort inaktiva enhetsprofiler från era segment.
* Enheten är inte längre berättigad till ett segment eftersom uppdateringar eller ändringar av enhetsprofilen diskvalificerar det. Detta inträffar när villkoren för ett segment ändras, eller när du tillämpar en [!DNL AND NOT] operator på en segmentregel eller anger [villkor för aktuell frekvens och frekvens](../segments/recency-and-frequency.md) som använder inställningarna mindre än/lika med. Användningsexempel beskrivs i dokumentationen för [direkt undertryckning](instant-cross-device-suppression.md) av olika enheter.

![endast enhet](assets/device-only.png)

## Inget enhetsalternativ och ingen enhetssegmentering {#no-device-option}

[!DNL Audience Manager] kan ta bort ett enhets-ID från ett segment när du [!UICONTROL Profile Merge Rule] använder alternativet **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** . Under dessa förhållanden sker avsegmentering när enhets-ID inte längre kvalificerar för ett segment eftersom uppdateringar eller ändringar av enhetsprofilen diskvalificerar det. Detta inträffar när villkoren för ett segment ändras, eller när du tillämpar en [!UICONTROL AND NOT] operator på en segmentregel eller anger [villkor för aktuell frekvens och frekvens](../segments/recency-and-frequency.md) som använder inställningarna mindre än/lika med. Användningsexempel beskrivs i dokumentationen för [direkt undertryckning](instant-cross-device-suppression.md) av olika enheter.

![](assets/current-no-device.png)

## Alternativ för enhetsdiagram och osegmentering av enheter {#device-graph-options-unsegmentation}

[!DNL Audience Manager] kan ta bort flera enhetsprofiler från ett segment när du [!UICONTROL Profile Merge Rule] använder ett enhetsdiagramalternativ. Osegmentering inträffar när den sammanfogade profilen för enheten från enhetsdiagrammet inte längre kvalificerar sig för segmentet eftersom uppdateringar eller ändringar av den sammanfogade profilen diskvalificerar det från segmentet. Detta inträffar när villkoren för ett segment ändras, eller när du tillämpar en [!UICONTROL AND NOT] operator på en segmentregel eller anger [villkor för aktuell frekvens och frekvens](../segments/recency-and-frequency.md) som använder inställningarna mindre än/lika med. Användningsexempel beskrivs i dokumentationen för [direkt undertryckning](instant-cross-device-suppression.md) av olika enheter.

>[!NOTE]
>
>**100-enhetsgräns för utvärdering och diskvalificering**av segment.
>Audience Manager sammanfogar upp till 100 enheter när segment utvärderas med en profilsammanfogningsregel som använder ett enhetsdiagram. Audience Manager utvärderar den aktuella enheten och upp till 99 enheter som är länkade till den aktuella enheten med en [autentiserad profil](../../reference/visitor-authentication-states.md) (enhets-ID). Om signalen för att dela upp segment skickas tas den aktuella enheten och ytterligare enheter bort från segmentet i målet.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Vanliga frågor om regler för profilsammanslagning och enhetsdiagram](../../faq/faq-profile-merge.md)
>* [Direkt undertryckning av olika enheter](instant-cross-device-suppression.md)

