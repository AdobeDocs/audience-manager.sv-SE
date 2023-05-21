---
description: Recommendations och användningsexempel för återmarknadsföring av segment och anpassade segmentkvalifikationer med enhetsdiagrammet Profile Link.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Användningsexempel för enhetsdiagram för profillänk
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 7%

---

# Användningsexempel för enhetsdiagram för profillänk {#profile-link-device-graph-use-cases}

Recommendations och användningsexempel för återmarknadsföring av segment och anpassade segmentkvalifikationer med [!UICONTROL Profile Link Device Graph].

## Recommendations {#recommendations}

Tänk på [!UICONTROL Profile Link] enhetsdiagram för kampanjer som

* Ha en hög autentiseringsnivå över alla digitala resurser. Använd en [externt enhetsdiagram, alternativ](merge-rule-definitions.md#device-options) om du har ett litet antal autentiserade användare.
* Kräv korrekt målinriktning av kända målgrupper. The [!UICONTROL Profile Link Device Graph] byggs med autentiserade data från första part.
* Rikta in er till kända målgrupper i autentiserade och oautentiserade lägen i realtid.

![](assets/merge-rule-triangle2.png)

## Målinriktning mellan olika enheter {#cross-device-personalization}

Låt oss säga att John äger tre enheter som han regelbundet använder för att söka efter semestererbjudanden: hans bärbara dator ([!DNL Device 1]), hans smartphone ([!DNL Device 2]) och hans surfplatta ([!DNL Device 3]). John använder dock sina enheter för att söka efter olika objekt i paketerbjudandena:

* Han använder sin bärbara dator för att söka efter flyg,
* Han använder sin smarttelefon för att söka efter hotell,
* Han använder sin surfplatta för att söka efter guidade turer.

Även om John inte är autentiserad på alla tre av de enheter som nämns ovan, genom att använda **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** en semesterpaketleverantör kan koppla dessa enheter till Johns autentiserade profil, förutsatt att han var den sista personen som autentiserades på alla tre enheterna.

![last-device-graph](assets/last-device-graph.png)

Eftersom Audience Manager kvalificerar alla enhetsprofiler som ingår i profilsammanfogningen för ett segment segmenteras alla tre enhetsprofilerna. The [!UICONTROL Profile Link Device Graph] gör att Audience Manager kan titta på beteendet på alla tre enheter och kvalificera alla enheter för ett segment som ingen enskild enhetsprofil kvalificerar sig för.

Detta [!UICONTROL Profile Merge Rule] gör det möjligt för marknadsförare att leverera en enhetlig upplevelse till alla enheter som ägs av en person, baserat på användaraktiviteten i stället för den enskilda enhetsaktiviteten.

![personalisering på olika enheter](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Användningsexempel för externt enhetsdiagram](external-graph-use-cases.md)
>* [Allmänna användningsexempel för regler för profilsammanslagning](merge-rule-targeting-options.md)
>* [Vanliga frågor om regler för profilsammanslagning](../../faq/faq-profile-merge.md)

